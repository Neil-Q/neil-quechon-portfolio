<template>
    <div class="project_presentation">
        <div class="illustration">
        </div>
        <div class="presentation">
            <h4>{{ title }}</h4>
            <ul class="techno_list">
            </ul>
            <p class="description"></p>
            <div class="links_container"></div>
        </div>
    </div>
</template>

<script>
export default {
    name: "ProjectPresentation",
    props: {
        title: String
    }

        /*svgIllustration: {
            type: string,
            required: true
        },
        image: {
            type: Object,
            required: true
        },
        title: {
            type: string,
            required: true
        },
        technoList: {
            type: array,
            required: true
        },
        description: {
            type: string,
            required: true
        },
        caseStudy: {
            asCaseStudy: {
                type: Boolean,
                default: false,
                requiret: false
            },
            link: {
                type: string
            }
        },
        liveSite: {
            asLiveSite: {
                type: Boolean,
                default: false,
                requiret: false
            },
            link: {
                type: string
            }
        },
        gitRepo: {
            link: {
                type: string,
                required: true
            }
        }*/
}
</script>

<style>

</style>