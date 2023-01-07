<template>
  <div class="made-with-love">
    <p>
      Made with ❤️ by
      <span>
        <a
          href="https://github.com/AgustinZavalaA"
          class="text-amber-lighten-5 by"
        >
          Agustin Zavala</a
        >
      </span>
    </p>
  </div>
</template>

<script>
export default {
  name: "TheFooter",
};
</script>

<style scoped lang="scss">
.made-with-love {
  text-align: center;
  background: transparent;

  p {
    position: absolute;
    bottom: 0;
    width: 100%;
    left: 0;
  }
  .by {
    font-weight: bold;
    a {
      text-decoration: none;
      color: inherit;
      &:hover {
        border-bottom: 1px solid;
      }
    }
  }
}
</style>
