<template>
  <div class="controls">
    <button id="cardnew" class="button" v-on:click="btn_cardnew">add clone card</button>
    <button id="cardtitle" class="button" v-on:click="btn_cardtitle">change clone title</button>
    <button id="cardbg" class="button" v-on:click="btn_cardbg">toggle clone bg color</button>
    <button id="carddel" class="button" v-on:click="btn_carddel">delete newest clone</button>
  </div>  
</template>

<script>
import Card from './Card.vue'
function btn_cardnew() {
  prompt("test");
  $('cards').appendChild(Card);
}
function btn_cardtitle() {
  if (this.$el.querySelectorAll('dupecard') != null) {
    let index = prompt("Enter the index of the CLONE you wish to edit")
    let title = prompt("Enter new title for the card");
    this.$el.querySelectorAll('dupecard')[index].children[1].innerHTML = title;
  }
}
function btn_cardbg() {
  if (this.$el.querySelectorAll('dupecard') != null) {
    index = prompt("Enter the index of the CLONE you wish to edit")
    color = prompt("Enter a color such as red, or green or white to return to default");
    this.$el.querySelectorAll('dupecard')[index].style.backgroundColor = color;
  }
}
function btn_carddel() {
  if (this.$el.querySelectorAll('dupecard') != null) {
    this.$el.querySelector('cards').removeChild(this.$el.querySelectorAll('dupecard')[this.$el.querySelectorAll('dupecard').length - 1])
  }
}
</script>

<style scoped>
.controls {
  margin: 16px auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.controls>.button {
  width: 20%;
}
</style>
