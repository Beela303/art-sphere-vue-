<script setup>
import { ref } from 'vue'

const is_expanded = ref(localStorage.getItem('is_expanded') === 'true')

const ToggleMenu = () => {
    is_expanded.value = !is_expanded.value

    localStorage.setItem('is_expanded', is_expanded.value)
}
</script>

<template>
    <aside :class="`${is_expanded && 'is-expanded'}`">
        <div class="logo">
            <!--<img src="../assets/logo.svg" alt="Logo" />-->
            <router-link to="/">
                <h1>A.S</h1>
            </router-link>
        </div>

        <div class="menu-toggle-wrap">
            <button class="menu-toggle" @click="ToggleMenu">
                <span class="material-icons">keyboard_double_arrow_right</span>
            </button>
        </div>

        <h3>Sphere</h3>
        <div class="menu">
            <router-link class="button" to="/">
                <span class="material-icons">home</span>
                <span class="text">Home</span>
            </router-link>
            <router-link class="button" to="/about">
                <span class="material-icons">visibility</span>
                <span class="text">About</span>
            </router-link>
            <router-link class="button" to="/gallery">
                <span class="material-icons">image</span>
                <span class="text">Gallery</span>
            </router-link>
            <router-link class="button" to="/contact">
                <span class="material-icons">account_circle</span>
                <span class="text">Contact</span>
            </router-link>
        </div>

        <div class="flex"></div>

        <div class="menu">
            <a href="https://beela303.vercel.app/" target="_blank" rel="noopener noreferrer" class="button">
                <span class="material-icons">copyright</span>
                <span class="text">Nabila Abubakar</span>
            </a>
        </div>
    </aside>
</template>

<style lang="scss" scoped>
body {
    margin-left: 0 !important;
}

aside {
    color: var(--light);
    background-color: var(--dark-color);

    width: calc(2rem + 32px);
    padding: 1rem;

    height: 100%;

    display: flex;
    flex-direction: column;

    transition: 0.2s ease-out;
    overflow: hidden;

    position: fixed;

    .flex {
        flex: 1 1 0;
    }

    .logo {
        margin-bottom: 1rem;

        h1 {
            color: #f3f3f3 !important;
        }

        img {
            width: 2rem;
        }
    }

    .menu-toggle-wrap {
        top: 0;
        margin-bottom: 1rem;

        position: relative;

        display: flex;
        justify-content: flex-end;

        transition: 0.2s ease-out;

        .menu-toggle {
            transition: 0.2s ease-out;

            .material-icons {
                color: var(--light);

                width: 2rem;

                transition: 0.2s ease-out;
            }

            &:hover {
                .material-icons {
                    color: var(--pastel-color-1);

                    transform: translateX(0.5rem);
                }
            }
        }
    }

    h3,
    .button .text {
        opacity: 0;

        transition: 0.3s ease-out;
    }

    h3 {
        color: var(--grey);

        margin-bottom: 0.5rem;

        font-size: 0.875rem;

        text-transform: uppercase;
    }

    .menu {
        margin: 0 -1rem;

        .button {
            padding: 0.5rem 1rem;

            display: flex;
            align-items: center;

            text-decoration: none;

            transition: 0.2s ease-out;

            .material-icons {
                color: var(--light);

                margin-right: 1rem;

                font-size: 2rem;

                transition: 0.2s ease-out;
            }

            .text {
                color: var(--light);

                transition: 0.2s ease-out;
            }

            &:hover,
            &.router-link-exact-active {
                background-color: var(--pastel-color-1);

                .material-icons,
                .text {
                    color: var(--dark-color);
                }
            }

            &.router-link-exact-active {
                border-right: 5px solid var(--dark-color);
            }
        }
    }

    &.is-expanded {
        width: var(--sidebar-width);

        .menu-toggle-wrap {
            top: -3rem;

            .menu-toggle {
                transform: rotate(-180deg);
            }
        }

        h3,
        .button .text {
            opacity: 1;
        }

        .button {
            .material-icons {
                margin-right: 1rem;
            }
        }
    }

    @media (max-width: 768px) {
        position: fixed;
        z-index: 99;
    }
}
</style>
