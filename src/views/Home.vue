<template>
    <NavbarHomepage/>
    <HomepageHeader/>
    <div id="content">
        <main>
            <HomepageAbout/>
            <HomepageSkills/>

            <section id="projects">
                <ProjectPresentation 
                    v-for="(project, index) in projects"
                    :key="index"
                    :title="project.title"
                />
            </section>

            <section id="contact">
            </section>

            <footer>
            </footer>
        </main>
    </div>
</template>

<script>
    import NavbarHomepage       from "@/components/Navbar_homepage.vue";
    import HomepageHeader       from "@/components/Homepage_header.vue";
    import HomepageAbout        from "@/components/Homepage_about.vue";
    import HomepageSkills       from "@/components/Homepage_skills.vue";
    import ProjectPresentation  from "@/components/Project_presentation.vue";

    export default {
        name: 'Home',
        components: {
            NavbarHomepage,
            HomepageHeader,
            HomepageAbout,
            HomepageSkills,
            ProjectPresentation
        },
        data() {
            return {
                projects: [
                    {
                        title: "Mudo Kwan Challandais",
                        presentation: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
                        tags: ["vue.js", "GSAP", "heroku"],
                        caseStudylink: null,
                        liveSiteLink: null,
                        gitRepoLink: "https://github.com/Neil-Q/Mudo-Kwan-Challandais",
                        svgIllustration: null,
                        image: null
                    },
                    {
                        title: "Emblem Wars",
                        presentation: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
                        tags: ["vue.js", "GSAP", "heroku"],
                        caseStudylink: null,
                        liveSiteLink: null,
                        gitRepoLink: "https://github.com/Neil-Q/Mudo-Kwan-Challandais",
                        svgIllustration: null,
                        image: null
                    }
                ]
            }
        }
    }
</script>

<style lang="scss">
    body {
        background-color: var(--bg-color);
    }

    #content {
        position: absolute;
        box-sizing: border-box;
        top: 100vh;
        // background-color: red;
        width: 100%;
        max-width: 100%;
        padding: 0 1em;
    }

    main {
        margin: auto;
        width: 100%;
        max-width: 1200px;
        // background-color: royalblue;
        height: 100%;
    }

    h3 {
        font-size: clamp(1.5em, 3vw, 2.5em);
    }
</style>
