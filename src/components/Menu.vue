<template>
  <li class="nav-item">
    <a :href="target" class="as-navbar__link">
      <p class="as-navbar__link--name">{{ name }}</p>
      <div v-if="count" class="as-navbar__count">
        <span>{{ count }}+</span>
      </div>
    </a>
  </li>
</template>

<script>
export default {
  name: "Menu",
  props: {
      name: String,
      target: String,
      count: Number
  }
};
</script>
