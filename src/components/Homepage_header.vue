<template>
    <header>
        <canvas></canvas>
        <section class="hero">
            <p class="text_colorized" id="hello_world">&lt;hello world&gt;</p>
            <h1>Je suis <span class="text_colorized">Neil Quéchon</span></h1>
            <h2 class="text_soft">Développeur web <span class="text_colorized_soft">front-end</span></h2>
            <p>J’aime créer des outils et expériences interactives et dynamiques. Apprendre tous les jours, sur de nombreux sujets, fait partie de ma nature. <br>
            Si je ne suis pas derrière mon ordinateur, vous me trouverez sûrement sur les tatamis.
            </p>
            <div class="button_type_1">
                <a id="hire_me" href="#">Engagez moi !</a>
            </div>
        </section>
    </header>
</template>

<script>
export default {
    name: "HomepageHeader"
}
</script>

<style lang="scss">
    header {
        display: flex;
        width: 100%;
        height: 100vh;
        position: absolute;
        z-index: 1;
        top: 0;
    }

    canvas {
        position:absolute;
        z-index: -1;
        width: 100%;
        height: 100%;
    }

    .hero {
        display: flex;
        flex-direction: column;
        justify-content: center;
        height: 100vh;
        width: 80vw;
        align-items: flex-start;
        margin: auto;
        text-align: left;

        h1, h2 {
            font-size: clamp(40px, 4vw, 60px);
            font-weight: bold;
            margin: 0;
        }

        p {
            max-width: 50em;
            margin-bottom: 2em;
        }
    }

    #hello_world {
        font-weight: bold;
        font-size: var(--font-sz-lg);
    }

    #hire_me {
        padding: 10px 20px;
        font-size: var(--font-sz-lg);
    }

    @media (max-width: 1920px) {
    }

</style>