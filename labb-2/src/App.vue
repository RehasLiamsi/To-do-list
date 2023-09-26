<script setup>
import LoopDirective from './components/LoopDirective.vue'
import SlotContainer from './components/SlotContainer.vue'
</script>

<template>
  <SlotContainer>
  <div class=header>
  <h1>My To-do List</h1>
</div>
<LoopDirective />
</SlotContainer>
</template>

<style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Gluten:wght@700&family=Libre+Baskerville:ital,wght@0,400;0,700;1,400&display=swap');
.header{
  padding: 10px 50px;
  background-color: #2F1B41;
  color: white;
}
h1{
  font-family: 'Libre Baskerville', serif;
  letter-spacing: 1px;
  width:100;
  text-align: center;
}
</style>
