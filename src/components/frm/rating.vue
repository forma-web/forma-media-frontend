<script setup lang="ts">
const { rating } = defineProps<{ rating: number }>();
</script>

<template>
  <div
    class="rating"
    :class="{
      rating_bad: rating < 5,
      rating_good: rating >= 7 && rating < 8,
      rating_great: rating >= 8,
    }"
  >
    {{ rating.toFixed(1) }}
  </div>
</template>

<style scoped lang="scss">
.rating {
  width: max-content;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 1em;
  line-height: 1;
  padding: 0.3em 0.5em 0.48em;
  border-radius: 0.125em;
  font-weight: 700;
  background-color: var(--color-rating-neutral);
  user-select: none;
}
.rating_bad {
  background-color: var(--color-rating-bad);
}
.rating_good {
  background-color: var(--color-rating-good);
}
.rating_great {
  background: var(--color-rating-great-background);
  color: var(--color-rating-great);
}
</style>
