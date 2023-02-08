<template>
  <div class="controls">
    <button id="cardnew" class="button" @click="btn_cardnew()">add clone card</button>
    <button id="cardtitle" class="button" @click="btn_cardtitle()">change clone title</button>
    <button id="cardbg" class="button" @click="btn_cardbg()">change clone bg color</button>
    <button id="carddel" class="button" @click="btn_carddel()">delete newest clone</button>
  </div>  
</template>

<script>
import { createApp } from 'vue'
import Card from './Card.vue'
export default {
  methods: {
    btn_cardnew: function() {
      // set new card class to dupecard
      let instance = createApp(Card).mount(document.createElement('div'));
      instance.$el.classList.add('dupecard');
      document.getElementById('cards').appendChild(instance.$el);
    },
    btn_cardtitle: function() {
      if (document.querySelectorAll('.dupecard') != null) {
        let index = prompt("Enter the index of the CLONE you wish to edit");
        let title = prompt("Enter new title for the card");
        document.querySelectorAll('.dupecard')[index].children[1].innerHTML = title;
      }
    },
    btn_cardbg: function() {
      if (document.querySelectorAll('.dupecard') != null) {
        let index = prompt("Enter the index of the CLONE you wish to edit");
        let color = prompt("Enter a color such as red, or green or white to return to default");
        document.querySelectorAll('.dupecard')[index].style.backgroundColor = color;
      }
    },
    btn_carddel: function() {
      if (document.querySelectorAll('.dupecard') != null) {
        document.getElementById('cards').removeChild(document.querySelectorAll('.dupecard')[document.querySelectorAll('.dupecard').length - 1]);
      }
    }
  }
}
</script>

<style>
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
