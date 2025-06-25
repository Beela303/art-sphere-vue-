<script>
</script>

<template>
    <div id="body">
        <h1 class="text-mask">Gallery</h1>
        <div id="gallery">
            <img src="../assets/images/amulet of avalor.jpg" alt="">
            <img src="../assets/images/archer in the forest.jpg" alt="">
            <img src="../assets/images/below the interspace of stars and clouds.jpg" alt="">
            <img src="../assets/images/below the ocean (2).jpg" alt="">
            <img src="../assets/images/brown aesthetic.jpg" alt="">
            <img src="../assets/images/calm ambience.jpg" alt="">
            <img src="../assets/images/Fashionista in a museum (blue frame, black bg).jpg" alt="">
            <img src="../assets/images/fashionista in a museum (blue frame, white bg).jpg" alt="">
            <img src="../assets/images/fashionista in a museum (pink frame, black bg).jpg" alt="">
            <img src="../assets/images/fashionista in a museum (pink frame, white bg).jpg" alt="">
            <img src="../assets/images/Fashionista in a museum (white bg).jpg" alt="">
            <img src="../assets/images/galactic ocean of dreams.jpg" alt="">
            <img src="../assets/images/hall of mirage (border).jpg" alt="">
            <img src="../assets/images/hall of mirage.jpg" alt="">
            <img src="../assets/images/the city's starry sky (day).jpg" alt="">
            <img src="../assets/images/the city's starry sky (night).jpg" alt="">
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
        width: 300px;
        margin: 2%;

        border-radius: 30px;
    }
}

@media screen and (max-width: 768px) {
    #gallery {
        columns: 3;

        img {
            width: 180px;
        }
    }
}
</style>