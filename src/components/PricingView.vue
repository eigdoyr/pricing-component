<script setup>
import { ref } from "vue";

const pricing = ref([
  {
    header: "Basic",
    price: 19.99,
    description: {
      storage: "500 GB Storage",
      user: "2 Users Allowed",
      sendUpTo: "Send up to 3 GB",
    },
  },
  {
    header: "Professional",
    price: 24.99,
    description: {
      storage: "1 TB Storage",
      user: "5 Users Allowed",
      sendUpTo: "Send up to 10 GB",
    },
  },
  {
    header: "Master",
    price: 39.99,
    description: {
      storage: "2 TB Storage",
      user: "5 Users Allowed",
      sendUpTo: "Send up to 20 GB",
    },
  },
]);
</script>

<template>
  <main class="py-6">
    <div class="container has-text-centered">
      <h1 class="title">Our Pricing</h1>
      <div
        class="toggle-container m-6 is-flex is-align-content-center is-align-items-center"
      >
        <span>Annualy</span>

        <input type="checkbox" id="switch" />
        <label for="switch">Toggle</label>
        <span>Monthly</span>
      </div>
      <div v-for="price in pricing" class="box pricing-card">
        <h2>{{ price.header }}</h2>
        <h3 class="is-size-1">
          <span class="is-size-2">&dollar;</span> {{ price.price }}
        </h3>

        <hr />
        <ul v-for="items in price.description" class="description">
          <li>{{ items }}</li>
          <hr />
        </ul>
        <div
          class="pointer px-2 is-normal is-fullwidth is-uppercase has-text-weight-bold is-size-7"
        >
          <a class="button is-fullwidth has-text-white"> learn more </a>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
main {
  font-family: "Montserrat", sans-serif;
  display: grid;
  align-content: center;
}

input[type="checkbox"] {
  height: 0;
  width: 0;
  visibility: hidden;
}

label {
  cursor: pointer;
  text-indent: -9999px;
  width: 52px;
  height: 27px;
  background: grey;
  display: block;
  border-radius: 100px;
  position: relative;
}

label:after {
  content: "";
  position: absolute;
  top: 2px;
  left: 5px;
  width: 22px;
  height: 22px;
  background: #fff;
  border-radius: 90px;
  transition: 0.3s;
}

input:checked + label,
.button {
  background: linear-gradient(hsl(236, 72%, 79%), hsl(237, 63%, 64%));
}

input:checked + label:after {
  left: calc(100% - 5px);
  transform: translateX(-100%);
}

label:active:after {
  width: 25px;
}

.button {
  letter-spacing: 0.1rem;
  font-family: "Montserrat", sans-serif;
}

.pricing-card {
  max-width: 20rem;
}
</style>
