<template>
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
</template>

<script>
import ProjectPresentation  from "@/components/Project_presentation.vue";

export default {
    name: "HomeProjects",
    components: {
        ProjectPresentation
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

<style>

</style>