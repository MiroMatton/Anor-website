<script>
  export let image;

  import arrow from "$lib/icons/arrow.svg";

  import Banner from "$lib/components/banner.svelte";
</script>

<Banner {image} alt={"foto huis la neuve forge"} />

<section>
  <div id="title">
    <h1>Gite de la Neuve Forge</h1>
    <p>Anor, Frankrijk</p>
  </div>
  <div id="moreInfo">
    <h2>Meer te weten komen?</h2>
    <a href="/gite"><img src={arrow} /></a>
  </div>
  <div id="intro">
    <h2>rustig plekje in midden van nergens</h2>
    <p>
      Het natuurhuisje is gelegen tegen een bos van 7000 ha. Op het domein is er
      een vijver van 9 ha waarop je kan vissen, roeiboten liggen ter
      beschikking. De gite vormt ook de ideale uitvalsbasis om dorpen en musea
      in de ruime omgeving te ontdekken. Lompret, veruit het mooiste dorpje van
      Wallonie ligt op 28 km van de gite. Chimay: wereldberoemd om zijn
      trappistenbieren, zijn kasteel is 22 km verwijderd...
    </p>
  </div>
</section>

<style lang="scss">
  section {
    display: flex;
    margin: 2rem 0 5rem 0;
  }

  #title,
  #moreInfo,
  #intro {
    border-radius: var(--borderRadius);
    flex: 1;
    text-align: left;
    padding: 1rem;
  }

  #title {
    background-color: var(--green);
    color: var(--darkGreen);

    h1 {
      font-size: 2rem;
      font-family: Fraunces;
    }
  }

  #moreInfo {
    position: relative;
    background-color: var(--darkGreen);
    color: var(--green);

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

    h2 {
      color: var(--darkGreen);
      font-size: 1.5rem;
      font-family: Fraunces;
    }
  }
</style>
