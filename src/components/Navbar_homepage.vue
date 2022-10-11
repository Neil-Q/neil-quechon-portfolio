<template>
    <nav id="nav_bar">
        <div class="logo">
            <a href="#" id="logo"></a>
        </div>
        <div id="nav_menu">
            <ol>
                <li>
                    <a @click="scrollToAnchorPoint('about')">A propos</a>
                </li>
                <li>
                    <a @click="scrollToAnchorPoint('skills')">Compétences</a>
                </li>
                <li>
                    <a @click="scrollToAnchorPoint('projects')">Projets</a>
                </li>
                <li>
                    <a @click="scrollToAnchorPoint('contact')">Contact</a>
                </li>
            </ol>
            <a id="cv_button" class="button_hollow" href="#">Mon CV</a>
        </div>
        <button id="nav_burger" v-on:click="toggleOverlayNavigation">
            <div></div>
            <div></div>
            <div></div>
        </button>
    </nav>

    <div id="blur_overlay">
    </div>
</template>

<script>
export default {
    name: "NavbarHomepage",
    methods: {
        hideNavBar() {
            let nav_bar = document.getElementById("nav_bar");
            if (!nav_bar.classList.contains("hidden")) nav_bar.classList.add("hidden");
        },

        navBarSetOpacity(toggle) {
            let nav_bar = document.getElementById("nav_bar");
            if(toggle) nav_bar.classList.add("opaque", "shadow_boxed_light");
            else nav_bar.classList.remove("opaque", "shadow_boxed_light");
        },

        scrollToAnchorPoint(anchorId) {
            let el = document.getElementById(anchorId);
            el.scrollIntoView({ behavior: 'smooth'});

            this. toggleOverlayNavigation();
        },

        showNavBar() {
            let nav_bar = document.getElementById("nav_bar");
            if (nav_bar.classList.contains("hidden")) nav_bar.classList.remove("hidden");
        },

        toggleOverlayNavigation() {
            let navOverlay = document.getElementById("nav_menu");
            navOverlay.classList.toggle("reveal");
            let gaussianBlur = document.getElementById("blur_overlay");
            gaussianBlur.classList.toggle("reveal");

            let burger = document.getElementById("nav_burger");
            burger.classList.toggle("checked");
        },

        closeOverlayNavigation() {
            let navOverlay = document.getElementById("nav_menu");
            navOverlay.classList.remove("reveal");
            let gaussianBlur = document.getElementById("blur_overlay");
            gaussianBlur.classList.remove("reveal");

            let burger = document.getElementById("nav_burger");
            burger.classList.remove("checked");
        }

    },
    mounted() {
        let lastScrollY = 0;

        document.addEventListener("scroll", () => {
            let newScrollY = window.scrollY;

            if (newScrollY == lastScrollY) return;

            if (newScrollY > lastScrollY) this.hideNavBar();
            else {
                this.showNavBar();
                window.scrollY === 0 ? this.navBarSetOpacity(false) : this.navBarSetOpacity(true);
            }

            lastScrollY = newScrollY;
        });
    }
}
</script>

<style lang="scss" scoped>

    // Developpé wide-screen-first car le menu burger rend la complexité du composant plus élevée du côté mobile

    #nav_bar {
        display: flex;
        position: fixed;
        z-index: 12;
        box-sizing: border-box;
        flex-direction: row;
        justify-content: space-between;
        width: 100%;
        padding: 0px 50px;
        height: var(--navbar-height);
        align-items: center;
        transition: 0.5s;

        &.opaque {
            background-color: var(--highlight-color);
        }

        &.hidden {
            transform: translateY(calc(-1 * var(--navbar-height)));
        }
    }

    #cv_button {
        margin-left: 25px;
        text-align: center;
        padding: 0.3em 2.5em;
    }

    .logo {
        height: 50px;
        width: 50px;
        margin-top: auto;
        margin-bottom: auto;
        border: 2px var(--primary-color) solid;
        border-radius: 25px;
    }

    #nav_menu {
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-items: center;
        font-size: var(--font-sz-sm);

        ol {
            display: flex;
            flex-direction: row;
            margin: 0px;
        }

        li {
            display: flex;
            margin-right: clamp(0.6em, 2vw, 2.5em);
            counter-increment: nav-link;
            cursor: pointer;

            a {
                padding: 10px;
                color: var(--contrast-color);

                &::before {
                    content: "0" counter(nav-link) ". ";
                    color: var(--primary-color);
                }

                &:hover {
                    color: var(--primary-color);
                }
            }
        }
    }

    #nav_burger {
        display: none;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        padding: 0;
        border: none;
        cursor: pointer;
        width: 40px;
        height: 40px;
        background-color: transparent;

        div {
            width: 40px;
            height: 4px;
            background-color: var(--primary-color);
            border-radius: 2px;
            transition: 0.5s;
            transform-origin: center;
        }

        &.checked {
            div:first-child {
                transform: translateY(18px) rotate(45deg) scale(1.3, 1);
            }

            div:nth-child(2) {
                opacity: 0;
            }

            div:last-child {
                transform: translateY(-18px) rotate(-45deg) scale(1.3, 1);
            }
        }
    }

    #blur_overlay {
        position: fixed;
        z-index: 9;
        width: 100%;
        height: 100%;
        backdrop-filter: blur(10px);
        transition: 0.25s;
        opacity: 0;
    }

    @media (hover: hover) {
        #nav_burger {
            div {
                background-color: var(--primary-color-soft);
            }

            &:not(.checked):hover {
                div:first-child, div:last-child {
                    transform: scale(0.8, 1);
                }
            }

            &.checked:hover {
                
                div:first-child {
                    transform: translateY(18px) rotate(45deg) scale(1);
                }

                div:last-child {
                transform: translateY(-18px) rotate(-45deg) scale(1);
            }
            }
        }
    }

    @media (max-width: 60em) {
        #nav_menu {
            position: absolute;
            flex-direction: column;
            justify-content: center;
            z-index: -20;
            width: 20em;
            max-width: 100vw;
            right: 0;
            top: var(--navbar-height);
            height: calc(100vh - var(--navbar-height));
            background-color: var(--highlight-color);
            transition: 0.25s;
            transform: translateX(30em);
            font-size: var(--font-sz-xxl);

            ol {
                flex-direction: column;
                padding-inline-start: 0;
                font-size: clamp(1.5em, 5vw, 2em);
            }

            li {
                margin-bottom: 1em;
            }

            &.reveal {
                transform: translateX(0);
            }
        }

        #nav_burger {
            display: flex;
        }

        #blur_overlay.reveal {
            opacity: 1;
        }

        #cv_button {
            margin-left: 0;
        }
    }
</style>