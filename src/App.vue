<template>
    <router-view/>
    <Footer/>
</template>

<script>
import Footer from "@/components/Footer.vue"

export default {
    components: {
        Footer
    }   
}
</script>


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
    scroll-behavior: smooth;
}

:root {
    --font-sans: "Poppins", "Open Sans", sans-serif;
    --font-sz-xs: 0.8em;
    --font-sz-sm: 0.85em;
    --font-sz-md: 0.9em;
    --font-sz-lg: 1em;
    --font-sz-xl: 1.1em;
    --font-sz-xxl: 1.3em;

    --light-color: #F8F5F5;
    --light-highlight-color: #ffffff;
    --light-primary-color: #B71C1C;
    --light-primary-soft-color: #c83a3a;
    --light-contrast-color: #262626;
    --light-contrast-color-soft: #404040;

    --dark-color: #121E2A;
    --dark-highlight-color: #172737;
    //--dark-primary-color: #1DE9B6;
    //--dark-primary-soft-color: #18b38c;
    --dark-primary-color: #17ddac;
    --dark-primary-soft-color: #1dc79d;
    --dark-contrast-color: #bfc9d6;
    --dark-contrast-color-soft: #949bb3;

    --navbar-height: 70px;
    --footer-height: 3.5em;
}

body {
    --bg-color: var(--light-color);
    --primary-color: var(--light-primary-color);
    --primary-color-soft: var(--light-primary-soft-color);
    --contrast-color: var(--light-contrast-color);
    --contrast-color-soft: var(--light-contrast-soft-color);
    --highlight-color: var(--light-highlight-color);

    &.dark_mode {
        --bg-color: var(--dark-color);
        --primary-color: var(--dark-primary-color);
        --primary-color-soft: var(--dark-primary-soft-color);
        --contrast-color: var(--dark-contrast-color);
        --contrast-color-soft: var(--dark-contrast-soft-color);
        --highlight-color: var(--dark-highlight-color);
    }
}

.button_hollow {
    box-sizing: border-box;
    display: block;
    text-align: center;
    color: var(--primary-color);
    border: 1px var(--primary-color) solid;
    border-radius: 5px;
    background-color: var(--bg-color);
    font-weight: bold;
    height: auto;
    padding: 0em 1em;

    &:hover {
        background-color: var(--highlight-color);
    }
}

.button_solid {
    display: block;
    text-align: center;
    color: var(--bg-color);
    border: none;
    border-radius: 5px;
    background-color: var(--primary-color);
    font-weight: bold;
    height: auto;
    padding: 0.5em 1em;
    font-size: var(--font-sz-sm);

    &:hover {
        background-color: var(--primary-color-soft);
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

.shadow_boxed {
    box-shadow: 0 1px 1px rgba(0,0,0,0.12), 
                0 2px 2px rgba(0,0,0,0.12), 
                0 4px 4px rgba(0,0,0,0.12);

    &_light {
        box-shadow: 0 12px 10px -15px rgba(0,0,0,0.12);
    }

    &_strong {
        box-shadow: 0 1px 1px rgba(0,0,0,0.12), 
                    0 2px 2px rgba(0,0,0,0.12), 
                    0 4px 4px rgba(0,0,0,0.12), 
                    0 8px 8px rgba(0,0,0,0.12),
                    0 16px 16px rgba(0,0,0,0.12);
    }
}

/*@media (prefers-color-scheme: light) {
    :root {
        --bg-color: var(--light-color);
        --primary-color: var(--light-primary-color);
        --primary-color-soft: var(--light-primary-soft-color);
        --contrast-color: var(--light-contrast-color);
        --contrast-color-soft: var(--light-contrast-soft-color);
        --highlight-color: var(--light-highlight-color);


    }
}

@media (prefers-color-scheme: dark) {
    :root {
        --bg-color: var(--dark-color);
        --primary-color: var(--dark-primary-color);
        --primary-color-soft: var(--dark-primary-soft-color);
        --contrast-color: var(--dark-contrast-color);
        --contrast-color-soft: var(--dark-contrast-soft-color);
        --highlight-color: var(--dark-highlight-color);
    }
}*/

@media (min-width: 40em) {
    :root {
        --font-sz-sm: 0.9em;
        --font-sz-md: 1em;
        --font-sz-lg: 1.1em;
        --font-sz-xl: 1.2em;
        --font-sz-xxl: 1.4em;
    }
}

@media (min-width: 60em) {
    :root {
        --font-sz-sm: 1em;
        --font-sz-md: 1.1em;
        --font-sz-lg: 1.4em;
        --font-sz-xl: 1.7em;
        --font-sz-xxl: 2em;
    }
}
</style>
