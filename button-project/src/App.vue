<script setup lang="ts">
import Button from "./components/Button.vue";
</script>

<template>
  <div>
    <Button tag="button" size="small" variant="filled" color-variant="orange"
      >Wejdź do pokoju</Button
    >
    <Button tag="button" size="regular" variant="filled" color-variant="orange"
      >Wybierz teraz</Button
    >
    <Button tag="button" size="large" variant="filled" color-variant="orange"
      >Text</Button
    >
  </div>
  <div>
    <Button
      tag="button"
      size="small"
      variant="filled"
      color-variant="dark-orange"
      >Wejdź do pokoju</Button
    >
    <Button
      tag="button"
      size="regular"
      variant="filled"
      color-variant="dark-orange"
      >Wybierz teraz</Button
    >
    <Button
      tag="button"
      size="large"
      variant="filled"
      color-variant="dark-orange"
      >Text</Button
    >
  </div>
  <div>
    <Button tag="button" size="small" variant="filled" color-variant="green"
      >Wejdź do pokoju</Button
    >
    <Button tag="button" size="regular" variant="filled" color-variant="green"
      >Wybierz teraz</Button
    >
    <Button tag="button" size="large" variant="filled" color-variant="green"
      >Text</Button
    >
  </div>
  <div>
    <Button
      tag="button"
      size="small"
      variant="filled"
      color-variant="dark-green"
      >Wejdź do pokoju</Button
    >
    <Button
      tag="button"
      size="regular"
      variant="filled"
      color-variant="dark-green"
      >Wybierz teraz</Button
    >
    <Button
      tag="button"
      size="large"
      variant="filled"
      color-variant="dark-green"
      >Text</Button
    >
  </div>
  <div>
    <Button tag="button" size="small" variant="filled" color-variant="red"
      >Wejdź do pokoju</Button
    >
    <Button tag="button" size="regular" variant="filled" color-variant="red"
      >Wybierz teraz</Button
    >
    <Button tag="button" size="large" variant="filled" color-variant="red"
      >Text</Button
    >
  </div>
  <div>
    <Button tag="button" size="small" variant="outlined" color-variant="red"
      >Wybierz jutro</Button
    >
    <Button tag="button" size="regular" variant="outlined" color-variant="red"
      >Wybierz teraz</Button
    >
    <Button tag="button" size="large" variant="outlined" color-variant="red"
      >Text</Button
    >
  </div>
  <div>
    <Button tag="button" size="large" variant="filled" color-variant="red" block
      >block</Button
    >
    <Button
      tag="button"
      size="large"
      variant="filled"
      color-variant="red"
      disabled
      >disabled</Button
    >
  </div>
  <div>
    <Button
      is="router-link"
      tag="router-link"
      to="/route"
      size="small"
      variant="filled"
      color-variant="orange"
      >vue Link</Button
    >
    <Button
      is="a"
      tag="a"
      href="https://risify.pl/"
      size="small"
      variant="filled"
      color-variant="orange"
      >a Link</Button
    >
  </div>
</template>

<style scoped></style>
