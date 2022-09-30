<template>
    <nav>
        <div class="logo">
            <a href="#" id="logo"></a>
        </div>
        <div class="nav-links">
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
            <div class="button_type_1 cv-button">
                <a href="#">Mon CV</a>
            </div>
        </div>
    </nav>
</template>

<script>
export default {
    name: "NavbarHomepage"
}
</script>

<style lang="scss">
    nav {
        display: flex;
        position: relative;
        z-index: 12;
        box-sizing: border-box;
        flex-direction: row;
        justify-content: space-between;
        width: 100%;
        padding: 0px 50px;
        height: var(--navbar-height);
        align-items: center;
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

    .nav-links {
        display: flex;
        align-items: center;
        flex-direction: row;

        ol {
            display: flex;
            flex-direction: row;
            margin: 0px;
        }

        li {
            display: flex;
            margin: 0px 20px;
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

    @media (max-width: 60em) {
        nav {
            display: none;
        }
    }
</style>