<script>
  //imports

  //images
  import house from "$lib/images/house.jpg";
  import anor from "$lib/images/anorTest.jpg";

  //components
  import Reviews from "$lib/components/reviews.svelte";
  import Gallery from "$lib/components/gallery.svelte";
  import Header from "$lib/components/header.svelte";
  import Banner from "$lib/components/banner.svelte";
  import Contact from "$lib/components/contact.svelte";
</script>

<svelte:head>
  <title>Gite de la Neuve Forge | Anor</title>
  <meta name="description" content="Gite de la Neuve Forge" />
</svelte:head>

<Header image={anor} />
<Reviews />

<section class="section-wrapper">
  <Banner image={house} alt={"foto huis la neuve forge"} />
  <div class="twoDiv">
    <Gallery />
    <Contact />
  </div>
</section>

<style lang="scss">
  h1,
  h2 {
    font-size: xx-large;
    font-weight: bold;
    margin-bottom: 0;
  }

  section {
    display: flex;
    flex-direction: column;
    margin-bottom: 5rem;

    div {
      display: flex;
      flex: 1;
      margin-top: 2rem;
    }
  }
  
  .twoDiv {
    display: flex;
    gap: var(--gap)
  }
</style>
