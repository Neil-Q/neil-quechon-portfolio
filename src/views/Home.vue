<template>
    <NavbarHomepage/>
    <HomepageHeader/>
    <div id="content">
        <main>
            <section id="about">
            </section>

            <section id="skills">
            </section>

            <section id="projects">
            </section>

            <section id="contact">
            </section>

            <footer>
            </footer>
        </main>
    </div>
</template>

<script>
    import NavbarHomepage from "@/components/Navbar_homepage.vue";
    import HomepageHeader from "@/components/Homepage_header.vue";

    export default {
        name: 'Home',
        components: {
            NavbarHomepage,
            HomepageHeader,
        } 
    }
</script>

<style lang="scss">
    body {
        background-color: var(--bg-color);
    }

    #content {
        position: absolute;
        height: 100vh;
        top: 100vh;
        background-color: red;
        width: 100%;
        
    }

    main {
        margin: auto;
        width: 100%;
        height: 100%;
        max-width: 1400px;
        background-color: royalblue;
    }
</style>
