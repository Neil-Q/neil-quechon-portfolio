<template>
    <section id="about">
        <h3><span class="text_colorized">01. </span>A PROPOS DE MOI</h3>

        <div id="about_presentation">
            <div id="about_presentation_text">
                <h4>Titre Lorem Ipsum</h4>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
                <p>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
                <p>Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
                <p class="text_colorized">En savoir plus -></p>
            </div>
            <div id="temp_picture">
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name:"HomepageAbout"
}
</script>

<style lang="scss">

    #about {
        p {
            text-align: justify;
        }
    }

    #about_presentation {
        display: flex;
        flex-direction: column-reverse;
        align-items: center;
        margin: 0;
        padding: 0;
    }

    #about_presentation_text {
        margin: auto 0;
    }

    #temp_picture {
        height: 24em;
        width: 18em;
        background-color: grey;
    }

    @media (min-width: 60em) {
        #about {
            text-align: left;
            min-height: 100vh;

            h3 {
                padding-left: 3em;
            }
        }

        #about_presentation {
            flex-direction: row;
            justify-content: space-between;
        }

        #about_presentation_text {
            max-width: 60%;
        }
    }

</style>