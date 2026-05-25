<script>
</script>

<template>
    <div id="body">
        <h1 class="text-mask">Get in Touch</h1>
        <div id="contact">
            <div id="contact-form">
                <form action="https://formsubmit.co/dc027401bb393a2c66cb207f9cccd3e2" method="POST">
                    <!--Honeypot-->
                    <input type="text" name="_honey" style="display:none" />

                    <!--Disable initial captcha-->
                    <input type="hidden" name="_captcha" value="false" />

                    <!--Custom response-->
                    <input type="hidden" name="_autoresponse"
                        value="Thank you for reaching out! I can't wait to work with you!!! You'll receive a reply soon :)" />

                    <!--Subject-->
                    <input type="hidden" name="_subject" value="New Submission!" />

                    <label for="name">Name: </label>
                    <br />
                    <input type="text" id="name" name="name" placeholder="Your Name" required>
                    <br />

                    <label for="name">Email: </label>
                    <br />
                    <input type="email" id="email" name="email" placeholder="Your Email" required>
                    <br />

                    <label for="description">Description:</label>
                    <br />
                    <textarea type="text" id="description" name="description" placeholder="I want..." rows="5" cols="40"
                        required></textarea>
                    <br />

                    <button type="submit">Submit</button>
                </form>
            </div>

            <!--<div id="others">
                <p>E-mail:</p>
                <a href="mailto:nabilaabubakar333@gmail.com" class="text-mask">nabilaabubakar333 <br> @gmail.com</a>
                
                <p>Socials:</p>
                <p class="text-mask"><a href="https://instagram.com/beela303" target="_blank"
                        rel="noopener noreferrer">Instagram</a></p>
                <p class="text-mask"><a href="https://x.com/beela303" target="_blank"
                        rel="noopener noreferrer">X/Twitter</a>
                </p>
            </div>-->

            <div id="footer">
                <ul id="footer-socials">
                    <li><a href="https://www.linkedin.com/in/nabilaabubakar" target="_blank" rel="noopener noreferrer"
                            title="Linked-In"><i class="fa-brands fa-linkedin-in"></i></a></li>
                    <li><a href="https://www.instagram.com/beela303" target="_blank" rel="noopener noreferrer"
                            title="Instagram"><i class="fa-brands fa-instagram"></i></a></li>
                    <li><a href="https://www.twitter.com/beela303" target="_blank" rel="noopener noreferrer"
                            title="Twitter"><i class="fa-brands fa-twitter"></i></a></li>
                    <li><router-link to="/podcast" title="Podcast"><i class="fas fa-podcast"></i></router-link></li>
                    <li><a href="https://www.youtube.com/@beela303" target="_blank" rel="noopener noreferrer"
                            title="YouTube"><i class="fa-brands fa-youtube"></i></a></li>
                    <li><a href="https://www.tiktok/beela303" target="_blank" rel="noopener noreferrer"
                            title="TikTok"><i class="fa-brands fa-tiktok"></i></a></li>
                    <li><a href="https://www.pinterest.com/beela303" target="_blank" rel="noopener noreferrer"
                            title="Pinterest"><i class="fa-brands fa-pinterest"></i></a></li>
                    <li><a href="mailto:nabilaabubakar333@gmail.com" title="E-mail"><i class="fas fa-envelope"></i></a>
                    </li>
                </ul>

            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
#body {
    margin-left: 0 !important;
    margin-right: 0 !important;
}

.text-mask {
    font-size: 10vh;
    text-align: center;
}

#contact {
    padding: 30px;
    font-size: 1.5rem;

    .text-mask {
        color: var(--pastel-color-1);
        text-align: left;
    }

    #contact-form {
        justify-content: center !important;
        display: grid;

        form {
            width: 50vw;
            padding: 25px;

            margin: 25px;
            margin-bottom: 12vh;

            border: 1px dashed var(--text-color);
            border-radius: 30px;

            label {
                font-size: 1.2rem;
            }

            input {
                width: 100%;
                height: 40px;

                margin: 10px;
                border-radius: 25px;
            }

            textarea {
                width: 100%;
                margin: 10px;
                border-radius: 25px;

                resize: vertical;
            }

            button {
                color: var(--grey);
                background: var(--pastel-color-2);
                border: 1px solid var(--pastel-color-2);

                width: 50%;
                height: 8vh;

                margin-left: 25%;
                border-radius: 30px;

                font-size: 1.5rem;

                transition: 2s;

                &:hover {
                    color: var(--text-color);
                    background: var(--grey);
                    border: 1px solid var(--grey);
                }
            }
        }
    }

    a {
        color: var(--pastel-color-1);

        &:hover {
            color: var(--pastel-color-2);
        }
    }

    #footer {
        justify-content: center;
        text-align: center;
        align-items: center;

        ul {
            display: flex;
            justify-content: space-evenly;

            li {
                color: var(--text-color);
                font-size: 2rem;

                transition: 2s;

                &:hover {
                    color: var(--pastel-color-1);
                }

                a {
                    color: var(--text-color);

                    &:hover {
                        color: var(--pastel-color-1);
                    }
                }
            }
        }

        p {
            color: var(--text-color);

            padding-top: 20px;

            font-size: 20px;
            text-align: center;
        }
    }
}

@media screen and (max-width: 768px) {
    .text-mask {
        margin-left: calc(2rem + 25px) !important;
    }

    #contact-form {
        width: 100%;
        display: block;

        form {
            width: 100% !important;
            margin: 0;
            padding: 0;
            margin-bottom: 7vh;

            label {
                font-size: 1.3rem;
            }

            input {
                height: 35px;
            }
        }
    }

    #footer {
        margin-left: calc(2rem + 32px) !important;

        ul {
            display: grid !important;
            grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
        }
    }
}

@media screen and (max-width: 800px) {
    .text-mask {
        font-size: 5vh;
        -webkit-text-stroke: .5px white;
    }

    #contact {
        font-size: 2rem;
    }
}


@media screen and (max-width: 600px) {
    #contact-form {
        form {
            width: 90% !important;
            margin-left: 5% !important;
            margin-bottom: 5vh;
        }
    }
}

@media screen and (max-width: 500px) {
    #contact-form {
        form {
            width: 85% !important;
            margin-left: 13% !important;
        }
    }

    #footer {
        ul {
            display: grid !important;
            grid-template-columns: 1fr 1fr 1fr;
        }
    }
}

@media screen and (min-width: 200px) and (max-width: 500px) {
    #footer p {
        font-size: 20px;
    }
}

@media screen and (max-width: 425px) {
    #footer p {
        font-size: 23px;
        margin-left: 20%;
        margin-right: 20%;
    }
}

@media screen and (max-width: 400px) {
    #contact-form {
        form {
            button {
                width: 50%;
                height: 7vh;

                font-size: 1.3rem;
            }
        }
    }

    #footer ul {
        font-size: 25px;
    }
}

@media screen and (max-width: 350px) {
    #contact {
        font-size: 1.5rem;
    }
}
</style>