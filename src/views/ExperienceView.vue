<script setup>
import { ref, computed } from 'vue';

const categoriesTab = ref(false)

const experiences = ref([
    {
        id: 1,
        role: 'Freelance Artist',
        company: '',
        dates: '2026 - Present',
        description: '',
        category: 'Freelance',
        icon: 'fa-palette',
        tags: ['Digital', 'Traditional']
    },
]);

const categories = ['All', 'Freelance'];
const selectedCategory = ref('All');

const filteredJobs = computed(() => {
    const reversedList = [...experiences.value].reverse();

    if (selectedCategory.value === 'All') {
        return reversedList;
    }
    return reversedList.filter(job => job.category === selectedCategory.value);
});
</script>

<template>
    <div class="experience-page">
        <div id="categories-div-arrow">
            <p>Categories</p>

            <button id="button-open-close" @click="categoriesTab = !categoriesTab" type="button">
                <i :class="['fas', categoriesTab ? 'fa-chevron-up' : 'fa-chevron-down']"></i>
            </button>
        </div>

        <!-- Category Tags Navigation -->
        <div class="categories" v-if="categoriesTab">
            <button v-for="category in categories" :key="category"
                :class="['tag', { active: selectedCategory === category }]" @click="selectedCategory = category">
                {{ category }}
            </button>
        </div>

        <!-- Timeline Wrapper -->
        <div class="timeline">
            <!-- TransitionGroup enables fluid shuffling/filtering animations -->
            <TransitionGroup name="timeline-list">
                <div v-for="(job) in filteredJobs" :key="job.id" class="timeline-item">
                    <!-- Dynamic Font Awesome Icon replaces standard dot -->
                    <div class="timeline-dot-icon">
                        <i :class="['fas', job.icon]"></i>
                    </div>

                    <div class="timeline-content">
                        <h3>{{ job.role }}</h3>
                        <h4>{{ job.company }}</h4>
                        <p class="date">{{ job.dates }}</p>
                        <p class="description">{{ job.description }}</p>
                        <div class="job-tags">
                            <span v-for="tag in job.tags" :key="tag" class="job-tag">{{ tag }}</span>
                        </div>
                    </div>
                </div>
            </TransitionGroup>
        </div>
    </div>
</template>

<style lang="scss">
#categories-div-arrow {
    width: 70%;
    margin-bottom: 2%;

    font-size: 30px;

    display: flex;
    justify-content: space-between;
    justify-self: center;

    button {
        color: var(--text-color);
        background: none;
    }
}

.experience-page {
    max-width: 800px;
    margin: 0 auto;
    padding: 2rem;
    padding-top: 0 !important;

    /* Category Filter Tags Style */
    .categories {
        margin-bottom: 2rem;
        //margin-bottom: 3.5rem;
        /*gap: 12px;

        display: flex;
        justify-content: center;*/
        margin-bottom: 30px;
        gap: 10px;

        display: flex;
        justify-content: center;
        flex-wrap: wrap;

        .tag {
            color: #4b5563;
            background: var(--text-color);

            padding: 10px 20px;

            border: 1px solid #e5e7eb;
            border-radius: 25px;

            font-weight: 500;

            box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
            transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);

            cursor: pointer;

            &.active,
            &:hover {
                color: var(--text-color);
                background: var(--pastel-color-2);

                border-color: var(--pastel-color-2);

                transform: translateY(-1px);
                box-shadow: 0 4px 6px -1px rgba(59, 130, 246, 0.2);
            }
        }
    }

    /* Timeline Layout Base Line */
    .timeline {
        margin-left: 1.5rem;
        padding-left: 2.5rem;

        border-left: 2px solid #e5e7eb;

        position: relative;

        .timeline-item {
            background: var(--dark-color);
            //background: var(--text-color);

            margin-bottom: 2.5rem;
            padding: 1.25rem;

            border-radius: 8px;
            border: 3px dashed var(--pastel-color-2);
            //border: 1px solid var(--pastel-color-2);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);

            position: relative;

            .timeline-dot-icon {
                //color: var(--text-color);
                color: #222;
                background: var(--pastel-color-2);

                left: -3.45rem;
                top: 14px;

                width: 28px;
                height: 28px;
                border-radius: 50%;

                box-shadow: 0 0 0 4px #ffffff, 0 2px 4px rgba(0, 0, 0, 0.1);

                font-size: 0.85rem;

                display: flex;
                align-items: center;
                justify-content: center;

                position: absolute;
                z-index: 2;
            }

            .timeline-content {
                color: var(--text-color);
                background-color: var(--dark-color);

                h3 {
                    color: var(--text-color);
                    //color: #111827;

                    margin: 0;
                    font-size: 1.25rem;
                }

                h4 {
                    color: #b6b5af;
                    //color: #4b5563;

                    margin: 0.35rem 0 0;
                    font-weight: 500;
                }

                .date {
                    color: #c1cada;
                    //color: #9ca3af;

                    margin: 0.5rem 0 0.75rem;

                    font-size: 0.85rem;
                    font-weight: 500;
                }

                .description {
                    color: #d5d9e0;
                    //color: #374151;

                    margin: 0;
                    line-height: 1.5;
                }

                .job-tags {
                    margin-top: 1rem;

                    gap: 8px;

                    display: flex;
                    flex-wrap: wrap;

                    .job-tag {
                        //color: #4b5563;
                        //background: var(--text-color);

                        padding: 4px 10px;

                        border-radius: 6px;
                        border: 1px solid var(--pastel-color-2);

                        font-weight: 500;
                        font-size: 0.75rem;
                    }
                }
            }
        }
    }
}

/* --- Vue TransitionGroup Classes --- */

/* Elements Entering and Leaving */
.timeline-list-enter-active,
.timeline-list-leave-active {
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

/* From State (Entering) / To State (Leaving) */
.timeline-list-enter-from,
.timeline-list-leave-to {
    opacity: 0;
    transform: translateX(-30px);
}

/* Absolute positioning during leave ensures smooth grid collapsing */
.timeline-list-leave-active {
    position: absolute;
    width: calc(100% - 2.5rem);
}

/* Smooth reordering layout movement (v-move) */
.timeline-list-move {
    transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

/*@media screen and (max-width: 600px) {
    .categories {
        display: flex;
        flex-wrap: nowrap;
        overflow-x: auto;
        -webkit-overflow-scrolling: touch;
        
        gap: 20px;
        padding: 15px;
        scrollbar-width: none;
    }

     .categories {
        .tag {
            &:first-child {
                margin-left: 250px;
            }

            &:last-child {
                margin-right: 50px;
            }
        }
    }
}*/
</style>