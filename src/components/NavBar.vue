<template>
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">BOOKPHILIA</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <a class="nav-link active" aria-current="page" href="#">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Shop</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">About</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Contact</a>
            </li>
          </ul>
          <!-- Search Form -->
          <form class="d-flex" role="search">
            <input
              class="form-control me-2"
              :value="searchQuery"
              @input="$emit('update:searchQuery', $event.target.value)"
              type="search"
              placeholder="Search"
              aria-label="Search"
            />
          </form>
          <!-- Cart Icon -->
          <div class="cart-icon ms-3">
            <img src="@/assets/images/shopping-bag.png" alt="Cart" />
            <div v-if="cartCount > 0" class="cart-count">{{ cartCount }}</div>
          </div>
        </div>
      </div>
    </nav>
  </template>
  
  <script>
  export default {
    name: "BookphiliaNavBar", // Nom multi-mot
    props: {
      searchQuery: {
        type: String,
        required: true,
      },
      cartCount: {
        type: Number,
        default: 0,
      },
    },
  };
  </script>
  <style >
  /* Add the navbar styles you already have */
  .navbar {
    background: linear-gradient(45deg, #e0d4b2, #f0e1b2);
    color: #333;
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);
    padding: 20px 50px;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1000;
    transition: background-color 0.3s ease, box-shadow 0.3s ease;
  }
  .cart-icon img {
    width: 28px;
    height: 28px;
    cursor: pointer;
  }
  .cart-count {
    position: absolute;
    top: -5px;
    right: -5px;
    background-color: red;
    color: white;
    border-radius: 50%;
    padding: 3px 6px;
    font-size: 10px;
    font-weight: bold;
    min-width: 20px;
    text-align: center;
  }
  </style>
  