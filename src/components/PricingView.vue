<script setup></script>

<template>
  <main>
    <div class="container has-text-centered">
      <h1 class="title">Our Pricing</h1>
      <div
        class="toggle-container is-flex is-align-content-center is-align-items-center"
      >
        <span>Annualy</span>
        <input type="checkbox" id="switch" /><label for="switch">Toggle</label>
        <span>Monthly</span>
      </div>
      <div class="box">
        <h2>Basic</h2>
        <h3 class="is-size-1"><span>&dollar; 199.99</span></h3>
        <hr />
        <p>500 GB Storage</p>
        <hr />
        <p>2 Users Allowed</p>
        <hr />
        <p>Send up to 3 GB</p>
        <hr />
        <a
          class="button is-medium is-fullwidth is-uppercase has-text-weight-bold has-text-white is-size-7"
        >
          learn more
        </a>
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
</style>
