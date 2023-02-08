<template>
  <div id="card" class="card">
    <img src="https://media.istockphoto.com/id/1147544807/vector/thumbnail-image-vector-graphic.jpg?s=612x612&w=0&k=20&c=rnCKVbdxqkjlcs3xH87-9gocETqpspHFXu5dIGB4wuM=" id="image">
    <h2 id="title">Placeholder Card</h2>
    <p id="description">placeholder card description</p>
    <button id="details" class="button" @click="btn_details($event)">details</button>
  </div>
</template>

<script>
export default {
  methods: {
    btn_details: function(event) {
      let desc = event.target.previousElementSibling;
      (desc.style.display == 'none') ? (desc.style.display = '') : (desc.style.display = 'none');
    }
  }
}
</script>

<style>
.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.3);
  max-width: 300px;
  margin: 16px 16px;
  text-align: center;
  font-family: 'Roboto Mono', monospace;
}
.card img {
  width: 100%;
}
.card p {
  padding: 16px;
}
.card>.button {
  display: none;
}
</style>
