<script setup>
import { useData } from 'vitepress'

const { frontmatter } = useData()
</script>

<style scoped>
  .use-case-illustration {
    width: calc(100px + 50vw);
    max-width: 420px;
    min-width: 240px;
    margin-top: -20px !important;
    margin-left: -24px !important;
  }
  @media (max-width: 559px) {
    .use-case-illustration {
      margin-top: -14px !important;
      margin-left: -16px !important;
    }
  }
</style>

<template>
  <div class="use-case-header">
    <p class="use-case-illustration">
      <img :src="frontmatter.image" />
    </p>
    <h1>
      {{ frontmatter.title }}
    </h1>
    <p class="concept">
      {{ frontmatter.description }}
    </p>
    <ul class="benefits">
      <li v-for="(benefit, index) in frontmatter.benefits" :key="index">
        {{ benefit }}
      </li>
    </ul>
  </div>
</template>