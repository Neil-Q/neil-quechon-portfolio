<template>
    <NavbarHomepage/>
    <Hero/>
    <div id="content">
        <main>
            <About/>
            <Skills/>
            <Projects/>
            <Contact/>            
        </main>
    </div>
</template>

<script>
    import NavbarHomepage       from "@/components/Navbar_homepage.vue";
    import Hero                 from "@/components/homepage_sections/Hero.vue";
    import About                from "@/components/homepage_sections/About.vue";
    import Skills               from "@/components/homepage_sections/Skills.vue";
    import Projects             from "@/components/homepage_sections/Projects.vue";
    import Contact              from "@/components/homepage_sections/Contact.vue";

    export default {
        name: 'Home',
        components: {
            NavbarHomepage,
            Hero,
            About,
            Skills,
            Projects,
            Contact
        },
    }
</script>

<style lang="scss">
    body {
        background-color: var(--bg-color);
    }

    #content {
        box-sizing: border-box;
        top: 100vh;
        width: 100%;
        max-width: 100%;
        padding: 0 1em;
    }

    main {
        margin: auto;
        width: 100%;
        max-width: 1200px;
        height: 100%;
    }

    h3 {
        font-size: clamp(2em, 3vw, 2.5em);
        margin-top: calc(var(--navbar-height) + 1em);
        margin-bottom: 2em;
        width: auto;
        //border: black solid 1px;
    }

    @media(min-width: 40em) {
        #content {
            padding: 0 2em;
        }
    }
</style>
