<script>
</script>

<template>
    <div id="body">
        <h1 class="text-mask">Gallery</h1>
        <div id="gallery">
            <img src="../assets/images/amulet of avalor.jpg" alt="Amulet of avalor">
            <img src="../assets/images/archer in the forest.jpg" alt="Archer in the forest">
            <img src="../assets/images/below the interspace of stars and clouds.jpg"
                alt="Below the interspace of stars and clouds">
            <img src="../assets/images/below the ocean (2).jpg" alt="Below the ocean">
            <img src="../assets/images/brown aesthetic.jpg" alt="Brown aesthetic">
            <img src="../assets/images/calm ambience.jpg" alt="Calm ambience">
            <img src="../assets/images/Fashionista in a museum (blue frame, black bg).jpg"
                alt="Fashionista in a museum (blue frame, black bg)">
            <img src="../assets/images/fashionista in a museum (blue frame, white bg).jpg"
                alt="fashionista in a museum (blue frame, white bg)">
            <img src="../assets/images/fashionista in a museum (pink frame, black bg).jpg"
                alt="fashionista in a museum (pink frame, black bg)">
            <img src="../assets/images/fashionista in a museum (pink frame, white bg).jpg"
                alt="fashionista in a museum (pink frame, white bg)">
            <img src="../assets/images/Fashionista in a museum (white bg).jpg" alt="Fashionista in a museum (white bg)">
            <img src="../assets/images/galactic ocean of dreams.jpg" alt="Galactic ocean of dreams">
            <img src="../assets/images/hall of mirage (border).jpg" alt="Hall of mirage (border)">
            <img src="../assets/images/hall of mirage.jpg" alt="Hall of mirage">
            <img src="../assets/images/the city starry sky (day).jpg" alt="The city's starry sky (day)">
            <img src="../assets/images/the city starry sky (night).jpg" alt="The city's starry sky (night)">
        </div>
    </div>
</template>

<style lang="scss" scoped>
h1:first-child {
    font-size: 15vh;
    text-align: center;
}

#gallery {
    columns: 4;

    img {
        width: 100%;
        margin: 2%;

        border-radius: 30px;
    }
}

@media screen and (max-width: 1024px) {
    h1:first-child {
        font-size: 10vh;
    }

    #gallery {
        columns: 3;

    }
}

@media screen and (max-width: 768px) {
    h1:first-child {
        font-size: 7vh;
    }

}

@media screen and (max-width: 660px) {}

@media screen and (max-width: 500px) {
    #gallery {
        columns: 2;

    }
}
</style>