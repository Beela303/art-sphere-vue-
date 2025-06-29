<script>
</script>

<template>
    <div id="body">
        <div id="second-frame">
            <p class="text-mask">Welcome!</p>
            <p>I'm Nabila Abubakar</p> <br>
            <p>and I'm an Artist with over four years of experience making digital art.</p>
            <div class="images">
                <img src="../assets/images/archer in the forest.jpg" alt="Archer in the forest">
                <img src="../assets/images/below the interspace of stars and clouds.jpg"
                    alt="Below the interspace of stars and clouds">
                <img src="../assets/images/fashionista in a museum (pink frame, black bg).jpg"
                    alt="Fashionista in a museum">
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
p:first-child {
    font-size: 8rem;
}

p {
    font-size: 3.5rem;
    text-align: center;
}

@media screen and (max-width: 1024px) {
    p:first-child {
        font-size: 6.5rem;
    }

    p {
        font-size: 4rem;
    }
}

@media screen and (max-width: 768px) {
    p:first-child {
        font-size: 5rem;
    }

    p {
        font-size: 3rem;
    }
}

@media screen and (max-width: 500px) {
    p:first-child {
        font-size: 3.5rem;
    }

    p {
        font-size: 2.5rem;
    }
}

@media screen and (max-width: 400px) {
    p:first-child {
        font-size: 3rem;
    }

    p {
        font-size: 2.7rem;
    }
}
</style>