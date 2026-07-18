<script>
export default {
    data() {
        return {
            showScrollButton: false,
        }
    },

    methods: {
        handleScroll() {
            this.showScrollButton = window.scrollY > 200;
        },

        scrollToTop() {
            //window.scrollTo(0, 0)
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            })
        },
    },

    mounted() {
        window.addEventListener('scroll', this.handleScroll);
    },

    beforeDestroy() {
        window.removeEventListener('scroll', this.handleScroll)
    },
}
</script>

<template>
    <button title="Scroll to Top" id="scroll-to-top" type="button" v-if="showScrollButton" @click="scrollToTop"><i
            class="fas fa-arrow-up-long"></i></button>
</template>

<style lang="scss">
#scroll-to-top {
    color: var(--white);
    background: rgba(255, 255, 255, .2);

    backdrop-filter: blur(10px);
    --webkit-backdrop-filter: blur(10px);

    border: 1px solid rgba(255, 255, 255, .3);
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);

    font-size: 40px;

    height: 65px;
    width: 65px;

    top: 80%;
    //top: 75%;
    right: 30px;

    border-radius: 50%;
    outline: none;

    position: fixed;
    z-index: 9999;

    cursor: pointer;

    transition: var(--transition);

    &:hover {
        border-radius: 20px;
    }
}
</style>