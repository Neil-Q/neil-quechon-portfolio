<template>
    <router-view/>
</template>

<style lang="scss">
html, body {
  margin: 0px;
  padding: 0px;
}
a {
    text-decoration: none;
}

#app {
    font-family: var(--font-sans), Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: var(--contrast-color);
    width: 100%;
    font-size: var(--font-sz-md);
}

:root {
    --font-sans: "Poppins", "Open Sans", sans-serif;
    --font-sz-xxs: 0.8em;
    --font-sz-xs: 0.85em;
    --font-sz-sm: 0.9em;
    --font-sz-md: 1em;
    --font-sz-lg: 1.1em;
    --font-sz-xl: 1.2em;
    --font-sz-xxl: 1.3em;

    --bg-color: #FAFAFA;
    --primary-color: #B71C1C;
    --primary-color-soft: #c83a3a;
    --contrast-color: #262626;
    --contrast-color-soft: #404040;
    --highlight-color: #ffffff;

    --navbar-height: 70px;

    --breakpoint-small: 40em;
    --breakpoint-medium: 60em;
}

.button_type_1 {
    display: flex;
    align-items: center;
    color: var(--primary-color);
    border: 1px var(--primary-color) solid;
    border-radius: 5px;

    &:hover {
        background-color: var(--highlight-color);
    }

    a {
        color: var(--primary-color);
        margin: auto;
    }
}

.text_colorized {
    color: var(--primary-color);
}

.text_colorized_soft {
    color: var(--primary-color-soft);
}

.text_soft {
    color: var(--contrast-color-soft);
}

@media (prefers-color-scheme: dark) {
    :root {
        --bg-color: #121E2A;
        --primary-color: #1DE9B6;
        --contrast-color: #E6F1FF;
        --contrast-color-soft: #CCD6F6;
        --highlight-color: #172231;
    }
}
</style>
