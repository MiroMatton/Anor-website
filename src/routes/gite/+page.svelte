<script>
  import gite from "$lib/gallery/013.jpg";
  import arrow from "$lib/icons/arrow.svg";
  import person from "$lib/icons/person.svg";
  import dog from "$lib/icons/dog.svg";
  import wifi from "$lib/icons/wifi.svg";
  import bed from "$lib/icons/bed.svg";

  import Banner from "$lib/components/banner.svelte";
  import Reviews from "$lib/components/reviews.svelte";
  import Contact from "$lib/components/contact.svelte";
  import ImageModal from "$lib/components/imageModal.svelte";

  // import all gallery images
  const images = import.meta.glob("$lib/gallery/*.{jpg,png,gif,jpeg}");

  // Extract the paths of the images into an array
  let imagePaths = Object.keys(images);

  let isOpen = false;
  let currentImage = null;

  function openModal(image) {
    currentImage = image;
    isOpen = true;
  }
  function closeModal() {
    isOpen = false;
  }
</script>

<section class="section-wrapper" >

  <div class="banner">
    <img src={gite} alt={"foto huis la neuve forge"} class="banner"/>
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
    <div id="bullet">
      <div>
        <div class="icons">
          <img src={person} alt={"max peronen aantal"} />
          <p> 5 personen</p>
        </div>
        <div class="icons">
          <img src={bed} alt={"aantal slaapkamers"} />
          <p> 2 slaapkamers</p>
        </div>
      </div>
      <div>
        <div class="icons">
          <img src={wifi} alt={"wifi beschikbaar"} />
          <p>WiFi</p>
        </div>
        <div class="icons">
          <img src={dog} alt={"geen dieren"} />
          <p> geen huisdieren</p>
        </div>
      </div>
    </div>
    
  </div>
  
</section>

<Reviews/>

<section class="section-wrapper">
  <div id="Faciliteiten">
    <div><p>
      Het natuurhuisje is gelegen tegen een bos van 7000 ha. Op het domein is er
      een vijver van 9 ha waarop je kan vissen, roeiboten liggen ter
      beschikking. De gite vormt ook de ideale uitvalsbasis om dorpen en musea
      in de ruime omgeving te ontdekken. Lompret, veruit het mooiste dorpje van
      Wallonie ligt op 28 km van de gite. Chimay: wereldberoemd om zijn
      trappistenbieren, zijn kasteel is 22 km verwijderd...
    </p></div>
    <div><p>
      Toegankelijkheid
  
    </p></div>
  </div>
</section>

<section class="section-wrapper">
  <Contact />
</section>

<section class="section-wrapper">
  <div class="gallery">
    {#each imagePaths as path}
      <img src={path} alt="gallery photo" on:click={() => openModal(path)} class="thumb" loading="lazy"/>
    {/each}
  </div>
  
</section>

<ImageModal
  src={currentImage}
  alt={"foto's gite de la neuve forge"}
  isOpen={isOpen}
  closeModal={closeModal}
/>

<style lang="scss">
  section {
    display: flex;
    gap: 2rem;
    padding: var(--gap), 0;

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
  #bullet,
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

  #bullet {
    position: relative;
    background-color: var(--darkGreen);
    color: var(--green);
    flex: 1;
    display: flex;
    align-items: center;
    justify-content: space-around;
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

  #Faciliteiten {
    display: flex;
    gap: var(--gap);

    div {
      border-radius: var(--borderRadius);
      background-color: var(--white);
      padding: var(--gap);
    }
  }

  .icons {
        display: flex;
        align-items: center;
        justify-content: flex-start;
        img {
          padding-right: 0.5rem;
        }
    }

  .section-wrapper {
    padding: 5rem;
    padding-top: var(--gap);
    max-width: 120rem;
    min-width: 90%;
    margin: 0 auto;
  }

  .gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(35rem, 1fr));
    width: 100%;
    column-gap: 2rem;   /* LEFT and RIGHT spacing between columns */
    row-gap: 1rem;  

    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      border-radius: var(--borderRadius);
    }
  }

  .thumb {
    width: 150px;
    height: auto;
    cursor: pointer;
    border-radius: 4px;
    transition: transform 0.2s;

    &:hover {
      transform: scale(1.05);
    }
  }

</style>
