<script>
</script>

<template>
    <div id="first-frame">
        <h1 class="text-mask">ART SPHERE</h1>
    </div>

    <div id="second-frame" class="text-mask">
        <h1>I am <span>Nabila</span></h1>
        <h2>And Welcome to my <span>Sphere</span></h2>

        <div class="images">
            <img src="../assets/images/galactic ocean of dreams.jpg" alt="">
            <img src="../assets/images/brown aesthetic.jpg" alt="">
            <img src="../assets/images/calm ambience.jpg" alt="">
        </div>
    </div>

    <div id="third-frame" class="text-mask">
        <p>Check Out More <span class="material-icons">arrow_forward_ios</span></p>

        <div class="buttons">
            <button class="button-main">About</button>
            <button class="button-main">Gallery</button>
        </div>
    </div>
</template>

<style lang="scss">
//FIRST FRAME/CONTENT
#first-frame {
    background-color: #000;

    margin: 0;
    height: 100vh;

    display: flex;

    align-items: center;
    text-align: center;

    .text-mask {
        font-size: 20vw;
    }
}

.text-mask {
    color: transparent;

    font-size: 20vw;
    font-weight: bold;

    -webkit-text-stroke: 2px white;
}

//SECOND FRAME
#second-frame {
    height: 100vh;

    font-size: 5vh !important;

    text-align: center;
    justify-content: center;
    align-items: center;

    h1 {
        span {
            color: var(--pastel-color-2);
        }
    }

    h2 {

        span {
            color: var(--pastel-color-2);
        }
    }

    .images {
        height: 70vh;

        display: flex;
        justify-content: center;
        align-self: center;

        img {
            width: 60vh;
            padding: 20px;
            border-radius: 30px;
        }
    }
}

//THIRD FRAME
#third-frame {
    background-color: #000;

    margin: 0;
    height: 100vh;

    padding: 30px;

    justify-content: center;
    align-items: center;
    text-align: center;

    p {
        font-size: 10vw !important;

        span {
            font-size: 7vw;
        }
    }

    .buttons {
        height: 70vh;

        display: flex;

        .button-main {
            width: 70vh;
            margin: 150px;
            font-size: 5vw;

            border-radius: 30px;

            background: var(--main-color);

            transition: 1s;

            &:hover {
                color: var(--main-color);
                background: transparent;

                width: 50vh;
                border-radius: 50px;
            }
        }
    }
}
</style>