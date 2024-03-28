<script>
    export let size = 100;
</script>

<div class="con" style="--size: {size}px;">
    <div class="icon">
        <div class="a">U</div>
        <div class="b">P</div>
        <div class="c">P</div>
        <div class="d">U</div>
    </div>
</div>

<style>
    .con {
        padding: calc(var(--size) * 0.2);
    }

    .icon {
        display: flex;
        flex-wrap: wrap;
        width: var(--size);
        height: var(--size);
        transform: rotate(-45deg);
    }

    .icon > div {
        font-family: "Nunito", sans-serif;
        font-weight: 900;

        width: 50%;
        height: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: calc(var(--size) / 1.45);
    }

    .a,
    .d {
        color: var(--up-color);
    }

    .b,
    .c {
        color: black;
    }

    .a {
        transform: rotate(-90deg);
    }

    .c {
        transform: rotate(180deg);
    }

    .d {
        transform: rotate(90deg);
    }
</style>
