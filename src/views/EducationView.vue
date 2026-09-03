<script setup>
import { ref, computed } from 'vue';

const categoriesTab = ref(false)

const education = ref([
    {
        id: 1,
        course: 'Infinite Realms - Creative (Art x Tech) Workshop',
        type: 'Diploma',
        school: 'ACERCA and CAVIC',
        duration: 'June 2026',
        category: 'Workshop',
        icon: 'fa-palette',
    }
]);

const categories = ['All', 'Workshop'];
const selectedCategory = ref('All');

const filteredEdu = computed(() => {
    const reversedList = [...education.value].reverse();

    if (selectedCategory.value === 'All') {
        return reversedList;
    }
    return reversedList.filter(education => education.category === selectedCategory.value);
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
                <div v-for="(education) in filteredEdu" :key="education.id" class="timeline-item">
                    <!-- Dynamic Font Awesome Icon replaces standard dot -->
                    <div class="timeline-dot-icon">
                        <i :class="['fas', education.icon]"></i>
                    </div>

                    <div class="timeline-content">
                        <h3>{{ education.course }}</h3>
                        <h4>{{ education.school }}</h4>
                        <p class="description">{{ education.type }}</p>
                        <p class="date">{{ education.duration }}</p>
                    </div>
                </div>
            </TransitionGroup>
        </div>
    </div>
</template>
