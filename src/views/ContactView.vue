<script>
</script>

<template>
    <div id="body">
        <h1 class="text-mask">Get in Touch</h1>
        <div id="contact">
            <p>E-mail:</p>
            <a href="mailto:nabilaabubakar333@gmail.com" class="text-mask">nabilaabubakar333 <br> @gmail.com</a>

            <p>Socials:</p>
            <p class="text-mask"><a href="https://instagram.com/beela303" target="_blank"
                    rel="noopener noreferrer">Instagram</a></p>
            <p class="text-mask"><a href="https://x.com/beela303" target="_blank"
                    rel="noopener noreferrer">X/Twitter</a>
            </p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.text-mask {
    font-size: 10vh;
    text-align: center;
}

#contact {
    padding: 30px;
    font-size: 3rem;

    .text-mask {
        color: var(--pastel-color-1);
        text-align: left;
    }

    a {
        color: var(--pastel-color-1);

        &:hover {
            color: var(--pastel-color-2);
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

@media screen and (max-width: 350px) {
    #contact {
        font-size: 1.7rem;
    }
}
</style>