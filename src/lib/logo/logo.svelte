<script>
    export let scale = 8;
    export let animate = true;

    const fullU = "Unbiased";
    let u = "";

    const fullP = "Programming";
    let p = "";

    import { onMount } from "svelte";

    if (animate) {
        onMount(async () => {
            for (let i = 0; i < 6; i++) {
                await new Promise((r) => setTimeout(r, 300));
                u = i % 2 ? "|" : " ";
            }
            let i = 1;
            while (i < fullU.length) {
                await new Promise((r) => setTimeout(r, 100));
                u = fullU.slice(0, i + 1) + "|";
                i++;
            }
            u = fullU;
            let j = 0;
            while (j < fullP.length) {
                await new Promise((r) => setTimeout(r, 100));
                p = fullP.slice(0, j + 1) + "|";
                j++;
            }
            p = fullP;
        });
    } else {
        u = fullU;
        p = fullP;
    }
</script>

<div class="logo" style="--base-size: {scale}px;">
    <div class="u">{u}</div>
    <div class="p">{p}</div>
</div>

<style>
    .logo {
        font-family: "Nunito", sans-serif;
        font-size: 2rem;
        font-weight: 800;
    }

    .u {
        color: var(--up-color);
        font-size: calc(var(--base-size) * 5);
        line-height: 0.9;
    }

    .p {
        color: black;
        font-size: calc(var(--base-size) * 4);
        line-height: 0.9;
    }
</style>
