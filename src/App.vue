<template>
  <div class="grid grid-cols-1 md:grid-cols-2">
    <Button
      text="Button Success"
      type="success"
      :onClick="this.onClickSuccess"
      tailwindClass="line-through"
    ></Button>

    <Button text="Button Warning" type="warning"></Button>
    <Button text="Button Error" type="error"></Button>
    <Button text="Button Default" type="default"></Button>
  </div>

  <Card content="Hola este es el card Content" image="https://ivangreve.com/profile.jpg">
    <template v-slot:title>
      <h1>Card Title 💥</h1>
    </template>
  </Card>
</template>

<script setup>
import Button from "./components/Button.vue";
import Card from "./components/Card.vue";

const onClickSuccess = () => {
  console.log("Success Click!");
};
</script>

<style>
body {
  background-color: #e0e0e0;
  padding: 50px;
}
</style>
