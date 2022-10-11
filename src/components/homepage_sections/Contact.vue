<template>
    <section id="contact">
        <h3><span class="text_colorized">04. </span>CONTACTEZ MOI</h3>
        <ContactForm :withText="true"/>
    </section>
</template>

<script>
import ContactForm  from "@/components/Contact_form.vue";

export default {
    name: "HomepageContact",
    components: {
        ContactForm
    }
}
</script>

<style lang="scss">
    #contact {
        display: flex;
        flex-direction: column;
        justify-content: center;
        min-height: calc(100vh - var(--footer-height));
    }
</style>