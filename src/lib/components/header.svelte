<script>
  export let image;

  import arrow from "$lib/icons/arrow.svg";

  import Banner from "$lib/components/banner.svelte";
</script>

<section class="section-wrapper" >

  <div class="banner">
    <img src={image} alt={"foto huis la neuve forge"} class="banner"/>
  </div>
  

  <div class="info">
    <div id="title">
    <h1>Gite de la Neuve Forge</h1>
    <p>Anor, Frankrijk</p>
    </div>
    <div id="intro">
      <p>
        Het natuurhuisje is gelegen tegen een bos van 7000 ha. Op het domein is er
        een vijver van 9 ha waarop je kan vissen, roeiboten liggen ter
        beschikking. De gite vormt ook de ideale uitvalsbasis om dorpen en musea
        in de ruime omgeving te ontdekken. Lompret, veruit het mooiste dorpje van
        Wallonie ligt op 28 km van de gite. Chimay: wereldberoemd om zijn
        trappistenbieren, zijn kasteel is 22 km verwijderd...
      </p>
    </div>
    <div id="moreInfo">
      <h2>Meer te weten komen?</h2>
      <a href="/gite"><img src={arrow} /></a>
    </div>
    
  </div>
  
</section>

<style lang="scss">
  section {
    display: flex;
    gap: 2rem;
    padding: 5rem 0;

    .banner {
      flex: 2;
        img {
          height: 100%;
          width: 100%;
          border-radius: var(--borderRadius);
        }
    }

    .info {
      flex: 1;
      display: flex;
      flex-direction: column;
      min-height: 70vh;
    }
  }

  #title,
  #moreInfo,
  #intro {
    border-radius: var(--borderRadius);
    text-align: left;
    padding: 2rem;
  }

  #title {
    background-color: var(--green);
    color: var(--darkGreen);
    flex: 2;

    h1 {
      font-size: 2rem;
      font-family: Fraunces;
    }
  }

  #moreInfo {
    position: relative;
    background-color: var(--darkGreen);
    color: var(--green);
    flex: 1;

    h2 {
      font-size: 2rem;
      font-family: Fraunces;
    }

    img {
      position: absolute;
      bottom: 1rem;
      right: 1rem;
    }
  }

  #intro {
    background-color: white;

    flex: 2;
        display: flex;
        align-items: end;
        justify-content: center;

        p {
          word-spacing: 0.75rem;
          font-size: 1.25rem;
          font-weight: 100;
          color: var(--darkGreen);
        }

    h2 {
      color: var(--darkGreen);
      font-size: 1.5rem;
    }
  }

  .section-wrapper {
	padding: 5rem;
	max-width: 120rem;
	margin: 0 auto;
  }
</style>
