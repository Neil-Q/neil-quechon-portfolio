<template>
    <footer>
        <p>CODE ET DESIGN AVEC ❤ PAR <b>NEIL QUECHON</b> 2022</p>
    </footer>
</template>

<script>
export default {
    name: "Footer",
}
</script>

<style lang="scss">
    footer {
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        font-size: var(--font-sz-xs);
        height: var(--footer-height);
        width: 100%;
        background-color: var(--primary-color-soft);
        color: var(--bg-color);
        padding: auto;
    }
</style>