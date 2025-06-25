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
            <router-link to="/about"><button class="button-main">About</button></router-link>
            <router-link to="/gallery"><button class="button-main">Gallery</button></router-link>
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
            width: 30%;
            padding: 20px;
            border-radius: 30px;

            object-fit: cover;
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
        justify-content: center;

        .button-main {
            background: var(--main-color);

            width: 30vw;
            height: 30vh;

            margin: 50px;
            border-radius: 150px;

            font-size: 5vw;

            transition: 1s;

            &:hover {
                color: var(--main-color);
                background: transparent;
            }
        }
    }
}

//RESPONSIVENESS
@media screen and (max-width: 600px) {
    #second-frame {
        padding-top: 15vh;
        font-size: 3vh !important;

        .images {
            height: 50vh;
        }
    }

    #third-frame {
        p {
            padding: 20px;
            font-size: 7vw !important;

            span {
                font-size: 5vw;
            }
        }

        .buttons {
            height: 50vh;
            margin-top: 15vh;

            .button-main {
                width: 20vw;
                height: 30vh;

                border-radius: 100px;
            }
        }
    }
}
</style>