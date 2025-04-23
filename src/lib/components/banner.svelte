<script>
  export let alt;
  export let image;
</script>

<img src={image} {alt} id="banner" />

<style lang="scss">
  #banner {
    border-radius: var(--borderRadius);
  }
</style>
