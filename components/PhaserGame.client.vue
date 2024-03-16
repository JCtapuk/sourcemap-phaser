<template>
    <div ref="parent" />
  </template>
  
  <script setup lang="ts">
  import type Phaser from "phaser";
  
  const parent = useState<HTMLElement>("phaser.parent");
  
  onMounted(() => {
    import("phaser").then(({ Game }) => {
      const game = new Game({
        parent: parent.value,
      });
    });
  });
  </script>