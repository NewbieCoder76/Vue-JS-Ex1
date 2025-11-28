<template>
    <header class="main-header">
      <h1 class="logo">Cooking Masterclass</h1>
  
      <div class="wishlist-box">
        <span class="icon">❤️</span>
        <span class="count">{{ wishlist }}</span>
      </div>
    </header>
  </template>
  
  <script>
  export default {
    name: "Header",
    props: {
      wishlist: Number
    }
  };
  </script>
  
  <style scoped>
  .main-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.2rem 2rem;
    background: white;
    border-bottom: 1px solid #e5e7eb;
    position: sticky;
    top: 0;
    z-index: 20;
  }
  
  .logo {
    font-size: 1.6rem;
    font-weight: 700;
    color: #034694;
  }
  
  .wishlist-box {
    display: flex;
    align-items: center;
    gap: 6px;
    background: #034694;
    color: white;
    padding: .5rem 1rem;
    border-radius: 10px;
    font-weight: bold;
    font-size: 1rem;
  }
  
  .icon {
    font-size: 1.2rem;
  }
  
  .count {
    font-size: 1.1rem;
  }
  </style>
  