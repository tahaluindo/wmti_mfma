<template>
  <li class="nav-item">
    <div class="dropdown as-dropdown-menu">
      <div class="as-navbar__dropdown-button">
        <p class="as-navbar__dropdown-button--name">{{ name }}</p>
        <i class="as-icon-arrow-down"></i>
      </div>
      <div class="as-navbar__dropdown-container">
        <div class="as-navbar__dropdown-content" v-if="list && list.length > 0">
          <a v-for="item, index in list" :key="index"  :href="item.target" class="as-navbar__dropdown-link">{{ item.name }}</a>
        </div>
      </div>
    </div>
  </li>
</template>

<script>
export default {
    name: "MenuDropdown",
    props: {
        name: String,
        list: Array
    }
}
</script>
