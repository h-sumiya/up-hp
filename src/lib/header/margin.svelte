<script>
    import { headerIsLarge } from "../store";
</script>

<div class={$headerIsLarge ? "large" : "small"} />

<style>
    .small {
        height: calc(48px + 3rem);
    }

    .large {
        height: calc(70px + 3rem);
    }
</style>