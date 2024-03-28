<script>
    export let href = "/";
    export let title = "";
    export let ditail = "";
</script>

<a {href} class="link">
    <p class="t">{title}</p>
    <p class="d">{ditail}</p>
</a>

<style>
    .link {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    .t {
        font-size: 16px;
        font-weight: bold;
        line-height: 1;
    }

    .d {
        font-size: 10px;
    }
</style>
