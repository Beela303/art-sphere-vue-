<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue';

// Reactive state
const selectedCategory = ref('All');
const searchQuery = ref('');
const activePhoto = ref(null);
const categoriesTab = ref(false)

const photos = ref([
    {
        id: 1,
        type: 'image',
        url: new URL('../assets/images/phone_on_a_desk.webp', import.meta.url).href,
        categories: ['Digital Art', 'Still Life'],
        title: 'Phone on a Desk'
    },
    {
        id: 2,
        type: 'image',
        url: new URL('../assets/images/silver_haired_lady_without_stars.webp', import.meta.url).href,
        categories: ['Digital Art', 'Portrait', 'Multiple Versions', 'Woman'],
        title: 'Silver haired lady without stars'
    },
    {
        id: 3,
        type: 'image',
        url: new URL('../assets/images/silver_haired_lady_with_stars.webp', import.meta.url).href,
        categories: ['Digital Art', 'Portrait', 'Multiple Versions', 'Woman'],
        title: 'Silver haired lady with stars'
    },
    {
        id: 4,
        type: 'image',
        url: new URL('../assets/images/fashionista_in_a_museum_pink_frame_black_bg.webp', import.meta.url).href,
        categories: ['Digital Art', 'Portrait', 'Multiple Versions', 'Woman'],
        title: 'Fashionista in a museum (Pink frame, Black BG)'
    },
    {
        id: 5,
        type: 'image',
        url: new URL('../assets/images/fashionista_in_a_museum_pink_frame_white_bg.webp', import.meta.url).href,
        categories: ['Digital Art', 'Portrait', 'Multiple Versions'],
        title: 'Fashionista in a museum (Pink frame, White BG)'
    },
    {
        id: 6,
        type: 'image',
        url: new URL('../assets/images/fashionista_in_a_museum_blue_frame_black_bg.webp', import.meta.url).href,
        categories: ['Digital Art', 'Portrait', 'Multiple Versions', 'Woman'],
        title: 'Fashionista in a museum (Blue frame, Black BG)'
    },
    {
        id: 7,
        type: 'image',
        url: new URL('../assets/images/fashionista_in_a_museum_blue_frame_white_bg.webp', import.meta.url).href,
        categories: ['Digital Art', 'Portrait', 'Multiple Versions', 'Woman'],
        title: 'Fashionista in a museum (Blue frame, White BG)'
    },
    {
        id: 8,
        type: 'image',
        url: new URL('../assets/images/fashionista_in_a_museum_white_bg.webp', import.meta.url).href,
        categories: ['Digital Art', 'Portrait', 'Multiple Versions', 'Woman'],
        title: 'Fashionista in a museum (White BG)'
    },
    {
        id: 9,
        type: 'image',
        url: new URL('../assets/images/brown_aesthetic.webp', import.meta.url).href,
        categories: ['Digital Art', 'Portrait', 'Woman'],
        title: 'Brown Aesthetic'
    },
    /*{
        id: 10,
        type: 'image',
        url: new URL('../assets/images/Into_the_illusion_of_the_mirror.webp', import.meta.url).href,
        categories: ['Digital Art', 'Fantasy', 'Underwater', 'Woman'],
        title: 'Into the illusion of the mirror'
    },*/
    {
        id: 11,
        type: 'image',
        url: new URL('../assets/images/seeking_through_the_abyss.webp', import.meta.url).href,
        categories: ['Digital Art', 'Fantasy', 'Woman'],
        title: 'Seeking through the abyss'
    },
    {
        id: 12,
        type: 'image',
        url: new URL('../assets/images/below_the_ocean_1.webp', import.meta.url).href,
        categories: ['Digital Art', 'Underwater'],
        title: 'Below the ocean'
    },
    {
        id: 13,
        type: 'image',
        url: new URL('../assets/images/archer_in_the_forest.webp', import.meta.url).href,
        categories: ['Digital Art', 'Forest', 'Nature', 'Woman'],
        title: 'Archer in the forest'
    },
    /*{
        id: 14,
        type: 'image',
        url: new URL('../assets/images/into_the_illusion_of_the_mirror.webp', import.meta.url).href,
        categories: ['Digital Art', 'Fantasy', 'Woman', 'Light'],
        title: 'Into the illusion of the mirror'
    },*/
    {
        id: 15,
        type: 'image',
        url: new URL('../assets/images/below_the_interspace_of_stars_and_clouds.webp', import.meta.url).href,
        categories: ['Digital Art', 'Abstract', 'Space'],
        title: 'Below the interspace of stars and clouds'
    },
    {
        id: 16,
        type: 'image',
        url: new URL('../assets/images/calm_ambience.webp', import.meta.url).href,
        categories: ['Digital Art', 'Still Life'],
        title: 'Calm ambience'
    },
    {
        id: 17,
        type: 'image',
        url: new URL('../assets/images/galactic_ocean_of_dreams.webp', import.meta.url).href,
        categories: ['Digital Art', 'Underwater', 'Flowers', 'Sky'],
        title: 'Galactic ocean of dreams'
    },
    {
        id: 18,
        type: 'image',
        url: new URL('../assets/images/hall_of_mirage_border.webp', import.meta.url).href,
        categories: ['Digital Art', 'Abstract', 'Multiple Versions'],
        title: 'Hall of mirage (border)'
    },
    {
        id: 19,
        type: 'image',
        url: new URL('../assets/images/hall_of_mirage.webp', import.meta.url).href,
        categories: ['Digital Art', 'Abstract', 'Multiple Versions'],
        title: 'Hall of mirage'
    },
    {
        id: 20,
        type: 'image',
        url: new URL('../assets/images/the_city_starry_sky_night.webp', import.meta.url).href,
        categories: ['Digital Art', 'Architecture', 'Night', 'Multiple Versions'],
        title: "The city's starry sky (night)"
    },
    {
        id: 21,
        type: 'image',
        url: new URL('../assets/images/the_city_starry_sky_day.webp', import.meta.url).href,
        categories: ['Digital Art', 'Architecture', 'Day', 'Multiple Versions'],
        title: "The city's starry sky (day)"
    },
    {
        id: 22,
        type: 'image',
        url: new URL('../assets/images/lady_in_an_illusion_1.webp', import.meta.url).href,
        categories: ['Digital Art', 'Fantasy', 'Multiple Versions', 'Woman'],
        title: 'Lady in an illusion 1'
    },
    {
        id: 23,
        type: 'image',
        url: new URL('../assets/images/lady_in_an_illusion_2.webp', import.meta.url).href,
        categories: ['Digital Art', 'Fantasy', 'Multiple Versions', 'Woman'],
        title: 'Lady in an illusion 2'
    },
    {
        id: 24,
        type: 'image',
        url: new URL('../assets/images/trad_05.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 25,
        type: 'image',
        url: new URL('../assets/images/trad_06.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 26,
        type: 'image',
        url: new URL('../assets/images/trad_07.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 27,
        type: 'image',
        url: new URL('../assets/images/trad_08.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 28,
        type: 'image',
        url: new URL('../assets/images/trad_09.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 29,
        type: 'image',
        url: new URL('../assets/images/trad_10.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 30,
        type: 'image',
        url: new URL('../assets/images/trad_11.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 31,
        type: 'image',
        url: new URL('../assets/images/trad_12.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 32,
        type: 'image',
        url: new URL('../assets/images/trad_13.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 33,
        type: 'image',
        url: new URL('../assets/images/trad_14.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 34,
        type: 'image',
        url: new URL('../assets/images/trad_15.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 35,
        type: 'image',
        url: new URL('../assets/images/trad_16.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 36,
        type: 'image',
        url: new URL('../assets/images/trad_16.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 37,
        type: 'image',
        url: new URL('../assets/images/trad_16.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 38,
        type: 'image',
        url: new URL('../assets/images/trad_17.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 39,
        type: 'image',
        url: new URL('../assets/images/trad_18.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 40,
        type: 'image',
        url: new URL('../assets/images/trad_19.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 41,
        type: 'image',
        url: new URL('../assets/images/trad_20.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 42,
        type: 'image',
        url: new URL('../assets/images/trad_21.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 43,
        type: 'image',
        url: new URL('../assets/images/trad_22.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 44,
        type: 'image',
        url: new URL('../assets/images/trad_23.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 45,
        type: 'image',
        url: new URL('../assets/images/trad_24.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Traditional art'
    },
    {
        id: 46,
        type: 'image',
        url: new URL('../assets/images/trad_25.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Cherries (sketch)'
    },
    {
        id: 47,
        type: 'image',
        url: new URL('../assets/images/trad_26.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Cherries'
    },
    {
        id: 48,
        type: 'image',
        url: new URL('../assets/images/trad_26.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Cherries'
    },
    {
        id: 49,
        type: 'image',
        url: new URL('../assets/images/trad_27.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Basket of Fruits'
    },
    {
        id: 50,
        type: 'image',
        url: new URL('../assets/images/trad_28.webp', import.meta.url).href,
        categories: ['Traditional Art', 'Pencil Art'],
        title: 'Basket of Fruits'
    },
    {
        id: 51,
        type: 'image',
        url: new URL('../assets/images/amulet_of_avalor.webp', import.meta.url).href,
        categories: ['Digital Art', 'Jewelry', 'Fan Art'],
        title: 'Amulet of Avalor'
    }
]);

// Track randomized display order
const randomizedPhotos = ref([]);

// True Fisher-Yates Random Shuffle algorithm
const shufflePhotos = () => {
    const arr = [...photos.value];
    for (let i = arr.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [arr[i], arr[j]] = [arr[j], arr[i]];
    }
    randomizedPhotos.value = arr;
};

const categoriesList = computed(() => {
    const allCats = photos.value.flatMap(p => p.categories || []);
    return ['All', ...new Set(allCats)];
});

// Filter Process applied directly onto the randomized array list
const filteredPhotos = computed(() => {
    return randomizedPhotos.value.filter(photo => {
        const matchesCategory = selectedCategory.value === 'All' ||
            (photo.categories && photo.categories.includes(selectedCategory.value));

        const matchesSearch = photo.title.toLowerCase().includes(searchQuery.value.toLowerCase());

        return matchesCategory && matchesSearch;
    });
});

// Modal and Navigation Logic
const openModal = (photo) => {
    activePhoto.value = photo;
};

const closeModal = () => {
    activePhoto.value = null;
};

const navigatePhoto = (direction) => {
    if (!activePhoto.value) return;

    const currentIndex = filteredPhotos.value.findIndex(p => p.id === activePhoto.value.id);
    let nextIndex = currentIndex + direction;
    // Infinite carousel wrap-around rules
    if (nextIndex >= filteredPhotos.value.length) nextIndex = 0;
    if (nextIndex < 0) nextIndex = filteredPhotos.value.length - 1;

    activePhoto.value = filteredPhotos.value[nextIndex];
};

// Keyboard Accessibility listener (Arrow keys left/right & Escape key close)
const handleKeyDown = (e) => {
    if (!activePhoto.value) return;
    if (e.key === 'ArrowRight') navigatePhoto(1);
    if (e.key === 'ArrowLeft') navigatePhoto(-1);
    if (e.key === 'Escape') closeModal();
};

// Shuffle arrays right when the component loads onto screen
onMounted(() => {
    shufflePhotos();
    window.addEventListener('keydown', handleKeyDown);
});
onUnmounted(() => window.removeEventListener('keydown', handleKeyDown));
</script>

<template>
    <div id="body">
        <h1 class="text-mask">Gallery</h1>

        <div class="gallery-container">
            <!-- Search Bar -->
            <div class="search-container">
                <input v-model="searchQuery" type="text" placeholder="Search photos or videos by title..."
                    class="search-bar" />
            </div>

            <div id="categories-div-arrow">
                <p>Categories</p>

                <button id="button-open-close" @click="categoriesTab = !categoriesTab" type="button">
                    <i :class="['fas', categoriesTab ? 'fa-chevron-up' : 'fa-chevron-down']"></i>
                </button>
            </div>

            <!-- Category Tabs -->
            <div class="tabs" v-if="categoriesTab">
                <button v-for="cat in categoriesList" :key="cat" :class="{ active: selectedCategory === cat }"
                    @click="selectedCategory = cat">
                    {{ cat }}
                </button>
            </div>

            <!-- Full-Screen Modal with Navigation -->
            <div v-if="activePhoto" class="modal-overlay" @click="closeModal">
                <button class="nav-btn prev-btn" @click.stop="navigatePhoto(-1)">‹</button>

                <div class="modal-content" @click.stop>
                    <button class="close-btn" @click="closeModal">×</button>

                    <!-- Large Image Mode -->
                    <img v-if="activePhoto.type === 'image'" :src="activePhoto.url" :alt="activePhoto.title" />

                    <!-- Large Video Player Mode -->
                    <video v-else-if="activePhoto.type === 'video'" :src="activePhoto.url" controls autoplay
                        class="modal-video-player">
                        <div class="play-overlay">
                            <span class="play-icon">▶</span>
                        </div>
                    </video>

                    <h2>{{ activePhoto.title }}</h2>
                    <div class="modal-tags">
                        <span v-for="tag in activePhoto.categories" :key="tag" class="tag-badge">
                            {{ tag }}
                        </span>
                    </div>
                </div>

                <button class="nav-btn next-btn" @click.stop="navigatePhoto(1)">›</button>
            </div>

            <div class="photo-grid box">
                <div v-for="photo in filteredPhotos" :key="photo.id" class="photo-item" @click="openModal(photo)">
                    <div class="image-wrapper">
                        <!-- Render Image if type is image -->
                        <img v-if="photo.type === 'image'" :src="photo.url" :alt="photo.title" />

                        <!-- Render Video Thumbnail if type is video -->
                        <div v-else-if="photo.type === 'video'">
                            <video :src="photo.url" muted preload="metadata" />
                            <div class="play-overlay">
                                <span class="play-icon">▶</span>
                            </div>
                        </div>
                        <!--<video v-else-if="photo.type === 'video'" :src="photo.url" muted preload="metadata" />-->
                    </div>

                    <div class="photo-info">
                        <h3>{{ photo.title }}</h3>
                        <div class="tags-container">
                            <span v-for="tag in photo.categories" :key="tag" class="tag-badge">
                                {{ tag }}
                            </span>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
h1:first-child {
    font-size: 10vh;
    text-align: center;
}

#categories-div-arrow {
    width: 70%;
    margin-bottom: 2%;

    font-size: 30px;

    display: flex;
    justify-content: space-between;
    justify-self: center !important;

    button {
        color: var(--text-color);
        background: none;
    }
}

.gallery-container {
    max-width: 1200px;

    margin: 0 auto;
    padding: 20px;

    /* Search Bar */
    .search-container {
        margin-bottom: 20px;

        justify-content: center;
        text-align: center;
        justify-self: center;

        .search-bar {
            width: 50vw;
            //max-width: 400px;

            padding: 12px;

            border: 2px solid var(--pastel-color-2);
            border-radius: 25px;

            font-size: 16px;
        }
    }

    /* Tabs */
    .tabs {
        margin-bottom: 30px;
        gap: 10px;

        display: flex;
        justify-content: center;
        flex-wrap: wrap;

        transition: 5s;

        button {
            background: var(--text-color);

            padding: 10px 20px;
            border: 1px solid var(--pastel-color-2);

            border-radius: 20px;
            font-weight: bold;

            transition: var(--transition);
            cursor: pointer;

            &:hover {
                color: var(--text-color);
                background: var(--pastel-color-2);
            }

            &.active {
                //color: var(--text-color);
                background: var(--pastel-color-2);

                border-color: var(--pastel-color-2);
            }
        }
    }

    /* Card Grid Layout */
    .photo-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
        gap: 20px;

        .photo-item {
            background: var(--dark-color);

            border-radius: 12px;
            border: 1px solid var(--pastel-color-2);

            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);

            transition: transform var(--transition), box-shadow 0.2s;

            cursor: pointer;
            overflow: hidden;

            &:hover {
                box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
                transform: translateY(-5px);

                /*.play-overlay {
                    background: rgba(0, 0, 0, 0.4);
                }*/

                .play-icon {
                    color: var(--text-color);
                    background: var(--pastel-color-2);
                    //background: #42b883;

                    transform: scale(1.1);
                    transition: var(--transition);
                }
            }

            .image-wrapper {
                background: #222;

                width: 100%;
                height: 220px;

                position: relative;
                overflow: hidden;

                img,
                video {
                    width: 100%;
                    height: 100%;
                    object-fit: cover;
                    display: block;
                }

                /*img {
                    width: 100%;
                    height: 35vh;
                    object-fit: cover;
                    display: block;
                }

                video {
                    width: 100%;
                    height: 220px;

                    object-fit: cover;

                    display: block;
                }*/
            }

            .photo-info {
                padding: 15px;

                h3 {
                    color: var(--white-color);

                    margin: 0 0 10px 0;
                    font-size: 18px;
                }
            }
        }
    }

    /* Small Category Badge Tags */
    .tags-container,
    .modal-tags {
        gap: 6px;

        display: flex;
        flex-wrap: wrap;
    }

    .tag-badge {
        //color: var(--text-color);
        color: #4b5563;
        background: var(--pastel-color-2);

        padding: 4px 10px;
        border-radius: 12px;

        font-size: 12px;
        font-weight: 500;

        text-transform: uppercase;
    }

    /* Modal */
    .modal-overlay {
        background: rgba(0, 0, 0, 0.9);

        top: 0;
        left: 0;
        right: 0;
        bottom: 0;

        display: flex;
        align-items: center;
        justify-content: center;

        position: fixed;

        z-index: 1000;

        /* Navigation buttons */
        .nav-btn {
            color: var(--text-color);
            background: rgba(255, 255, 255, 0.15);

            top: 50%;

            width: 60px;
            height: 60px;
            border-radius: 50%;

            font-size: 48px;

            border: none;
            position: absolute;

            display: flex;
            align-items: center;
            justify-content: center;

            transition: var(--transition);
            transform: translateY(-50%);

            cursor: pointer;
            user-select: none;

            &:hover {
                background: rgba(255, 255, 255, 0.3);
            }
        }

        .prev-btn {
            left: 40px;
        }

        .next-btn {
            right: 40px;
        }

        .modal-content {
            background: var(--dark-color);

            max-width: 80%;
            max-height: 85%;

            padding: 25px;
            border-radius: 12px;

            text-align: center;

            position: relative;

            img {
                max-width: 100%;
                max-height: 65vh;

                object-fit: contain;

                border-radius: 15px;
            }

            h2 {
                color: var(--text-color);

                margin: 15px 0 10px 0;
                font-size: 22px;
            }


            .close-btn {
                color: var(--text-color);
                background: transparent;

                top: 2.5px;
                right: 3.5px;

                font-size: 50px;

                position: absolute;

                border: none;
                cursor: pointer;
            }

            .modal-video-player {
                background: #000;

                max-width: 100%;
                max-height: 65vh;

                border-radius: 6px;
                outline: none;

            }

        }
    }

}

.play-overlay {
    //background: rgba(0, 0, 0, 0.25);

    top: 0;
    left: 0;
    right: 0;
    bottom: 0;

    display: flex;
    align-items: center;
    justify-content: center;
    justify-self: center;

    position: absolute;
    transition: background 0.2s;

    .play-icon {
        color: #222;
        background: var(--text-color);

        width: 50px;
        height: 50px;

        //padding-left: 4px;
        border-radius: 50%;

        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);

        font-size: 2rem;
        //font-size: 50px;

        display: flex;
        align-items: center;
        justify-content: center;

        transition: var(--transition);
        //transition: transform 0.2s;
    }
}


@media screen and (max-width: 1024px) {
    h1:first-child {
        font-size: 10vh;
    }
}

@media screen and (max-width: 768px) {
    h1:first-child {
        font-size: 7vh;
    }

    .gallery-container {
        .search-container {
            width: 35vw !important;

            .search-bar {
                width: 35vw !important;
            }
        }
    }
}

@media (max-width: 600px) {
    .photo-grid {
        grid-template-columns: 1fr 1fr !important;
    }

    .nav-btn {
        width: 45px;
        height: 45px;
        font-size: 32px;
    }

    .prev-btn {
        left: 10px;
    }

    .next-btn {
        right: 10px;
    }

    .gallery-container {
        .search-container {
            width: 100% !important;

            .search-bar {
                width: 100% !important;
            }
        }
    }
}

@media (max-width: 400px) {
    .photo-grid {
        grid-template-columns: 1fr !important;
    }
}
</style>