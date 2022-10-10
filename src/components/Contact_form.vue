<template>
    <div id="contact_form">
        <form action="null">

            <input type="text" id="name" class="shadow_boxed_light" name="name" placeholder="Votre nom">
            <input type="text" id="mail_adress" class="shadow_boxed_light" name="mail_adress" placeholder="Votre mail">

            <textarea id="message" class="shadow_boxed_light" name="message" placeholder="Ecrivez votre message..."></textarea>

            <input class="button_solid" id="submit_button" type="submit" value="Envoyer">
        </form>
        <div v-if="withText" id="coffee_text">
            <h4>Si vous avez des questions sur moi ou mes projets...</h4>
            <p>Je suis disponible pour prendre un café et discuter ! Envoyez-moi un commentaire, une question ou une préoccupation, et merci de votre visite !</p>
            <p>NEIL.QUECHON@GMAIL.COM</p>
            <div id="coffee_cup">
                <svg version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 511 511" xmlns:xlink="http://www.w3.org/1999/xlink" enable-background="new 0 0 511 511">
                    <g fill="currentColor">
                        <path d="m399.5,192h-32c-5.647,0-11.161,0.742-16.5,2.177v-34.677c0-8.547-6.953-15.5-15.5-15.5h-272c-8.547,0-15.5,6.953-15.5,15.5v280c0,19.43 14.106,35.617 32.613,38.887 3.27,18.506 19.457,32.613 38.887,32.613h160c19.43,0 35.617-14.107 38.887-32.613 18.507-3.27 32.613-19.457 32.613-38.887v-26.678c5.339,1.436 10.854,2.178 16.5,2.178h32c35.014,0 63.5-28.486 63.5-63.5v-96c0-35.014-28.486-63.5-63.5-63.5zm-48.5,63.5c0-9.098 7.402-16.5 16.5-16.5h32c9.098,0 16.5,7.402 16.5,16.5v96c0,9.098-7.402,16.5-16.5,16.5h-32c-9.098,0-16.5-7.402-16.5-16.5v-96zm-71.5,240.5h-160c-10.894,0-20.146-7.149-23.321-17h206.643c-3.176,9.851-12.428,17-23.322,17zm56.5-56.5c0,13.509-10.991,24.5-24.5,24.5h-224c-13.509,0-24.5-10.991-24.5-24.5v-280c0-0.276 0.224-0.5 0.5-0.5h272c0.276,0 0.5,0.224 0.5,0.5v280zm112-88c0,26.743-21.757,48.5-48.5,48.5h-32c-5.707,0-11.235-0.98-16.5-2.89v-18.792c4.802,2.965 10.454,4.681 16.5,4.681h32c17.369,0 31.5-14.131 31.5-31.5v-96c0-17.369-14.131-31.5-31.5-31.5h-32c-6.046,0-11.698,1.716-16.5,4.681v-18.792c5.264-1.91 10.792-2.889 16.5-2.889h32c26.743,0 48.5,21.757 48.5,48.5v96.001z"/>
                        <path d="m184,119.5c0,4.142 3.358,7.5 7.5,7.5s7.5-3.358 7.5-7.5c0-6.554 2.464-9.427 6.193-13.776 4.369-5.095 9.807-11.436 9.807-23.541 0-12.109-5.437-18.454-9.805-23.551-3.73-4.353-6.195-7.229-6.195-13.791s2.464-9.438 6.195-13.791c4.368-5.096 9.805-11.441 9.805-23.55 0-4.142-3.358-7.5-7.5-7.5s-7.5,3.358-7.5,7.5c0,6.562-2.464,9.438-6.195,13.791-4.368,5.097-9.805,11.441-9.805,23.551s5.437,18.454 9.805,23.551c3.73,4.353 6.195,7.229 6.195,13.791 0,6.554-2.464,9.427-6.193,13.776-4.369,5.095-9.807,11.436-9.807,23.54z"/>
                        <path d="m224,119.5c0,4.142 3.358,7.5 7.5,7.5s7.5-3.358 7.5-7.5c0-6.554 2.464-9.427 6.193-13.776 4.369-5.095 9.807-11.436 9.807-23.541 0-12.109-5.437-18.454-9.805-23.551-3.73-4.353-6.195-7.229-6.195-13.791 0-4.142-3.358-7.5-7.5-7.5s-7.5,3.358-7.5,7.5c0,12.109 5.437,18.454 9.805,23.551 3.73,4.353 6.195,7.229 6.195,13.791 0,6.554-2.464,9.427-6.193,13.776-4.369,5.096-9.807,11.437-9.807,23.541z"/>
                        <path d="m144,119.5c0,4.142 3.358,7.5 7.5,7.5s7.5-3.358 7.5-7.5c0-6.554 2.464-9.427 6.193-13.776 4.369-5.095 9.807-11.436 9.807-23.541 0-12.109-5.437-18.454-9.805-23.551-3.73-4.353-6.195-7.229-6.195-13.791 0-4.142-3.358-7.5-7.5-7.5s-7.5,3.358-7.5,7.5c0,12.109 5.437,18.454 9.805,23.551 3.73,4.353 6.195,7.229 6.195,13.791 0,6.554-2.464,9.427-6.193,13.776-4.369,5.096-9.807,11.437-9.807,23.541z"/>
                        <path d="m311.5,176c-4.142,0-7.5,3.358-7.5,7.5v24c0,4.142 3.358,7.5 7.5,7.5s7.5-3.358 7.5-7.5v-24c0-4.142-3.358-7.5-7.5-7.5z"/>
                        <path d="m311.5,232c-4.142,0-7.5,3.358-7.5,7.5v120c0,4.142 3.358,7.5 7.5,7.5s7.5-3.358 7.5-7.5v-120c0-4.142-3.358-7.5-7.5-7.5z"/>
                    </g>
                </svg>
            </div>
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
        flex-direction: column;
        margin-bottom: 3em;
        gap: 2em;
    }

    form {
        display: flex;
        flex-direction: column;
        width: 100%;

        #message {
            flex-grow: 1;
        }
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
        box-sizing: border-box;
        width: 100%;

        h4 {
            font-size: var(--font-sz-lg);
        }
    }

    #coffee_cup {
        width: 8em;
        //background-color: grey;
        margin: auto;
        //color: var(--primary-color);
        color: var(--contrast-color-soft);
    }

    @media(min-width: 40em) {
        #contact_form {
            flex-direction: row;
        }

        #coffee_text {
            border: none;
            min-width: 50%;
            text-align: left;
            font-size: var(--font-sz-lg);

            h4 {
                margin-top: 0;
                font-size: var(--font-sz-lg);
            }
        }
    }

    @media(min-width: 60em) {
        #coffee_text {
            font-size: var(--font-sz-xl);

            h4 {
                font-size: var(--font-sz-xl);
            }
        }
    }
</style>