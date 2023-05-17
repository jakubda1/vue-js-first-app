<script setup>

import {RouterLink} from "vue-router";

defineProps({
    event: {
        type: Object,
        required: true,
    }
})

// const event = ref({
//     id: 123,
//     category: 'animal welfare',
//     title: 'cat adoption day',
//     description: 'Some description',
//     location: 'Meow Town',
//     date: 'January 28, 2020',
//     time: '12:00',
//     petsAllowed: true,
//     organizer: 'Kat Laydeedadee'
// })

</script>

<template>
    <RouterLink class="event-link" :to="{name:'event-details', params: {id: event.id }}">
        <div class="event-card">
            <!--       Display event data -->
            <h2>{{ event.title }}</h2>
            <span>@{{ event.time }} on {{ event.date }}</span>
        </div>
    </RouterLink>
</template>

<style scoped>
.event-card {
    padding: 20px;
    width: 250px;
    cursor: pointer;
    border: 1px solid #39495c;
    margin-bottom: 18px;
}

.event-card:hover {
    transform: scale(1.01);
    box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}

.event-link {
    color: #2c3e50;
    text-decoration: none;
}
</style>
