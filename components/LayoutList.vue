<template>
  <ul class="layout-list tiny">
    <slot />
  </ul>
</template>

<script>
</script>

<style scoped lang="scss">
@import "~@/assets/style/global";
.layout-list {
  margin: $spacing #{-$spacing / 2};
  padding: $spacing / 2 $spacing / 2 $spacing / 4;
  background-color: transparentize(getColor(neon, 100), 0.7);
  color: getColor(neon, 40);
  list-style: none;

  border-radius: $border-radius;
  @include max-width($touching) {
    border-radius: $border-radius 0 0 $border-radius;
  }
  @include max-width($narrow) {
    border-radius: 0;
  }

  li {
    margin: $spacing / 4 $spacing / 2;
    max-width: $narrow;

    &::before {
      content: "●";
      position: absolute;
      transform: translateX(calc(-50% - #{$spacing * 0.375}));
    }
  }

  a {
    color: inherit;
    background: none;

    &:hover {
      color: getColor(neon, 20);
    }
  }
}
</style>
