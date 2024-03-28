<script>
    import { onMount } from "svelte";
    import { cubicOut } from "svelte/easing";
    import { tweened } from "svelte/motion";
    import classImg from "./imgs/class.jpg";
    import pSomaImg from "./imgs/p_soma.png";
    import aiImg from "./imgs/ai.webp";

    const length = 3;
    const totalAngle = 180 * length;
    const duration = 1000;
    const delay = 3000;

    let angle = 0;
    let index = 0;
    let cardAngle = 0;
    let progress = 0;
    let priorityAngle = null;

    const fixAngle = (angle) => {
        let fixed = angle % totalAngle;
        if (fixed < 0) {
            fixed += totalAngle;
        }
        return fixed;
    };

    const angleToIndex = (priorityAngle, angle) => {
        let fixed = fixAngle(priorityAngle ?? angle);
        if (totalAngle - fixed <= 90) {
            index = 0;
            cardAngle = totalAngle - fixed;
            progress = cardAngle / 90;
        } else {
            index = ((fixed + 90) / 180) | 0;
            let tempAngle = fixed - index * 180;
            cardAngle = -tempAngle;
            progress = Math.abs(tempAngle) / 90;
        }
    };

    const snapAngle = (index, angle) => {
        if (90 > totalAngle - angle) {
            return totalAngle;
        }
        return index * 180;
    };

    const tweenedAngle = tweened(0, {
        duration: duration,
        easing: cubicOut,
    });

    $: $tweenedAngle = angle;
    $: angleToIndex(priorityAngle, $tweenedAngle);

    let timer;
    let c;
    let w;
    let beforePos = 0;
    const startTimer = () => {
        if (timer) {
            return;
        }
        timer = setInterval(() => {
            angle += 180;
        }, delay);
    };
    const stopTimer = () => {
        clearInterval(timer);
        timer = null;
    };

    const start = (x) => {
        beforePos = x;
        w = c.clientWidth;
        priorityAngle = $tweenedAngle;
        stopTimer();
    };

    const move = (x) => {
        priorityAngle += -((x - beforePos) / w) * 180;
        beforePos = x;
    };

    const end = () => {
        let fixed = fixAngle(priorityAngle);
        tweenedAngle.set(fixed, { duration: 0 });
        angle = snapAngle(index, fixed);
        tweenedAngle.set(angle, { duration: duration });
        priorityAngle = null;
        console.log(fixed, angle);
        startTimer();
    };

    const startTouch = (e) => {
        start(e.touches[0].clientX);
        const moveTouch = (e) => {
            move(e.touches[0].clientX);
        };

        const endEvent = () => {
            end();
            document.body.removeEventListener("touchmove", moveTouch);
            document.body.removeEventListener("touchend", endEvent);
            document.body.removeEventListener("touchcancel", endEvent);
        };

        document.body.addEventListener("touchmove", moveTouch);
        document.body.addEventListener("touchend", endEvent);
        document.body.addEventListener("touchcancel", endEvent);
    };

    const startMouse = (e) => {
        start(e.clientX);
        const moveMouse = (e) => {
            move(e.clientX);
        };

        const endEvent = () => {
            end();
            document.body.removeEventListener("mousemove", moveMouse);
            document.body.removeEventListener("mouseup", endEvent);
            document.body.removeEventListener("mouseleave", endEvent);
        };

        document.body.addEventListener("mousemove", moveMouse);
        document.body.addEventListener("mouseup", endEvent);
        document.body.addEventListener("mouseleave", endEvent);
    };

    onMount(() => {
        startTimer();
        return stopTimer;
    });

    class Item {
        constructor(img, title, description, href) {
            this.img = img;
            this.title = title;
            this.description = description;
            this.href = href;
        }
    }

    const items = [
        new Item(
            classImg,
            "仲間と共に学びを深める",
            "Unbiased Programmingではレベルや性別、学部を問わず、楽しくプログラミングを学ぶことができます。",
            "#",
        ),
        new Item(
            pSomaImg,
            "Project Soma",
            "夏に開催されるProject Somaでは先輩のアドバイスを受けながら、チーム開発を行うことができます。",
            "#",
        ),
        new Item(
            aiImg,
            "AIとデータ分析",
            "Unbiased ProgrammingではAIやデータ分析に力を入れており、機械学習やデータ分析を基礎から学ぶことができます。",
            "#",
        ),
    ];
</script>

<div style:--angle={cardAngle} style:--progress={progress} class="container">
    <!-- svelte-ignore a11y-no-static-element-interactions -->
    <div class="wrapper">
        <div
            class="card"
            bind:this={c}
            on:mousedown|preventDefault={startMouse}
            on:touchstart|preventDefault={startTouch}
        >
            {#each items as item, i}
                <div class:show={i === index}>
                    <img src={item.img} alt={item.title} />
                </div>
            {/each}
        </div>
    </div>
    <div class="ditail">
        <h2>{items[index].title}</h2>
        <p>{items[index].description}</p>
    </div>
</div>

<style>
    @media (width < 768px) {
        .container {
            --width: calc(100vw - 100px);
            --height: min(calc(var(--width) * 1.5), calc(100vh - 120px - 9rem));
            position: relative;
            height: 100vh;
            padding-top: 100px;
        }

        .wrapper {
            height: var(--height);
            width: var(--width);
            display: block;
            margin: 0 auto;
        }

        .ditail {
            width: var(--width);
            display: block;
            margin: 0 auto;
            min-height: 9rem;
            margin-top: 3rem;
        }

        .ditail > h2 {
            font-size: 1.2rem;
        }
    }

    @media (width >= 768px) {
        .container {
            display: flex;
            justify-content: center;
            align-items: center;
            --half: calc(100vw / 2 - 100px);
            --height: min(calc(var(--half) * 1.5), calc(100vh - 150px));
            --width: calc(var(--height) / 1.5);
            height: calc(100vh + 50px);
            padding-top: 120px;
            gap: 0 50px;
            padding-bottom: 50px;
        }

        .wrapper {
            height: var(--height);
            width: var(--width);
            display: block;
        }

        .ditail {
            width: var(--width);
            height: var(--height);
            justify-content: center;
        }
    }

    .card {
        width: 100%;
        height: 100%;
    }

    .card > div {
        position: absolute;
        width: 100%;
        height: 100%;
        display: none;
    }

    .card > div.show {
        display: block;
    }

    .card > div > img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .container {
        user-select: none;
    }

    .wrapper {
        perspective-origin: center center;
        perspective: 1000px;
    }

    .card {
        transform: rotateY(calc(var(--angle) * 1deg));
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
        overflow: hidden;
        border-radius: 25px;
    }

    .ditail {
        display: flex;
        flex-direction: column;
    }

    .ditail > * {
        filter: blur(calc(var(--progress) * 6px));
    }
</style>
