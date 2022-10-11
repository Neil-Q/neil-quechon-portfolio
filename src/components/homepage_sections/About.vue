<template>
    <section id="about">
        <h3><span class="text_colorized">01. </span>A PROPOS DE MOI</h3>

        <div id="about_presentation">
            <div id="about_presentation_text">
                <h4>J'aime créer des outils beaux et interactifs !</h4>
                <p>Hello, je m'appelle Neil Quéchon ! Après un premier cursus dans l'électrotechnique, j'ai décidé de changer de voie et me reconvertir dans le développement web... domaine qui m'a toujours attiré et me permet de réellement exprimer ma créativité.</p>
                <p>C'est ainsi que j'ai fait le choix et pari risqué, mais valant le coup, de me former en autonomie. Pour ce faire, j'ai appris par la mise en pratique sur divers projets toujours plus challengeants et ambitieux.</p>
                <p>J'ai hâte de faire le grand saut et de continuer à faire progresser mes compétences auprès de la bonne équipe.</p>
                <a class="text_colorized" href="#">En savoir plus -></a>
            </div>
            <div id="profil_picture">
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
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        justify-content: center;

        h4 {
            font-size: var(--font-sz-lg);
            //color: var(--primary-color);
        }

        p, a {
            text-align: justify;
            font-size: var(--font-sz-md);
        }

        a:hover {
            font-weight: bold;
            color: var(--primary-color-soft);
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

    #profil_picture {
        aspect-ratio: 3/4;
        width: 35%;
        background-color: grey;
    }

    @media (min-width: 40em) {
        #about {
            h4 {
                font-size: var(--font-sz-xl);
            }

            p, a {
                font-size: var(--font-sz-lg);
            }
        }
    }

    @media (min-width: 60em) {
        #about {
            text-align: left;
            min-height: 100vh;

            h3 {
                padding-left: 3em;
                margin-bottom: 2em;
            }

            h4 {
                font-size: var(--font-sz-xxl);
            }

            p, a {
                font-size: var(--font-sz-xl);
            }
        }

        #about_presentation {
            flex-direction: row;
            justify-content: space-between;
        }

        #about_presentation_text {
            max-width: 55%;
        }
    }

</style>