<script>
</script>

<template>
    <div id="body">
        <div id="second-frame">
            <p class="text-mask">Welcome!</p>
            <p>I'm Nabila Abubakar</p>
            <p>and I'm a Digital and Traditional Artist.</p>
            <br />
            <p>My personal website is available at:
                <a href="https://beela303.vercel.app/" target="_blank" rel="noopener noreferrer" class="button">
                    https://beela303.vercel.app/
                </a>
            </p>
            <div class="images">
                <img src="../assets/images/archer_in_the_forest.webp" alt="Archer in the forest">
                <img src="../assets/images/below_the_interspace_of_stars_and_clouds.webp"
                    alt="Below the interspace of stars and clouds">
                <img src="../assets/images/fashionista_in_a_museum_pink_frame_black_bg.webp"
                    alt="Fashionista in a museum">
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
p:first-child {
    font-size: 7rem;
}

p {
    font-size: 2.5rem;
    text-align: center;

    a {
        color: var(--pastel-color-2);
        
        &:hover {
            color: var(--pastel-color-1);
        }
    }
}

p:last-child {
    font-size: 1.5rem;
}

@media screen and (max-width: 1024px) {
    p:first-child {
        font-size: 5.5rem;
    }

    p {
        font-size: 2rem;
    }
}

@media screen and (max-width: 768px) {
    p:first-child {
        font-size: 4rem;
    }

    p {
        font-size: 2rem;
    }
}

@media screen and (max-width: 500px) {
    p:first-child {
        font-size: 3.5rem;
    }

    p {
        font-size: 1.5rem;
    }
}

@media screen and (max-width: 400px) {
    p:first-child {
        font-size: 3rem;
    }

    p {
        font-size: 1.7rem;
    }
}
</style>