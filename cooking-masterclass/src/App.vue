<script setup>
import { ref } from 'vue'
import CourseCard from './components/CourseCard.vue'


const courses = ref([
{ id: 1, name: 'Italian Cuisine Basics', chef: 'Chef Vinsmoke Sanji', level: 'Beginner', price: 49 },
{ id: 2, name: 'French Pastry Mastery', chef: 'Chef Soma Yukihara', level: 'Advanced', price: 79 },
{ id: 3, name: 'Vegan Fusion Dishes', chef: 'Chef Joichiro Yukihara', level: 'Intermediate', price: 59 },
{ id: 4, name: 'Sushi Rolling Art', chef: 'Chef Charmy Pappitson', level: 'Beginner', price: 45 },
{ id: 5, name: 'BBQ Grill Perfection', chef: 'Chef Megumi Tadokoro', level: 'Intermediate', price: 65 },
{ id: 6, name: 'Chocolate Sculpting', chef: 'Chef Yor Forger', level: 'Advanced', price: 90 }
])


const wishlist = ref([])


function saveToWishlist(course) {
if (!wishlist.value.find(item => item.id === course.id)) {
wishlist.value.push(course)
}
}
</script>

<style>
body {
font-family: Arial, sans-serif;
padding: 5px;
margin: 10px;
background: #fff;
}
.heading{
  text-align: center;
  color: #fca311;
  font-size: 75px;
}
</style>

<template>
  <div class="min-h-sccreen bg-gray-100 p-6">
    <h1 class="text-3xl font-bold mb-6 text-center heading">Cooking Materclass Catalogue</h1>
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
        <CourseCard
          v-for="course in courses"
          :key="course.id"
          :course="course"
          @save="saveToWishlist"/>
      </div>

      <h2 class="text-2xl font-semibold mt-10 mb-4">Wishlist</h2>
      <ul class="list-disc ml-5">
        <li v-for="item in wishlist" :key="item.id">
          {{ item.name }} - {{ item.chef }} ({{ item.level }})
        </li>
      </ul>
  </div>
</template>