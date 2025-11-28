<template>
    <div>
  
      <!-- Header with wishlist -->
      <Header :wishlist="wishlistCount" />
  
      <div class="wrapper">
        <div class="courses-grid">
          <CourseCard
            v-for="course in courses"
            :key="course.id"
            :course="course"
            @add-to-wishlist="addToWishlist"
          />
        </div>
      </div>
  
    </div>
  </template>
  
  <script>
  import Header from "./components/Header.vue";
  import CourseCard from "./components/CourseCard.vue";
  
  export default {
    components: { Header, CourseCard },
  
    data() {
      return {
        wishlistCount: 0,
        courses: [
          { id: 1, name: "Italian Cuisine", chef: "Chef Marco", level: "Beginner", price: 899, available: true },
          { id: 2, name: "Sushi Mastery", chef: "Chef Hana", level: "Advanced", price: 1200, available: false },
          { id: 3, name: "Bakery Essentials", chef: "Chef Lucy", level: "Intermediate", price: 750, available: true }
        ]
      };
    },
  
    methods: {
      addToWishlist() {
        this.wishlistCount++;
      }
    }
  };
  </script>
  
  <style>
  .wrapper {
    padding: 2rem;
  }
  
  .courses-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
  }
  
  /* Responsive */
  @media (max-width: 768px) {
    .courses-grid {
      grid-template-columns: repeat(2, 1fr);
    }
  }
  
  @media (max-width: 480px) {
    .courses-grid {
      grid-template-columns: 1fr;
    }
  }
  </style>
  