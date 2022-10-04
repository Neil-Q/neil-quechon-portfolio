<template>
    <div id="contact_form">
        <form action="null">

            <input type="text" id="name" class="shadow_boxed_light" name="name" placeholder="Votre nom">
            <input type="text" id="mail_adress" class="shadow_boxed_light" name="mail_adress" placeholder="Votre mail">

            <textarea id="message" class="shadow_boxed_light" name="message" placeholder="Ecrivez votre message..."></textarea>

            <input class="button_solid" id="submit_button" type="submit" value="Envoyer">
        </form>
        <div v-if="withText" id="coffee_text">
            <h4>Titre Lorem Ipsum</h4>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
            <p>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
            <div id="coffee_cup"></div>
        </div>
    </div>
</template>

<script>
export default {
    name: "ContactForm",
    props: {
        withText: {
            type: Boolean,
            default: false
        }
    }
}
</script>

<style lang="scss" scoped>
    #contact_form {
        display: flex;
        width: 100%;
        flex-direction: column-reverse;
        align-items: center;
        margin: 3em 0;
    }

    form {
        padding-top: 1em;
        width: 100%;
    }

    input, textarea {
        display: block;
        box-sizing: border-box;
        border: none;
        border-radius: 4px;
        font-family: var(--font-sans);
        font-size: 1em;
        margin-bottom: 1em;
        padding: 0em 1em;
        width: 100%;
        caret-color: var(--primary-color-soft);

        &:focus {
            outline: none;
            border: 2px solid var(--primary-color-soft);

            &::placeholder {
                opacity: 0;
            }
        }
    }

    input {
        min-height: 3em;
    }

    textarea {
        min-height: 15em;
        padding: 1em;
        resize: none;
    }

    #submit_button {
        width: auto;
        margin: auto;
        padding: 0 2em;
    }

    #coffee_text {
        text-align: left;
        padding-left: 2em;
        width: 100%;
    }

    #coffee_cup {
        width: 10em;
        height: 10em;
        background-color: grey;
        margin: auto;
    }

    @media(min-width: 40em) {
        #contact_form {
            flex-direction: row;
        }

        #coffee_text {
            border: none;
            min-width: 50%;
        }
    }
</style>