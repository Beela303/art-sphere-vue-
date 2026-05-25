<script>
</script>

<template>
    <div id="body">
        <h1 class="text-mask">Gallery</h1>
        <div id="gallery">
            <img src="../assets/images/amulet of avalor.webp" alt="Amulet of avalor">
            <img src="../assets/images/archer in the forest.webp" alt="Archer in the forest">
            <img src="../assets/images/below the interspace of stars and clouds.webp"
                alt="Below the interspace of stars and clouds">
            <img src="../assets/images/below the ocean (2).webp" alt="Below the ocean">
            <img src="../assets/images/trad 05.webp" alt="Traditional Art">
            <img src="../assets/images/Into the illusion of the mirror.webp" alt="Digital Art">
            <img src="../assets/images/Seeking through the abyss.webp" alt="Digital Art">
            <img src="../assets/images/brown aesthetic.webp" alt="Brown aesthetic">
            <img src="../assets/images/calm ambience.webp" alt="Calm ambience">
            <img src="../assets/images/Fashionista in a museum (blue frame, black bg).webp"
                alt="Fashionista in a museum (blue frame, black bg)">
            <img src="../assets/images/fashionista in a museum (blue frame, white bg).webp"
                alt="fashionista in a museum (blue frame, white bg)">
            <img src="../assets/images/fashionista in a museum (pink frame, black bg).webp"
                alt="fashionista in a museum (pink frame, black bg)">
            <img src="../assets/images/galactic ocean of dreams.webp" alt="Galactic ocean of dreams">
            <img src="../assets/images/trad 09.webp" alt="Traditional Art">
            <img src="../assets/images/hall of mirage (border).webp" alt="Hall of mirage (border)">
            <img src="../assets/images/hall of mirage.webp" alt="Hall of mirage">
            <img src="../assets/images/Fashionista in a museum (white bg).webp"
                alt="Fashionista in a museum (white bg)">
            <img src="../assets/images/trad 12.webp" alt="Traditional Art">
            <img src="../assets/images/the city starry sky (day).webp" alt="The city's starry sky (day)">
            <img src="../assets/images/the city starry sky (night).webp" alt="The city's starry sky (night)">
            <img src="../assets/images/trad 06.webp" alt="Traditional Art">
            <img src="../assets/images/fashionista in a museum (pink frame, white bg).webp"
                alt="fashionista in a museum (pink frame, white bg)">
            <img src="../assets/images/trad 07.webp" alt="Traditional Art">
            <img src="../assets/images/trad 08.webp" alt="Traditional Art">
            <img src="../assets/images/trad 10.webp" alt="Traditional Art">
            <img src="../assets/images/trad 11.webp" alt="Traditional Art">
            <img src="../assets/images/trad 13.webp" alt="Traditional Art">
            <img src="../assets/images/trad 14.webp" alt="Traditional Art">
            <img src="../assets/images/trad 15.webp" alt="Traditional Art">
            <img src="../assets/images/trad 16.webp" alt="Traditional Art">
            <img src="../assets/images/trad 17.webp" alt="Traditional Art">
            <img src="../assets/images/trad 18.webp" alt="Traditional Art">
            <img src="../assets/images/trad 19.webp" alt="Traditional Art">
            <img src="../assets/images/trad 20.webp" alt="Traditional Art">
            <img src="../assets/images/trad 21.webp" alt="Traditional Art">
            <img src="../assets/images/trad 22.webp" alt="Traditional Art">
            <img src="../assets/images/trad 23.webp" alt="Traditional Art">
            <img src="../assets/images/trad 24.webp" alt="Traditional Art">
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