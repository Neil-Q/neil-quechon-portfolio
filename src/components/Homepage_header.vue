<template>
    <header>
        <canvas id="fog_canvas"></canvas>
        <section class="hero">
            <p class="text_colorized" id="hello_world">&lt;hello world&gt;</p>
            <h1>Je suis <span class="text_colorized">Neil</span></h1>
            <h2 class="text_soft">Développeur <span class="text_colorized_soft">front-end</span></h2>
            <p>J’aime créer des outils et expériences interactives et dynamiques. Apprendre tous les jours, sur de nombreux sujets, fait partie de ma nature. <br>
            Si je ne suis pas derrière mon ordinateur, vous me trouverez sûrement sur les tatamis.
            </p>
            <a id="hire_me" class="button_hollow" href="#">Engagez moi !</a>
        </section>
    </header>
</template>

<script>

class Particle {
    constructor(canvas) {
        this.canvas = canvas;
        this.x = Math.round(this.canvas.width * Math.random());
        this.y = Math.round(this.canvas.height * Math.random());
        this.energy = Math.random();
        this.opacity =  Math.floor(256 * (this.energy * 0.3 + 0.1));
        //this.velocity = this.energy / 10;
        //this.direction = 360 * Math.random(); 
    }
}

export default {
    name: "HomepageHeader",

    methods: {
        drawParticle(particle, canvasWidth, datas) {
            let index = (particle.x + (particle.y * canvasWidth)) * 4;

            datas[index + 0] = 0;
            datas[index + 1] = 0;
            datas[index + 2] = 0;
            datas[index + 3] = particle.opacity;
        },

        generateParticules(canvas, pixelsPerParticule) {
            //let numberOfParticles = canvas.height * canvas.width / pixelsPerParticule;
            let numberOfParticles = pixelsPerParticule;
            let particles = [];

            for(let i = 0; i < numberOfParticles; i++) {
                let newParticle = new Particle(canvas);
                particles.push(newParticle);
            }

            return particles;
        },

        resizeCanvas(canvas) {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        },

        updateCanvas(ctx, data) {
            ctx.putImageData(data, 0, 0);
        }
    },

    mounted() {
        let fogCanvas = document.getElementById("fog_canvas");
        this.resizeCanvas(fogCanvas); // Sans cela le canvas aurait sa valeur par defaut

        let ctx = fogCanvas.getContext("2d");
        let canvasDatas = ctx.getImageData(0, 0, fogCanvas.width, fogCanvas.height);

        let particules = this.generateParticules(fogCanvas, 100000);        

        particules.forEach((particule) => {
            this.drawParticle(particule, fogCanvas.width, canvasDatas.data)
        });

        this.updateCanvas(ctx, canvasDatas);


    }
}
</script>

<style lang="scss">
    header {
        display: flex;
        width: 100%;
        height: 100vh;
        
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

        h1 {
            font-size: clamp(40px, 4vw, 60px);
            font-weight: bold;
            margin: 0;
        }

        h2 {
            font-size: clamp(30px, 3vw, 45px);
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
        font-size: 2em;
        margin-bottom: 0;
    }

    #hire_me {
        padding: 10px 20px;
        font-size: var(--font-sz-lg);
    }

    @media (max-width: 1920px) {
    }

</style>