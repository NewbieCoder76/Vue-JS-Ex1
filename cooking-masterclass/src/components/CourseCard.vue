<template>
  <div class="course-card" :class="{ soldOut: !course.available }">
    <div class="course-header">
      <h3>{{ course.name }}</h3>
      <span class="chef">{{ course.chef }}</span>
    </div>

    <p class="level">{{ course.level }}</p>

    <p class="price" v-if="course.available">R{{ course.price }}</p>
    <p class="sold-out-label" v-else>Sold Out</p>

    <button
      class="wishlist-btn"
      @click="$emit('add-to-wishlist', course)"
    >
      ❤️ Add To Wishlist
    </button>
  </div>
</template>

<script>
export default {
  name: "CourseCard",
  props: {
    course: Object
  }
};
</script>

<style scoped>
.course-card {
  background: #000000;
  padding: 1.2rem;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  transition: transform .2s ease;
  margin: 20px;
}
.course-card:hover {
  transform: translateY(-4px);
}

.course-header {
  display: flex;
  flex-direction: column;
  margin-bottom: .5rem;
  color: #fca311;
}

.chef {
  font-size: 0.9rem;
  opacity: 0.6;

}

.level {
  font-weight: 600;
  margin-bottom: 0.5rem;
  color: #e5e5e5;
}

.price {
  font-size: 1.1rem;
  font-weight: bold;
  color: #fca311;
}

.wishlist-btn {
  width: 100%;
  margin-top: 1rem;
  padding: .6rem;
  border: none;
  border-radius: 8px;
  background: #fca311;
  color: white;
  cursor: pointer;
  transition: background .2s;
}

.sold-out-label {
  font-weight: bold;
  color: #c62828;
}

/*.soldOut {
  opacity: .6;
}*/
</style>
   