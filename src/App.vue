<template>
  <CardControls />
  <div id="cards" class="cards">
    <Card />
  </div>
</template>

<script setup>
import Card from './components/Card.vue'
import CardControls from './components/CardControls.vue'
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto+Mono&display=swap');

.cards {
  display: flex;
  flex-direction: row;
  justify-content: center;
}

.button {
  background-color: #2895e8; /* Blue */
  border: none;
  color: white;
  padding: 8px 2vw;
  text-align: center;
  text-decoration: none;
  font-size: 14px;
  margin-bottom: 8px;
  cursor: pointer;
  border-radius: 4px;
  width: 25%;
  transform: scale(1);
  transition: 0.6s;
}
.button:hover, .button:focus {
  transform: scale(1.05);
  box-shadow: 0px 0px 48px 10px rgba(40,149,232,.7);
}

@media (min-width: 501px) and (max-width: 800px) {
  .card>.button {
    display: inline-block;
  }
}
@media (max-width: 500px) {
  .card {
    transform: scale(1.1);
  }
}
</style>
