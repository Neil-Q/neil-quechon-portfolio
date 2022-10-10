<template>
    <NavbarHomepage/>
    <HomepageHeader/>
    <div id="content">
        <main>
            <HomepageAbout/>
            <HomepageSkills/>

            <section id="projects">
                <h3><span class="text_colorized">03. </span>MES PROJETS</h3>
                <ProjectPresentation 
                    v-for="(project, index) in projects"
                    :key="index"
                    :title="project.title"
                    :presentation="project.presentation"
                    :tags="project.tags"
                    :caseStudyLink="project.caseStudyLink"
                    :liveSiteLink="project.liveSiteLink"
                    :gitRepoLink="project.gitRepoLink"
                    :svgIllustration="project.svgIllustration"
                    :image="project.image"
                />
            </section>

            <section id="contact">
                <h3><span class="text_colorized">04. </span>CONTACTEZ MOI</h3>
                <ContactForm :withText="true"/>
            </section>
        </main>
    </div>
    <footer>
        <p>CODE ET DESIGN AVEC ❤ PAR <b>NEIL QUECHON</b> 2022</p>
    </footer>
</template>

<script>
    import NavbarHomepage       from "@/components/Navbar_homepage.vue";
    import HomepageHeader       from "@/components/Homepage_header.vue";
    import HomepageAbout        from "@/components/Homepage_about.vue";
    import HomepageSkills       from "@/components/Homepage_skills.vue";
    import ProjectPresentation  from "@/components/Project_presentation.vue";
    import ContactForm          from "@/components/Contact_form.vue";

    export default {
        name: 'Home',
        components: {
            NavbarHomepage,
            HomepageHeader,
            HomepageAbout,
            HomepageSkills,
            ProjectPresentation,
            ContactForm
        },
        data() {
            return {
                projects: [
                    {
                        title: "Mudo Kwan Challandais",
                        presentation: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
                        tags: ["vue.js", "GSAP", "heroku"],
                        caseStudyLink: "https://github.com/Neil-Q/Mudo-Kwan-Challandais",
                        liveSiteLink: "https://github.com/Neil-Q/Mudo-Kwan-Challandais",
                        gitRepoLink: "https://github.com/Neil-Q/Mudo-Kwan-Challandais",
                        svgIllustration: null,
                        image: null
                    },
                    {
                        title: "Emblem Wars",
                        presentation: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
                        tags: ["vue.js", "GSAP", "heroku"],
                        caseStudyLink: "something",
                        liveSiteLink: "https://github.com/Neil-Q/Mudo-Kwan-Challandais",
                        gitRepoLink: "https://github.com/Neil-Q/Mudo-Kwan-Challandais",
                        svgIllustration: null,
                        image: null
                    }
                ]
            }
        },
        mounted() {
            let projects = document.getElementsByClassName("project_presentation");

            for (let i = 0; i < projects.length; i++) {
                if (i%2 != 0) projects[i].classList.add("reversed");
            }
        }
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

    #contact {
        display: flex;
        flex-direction: column;
        justify-content: center;
        min-height: calc(100vh - var(--footer-height));
    }

    main {
        margin: auto;
        width: 100%;
        max-width: 1200px;
        height: 100%;
    }

    h3 {
        font-size: clamp(2em, 3vw, 2.5em);
        //border: black solid 1px;
        margin-top: calc(var(--navbar-height) + 1em);
        margin-bottom: 2em;
        width: auto;
    }

    footer {
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        font-size: var(--font-sz-sm);
        height: var(--footer-height);
        width: 100%;
        background-color: var(--primary-color-soft);
        color: var(--light-color);
        padding: auto;
    }

    @media(min-width: 40em) {
        #content {
            padding: 0 2em;
        }
    }
</style>
