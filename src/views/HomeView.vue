<script>
</script>

<template>
    <div id="body">
        <div class="first-frame bg-dark">
            <h1 class="text-mask">ART SPHERE</h1>
        </div>

        <!--========================== ME =============================-->
        <div class="full">
            <section id="about-me">
                <h2>Multifaceted Artist with a background in Science</h2>

                <p>I believe everything can be ART and everything is ART.</p>
                <p>I use ART to capture memories, experiences, timelines and illusions,
                    <br>
                    using this art,
                    <br>
                    I write lines of poetry crafted to express this art,
                    <br>
                    I still use this art as an inspiration to code lovely websites and apps to tell stories
                    <br>
                    and also create beautiful and fashionable designs that expresses identities and personas.
                    <br>
                    My background as a Nurse also teaches me a lot about empathy and how everything can be shown.
                </p>
            </section>
        </div>

        <div class="fourth-frame bg-dark">
            <p class="text-mask">Digital & Traditional
                <br /> Artist
            </p>
            <p>I'm Nabila Abubakar</p>
            <p>and I specialize in semi-realistic traditional and digital Art.</p>
            <br />
            <p>Personal Website:
                <a href="https://beela303.vercel.app/" target="_blank" rel="noopener noreferrer" class="button">
                    https://beela303.vercel.app/
                </a>
            </p>
        </div>

        <div class="second-frame bg-dark">
            <div class="images">
                <img src="../assets/images/archer_in_the_forest.webp" alt="Archer in the forest">
                <img src="../assets/images/below_the_interspace_of_stars_and_clouds.webp"
                    alt="Below the interspace of stars and clouds">
                <!--<img src="../assets/mypicture.webp" alt="Below the interspace of stars and clouds">-->
                <img src="../assets/images/fashionista_in_a_museum_pink_frame_black_bg.webp"
                    alt="Fashionista in a museum">
            </div>
        </div>

        <!--<div class="second-frame text-mask">
            <h1>I am <span>Nabila</span></h1>
            <h2>And Welcome to my <span>Sphere</span></h2>

            <div class="images">
                <img src="../assets/images/galactic_ocean_of_dreams.webp" alt="Galactic ocean of dreams">
                <img src="../assets/images/brown_aesthetic.webp" alt="Brown aesthetic">
                <img src="../assets/images/calm_ambience.webp" alt="Calm ambience">
            </div>
        </div>-->

        <div class="third-frame">
            <p>Check Out More <span class="material-icons">arrow_forward_ios</span></p>

            <div class="buttons">
                <router-link to="/eduexp"><button class="button-main">Edu X Exp</button></router-link>
                <router-link to="/gallery"><button class="button-main">Gallery</button></router-link>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
.bg-dark {
    background-color: #222;
}

//FIRST FRAME/CONTENT
.first-frame {
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
.second-frame {
    //height: 100vh;

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

            //&:nth-child(2) {
            //rotate: 90deg;
            //}
        }
    }
}

//THIRD FRAME
.third-frame {
    color: transparent;

    //margin: 0;
    padding: 30px;

    font-weight: bold;

    justify-content: center;
    align-items: center;
    text-align: center;

    p {
        margin-bottom: 7vh;

        font-size: 5vw;
        font-weight: normal;

        -webkit-text-stroke: 2px white;

        span {
            font-size: 5vw;
        }
    }

    .buttons {
        //height: 30vh;

        display: flex;
        justify-content: center;

        .button-main {
            //color: #000 !important;
            -webkit-text-stroke: 1px gray;
            background: var(--pastel-color-2);

            //width: 15vw;
            //height: 15vh;
            width: 25vw;
            height: 8vw;

            margin: 50px;
            border-radius: 100px;

            font-size: 2vw;

            transition: 2s;

            &:hover {
                color: var(--pastel-color-2);
                background: transparent;

                border: 1px solid var(--pastel-color-2);
            }
        }
    }
}

// FOURTH FRAME
.fourth-frame {
    //height: 50vh;

    .text-mask {
        padding-top: 30px;
        font-size: 7vw !important;
    }

    p {
        font-size: 2rem;
        text-align: center;

        &:first-child {
            font-size: 7rem;
        }

        &:last-child {
            font-size: 1.5rem;
        }

        a {
            color: var(--pastel-color-2);

            &:hover {
                color: var(--pastel-color-1);
            }
        }
    }
}

#about-me {
    background-color: var(--dark-color);

    width: 50%;
    padding: 30px;

    margin: 0 25%;

    border-radius: 30px;
    border: 1px solid var(--pastel-color-2);

    text-align: center;

    h2 {
        color: var(--pastel-color-2);
        //font-size: 1.75rem;
    }

    p {
        font-size: 1.1rem;
    }
}

//RESPONSIVENESS
@media screen and (max-width: 1024px) {
    .fourth-frame {
        p {
            font-size: 2rem;

            &:first-child {
                font-size: 5.5rem;
            }
        }
    }
}

@media screen and (max-width: 768px) {
    .third-frame {
        p {
            font-size: 2rem;
        }

        .buttons {
            .button-main {
                width: 30vw;
                height: 12vw;

                margin: 30px;

                font-size: 1.7rem !important;
            }
        }
    }

    .fourth-frame {
        p {
            font-size: 2rem;

            &:first-child {
                font-size: 4rem;
            }
        }
    }

    #about-me {
        width: 70%;
        margin: 0 15%;
    }
}

@media screen and (max-width: 600px) {
    .second-frame {
        padding-top: 15vh;
        font-size: 3vh !important;

        .images {
            height: 50vh;
        }
    }

    /*#third-frame {
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
    }*/

    #about-me {
        width: 90%;
        margin: 2.5% 5%;
    }
}


@media screen and (max-width: 500px) {
    .fourth-frame {
        p {
            font-size: 1.5rem;

            &:first-child {
                font-size: 3.5rem;
            }
        }
    }
}

@media screen and (max-width: 400px) {
    .fourth-frame {
        p {
            font-size: 1.7rem;

            &:first-child {
                font-size: 3rem;
            }
        }
    }
}
</style>