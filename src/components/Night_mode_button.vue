<template>
    <button class="dark_mode_button" v-on:click="toggleDarkMode()">
        <svg id="sun" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M12 3v2.25m6.364.386l-1.591 1.591M21 12h-2.25m-.386 6.364l-1.591-1.591M12 18.75V21m-4.773-4.227l-1.591 1.591M5.25 12H3m4.227-4.773L5.636 5.636M15.75 12a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0z" />
        </svg>
        <svg id="moon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M21.752 15.002A9.718 9.718 0 0118 15.75c-5.385 0-9.75-4.365-9.75-9.75 0-1.33.266-2.597.748-3.752A9.753 9.753 0 003 11.25C3 16.635 7.365 21 12.75 21a9.753 9.753 0 009.002-5.998z" />
        </svg>
        <div id="mode_mask"></div>
    </button>
</template>

<script>
export default {
    name: "NightModeButton",
    methods : {
        toggleDarkMode() {
            let body = document.querySelector("body");
            body.classList.toggle("dark_mode");

            let darkModeButtons = document.querySelectorAll(".dark_mode_button");
            darkModeButtons.forEach(button => {
                button.classList.toggle("darkMode");
            });
        }
    }
}
</script>

<style lang="scss" scoped>
    .dark_mode_button {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        height: 120px;
        width: 46px;
        padding: 8px 0;
        border: none;
        outline: 2px solid var(--primary-color);
        border-radius: 25px;
        color: var(--primary-color);
        background-color: var(--highlight-color);

        svg {
            height: 35px;
            width: 35px;
            transition: 0.25s;
        }

        #mode_mask {
            position: absolute;
            top: 0px;
            left: 3px;
            width: 40px;
            height: 40px;
            background-color: var(--contrast-color);
            border-radius: 20px;
            transition: 0.5s;
            transform: translateY(3px);
        }

        &.darkMode{

            #mode_mask {
                transform: translateY(77px);
            }
        }
    }
</style>