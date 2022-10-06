<template>
    <nav id="nav_bar">
        <div class="logo">
            <a href="#" id="logo"></a>
        </div>
        <div id="wide_nav">
            <ol>
                <li>
                    <a href="#">A propos</a>
                </li>
                <li>
                    <a href="#">Compétences</a>
                </li>
                <li>
                    <a href="#">Projets</a>
                </li>
                <li>
                    <a href="#">Contact</a>
                </li>
            </ol>
            <div class="button_hollow cv-button">
                <a href="#">Mon CV</a>
            </div>
        </div>
        <button id="burger_nav" v-on:click="toggleOverlayNavigation">
            <div></div>
            <div></div>
            <div></div>
        </button>
    </nav>

    <nav id="nav_overlay">
        <div id="gaussian_blur">
        </div>
        <div id="overlay_menu">
            <ol>
                <li>
                    <a href="#">A propos</a>
                </li>
                <li>
                    <a href="#">Compétences</a>
                </li>
                <li>
                    <a href="#">Projets</a>
                </li>
                <li>
                    <a href="#">Contact</a>
                </li>
            </ol>
            <div class="button_hollow cv-button">
                <a href="#">Mon CV</a>
            </div>
        </div>
    </nav>
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

        showNavBar() {
            let nav_bar = document.getElementById("nav_bar");
            if (nav_bar.classList.contains("hidden")) nav_bar.classList.remove("hidden");
        },

        toggleOverlayNavigation() {
            let navOverlay = document.getElementById("nav_overlay");
            navOverlay.classList.toggle("reveal");
            //let gaussianBlur = document.getElementById("gaussian_blur");
            //gaussianBlur.classList.toggle("reveal");

            let burger = document.getElementById("burger_nav");
            burger.classList.toggle("checked");
        },

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

    #nav_overlay {
        position: fixed;
        visibility: hidden;
        z-index: 11;
        width: 100%;
        height: 100%;

        &.reveal {
            visibility: visible;

            #gaussian_blur {
                opacity: 1;
            }

            #overlay_menu {
                transform: translateX(0);
            }
        }
    }

    .cv-button {
        margin-left: 25px;
        a {
            margin: 5px 30px;
        }
    }

    .logo {
        height: 50px;
        width: 50px;
        margin-top: auto;
        margin-bottom: auto;
        border: 2px var(--primary-color) solid;
        border-radius: 25px;
    }

    #wide_nav {
        display: none;
        align-items: center;
        flex-direction: row;

        ol {
            display: flex;
            flex-direction: row;
            margin: 0px;
        }

        li {
            display: flex;
            margin-right: clamp(0.6em, 2vw, 2.5em);
            counter-increment: nav-link;

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

    #burger_nav {
        display: flex;
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

    #gaussian_blur {
        position: fixed;
        z-index: 9;
        width: 100%;
        height: 100%;
        backdrop-filter: blur(10px);
        transition: 0.25s;
        opacity: 0;
    }

    #overlay_menu {
        position: fixed;
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        right: 0;
        width: 30em;
        height: 100%;
        background-color: var(--highlight-color);
        z-index: 10;
        transition: 0.25s;
        transform: translateX(30em);
    }

    @media (hover: hover) {
        #burger_nav {
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

    @media (min-width: 60em) {
        #wide_nav {
            display: flex;
        }

        #burger_nav {
            display: none;
        }

        #nav_overlay, #nav_overlay.reveal {
            display: none;
        }
    }
</style>