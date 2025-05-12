<script>
  // import all gallery images
  const images = import.meta.glob("$lib/gallery/*.{jpg,png,gif,jpeg}");

  // Extract the paths of the images into an array
  let imagePaths = Object.keys(images);

  let currentImageIndex = 0;

  // Change image every 5 seconds
  const interval = setInterval(() => {
    currentImageIndex = (currentImageIndex + 1) % imagePaths.length;
  }, 5000);


  import ImageModal from "$lib/components/imageModal.svelte";

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

<div id="gallery">
  <img src={imagePaths[currentImageIndex]} alt="foto's anor" class="image thumb" on:click={() => openModal(imagePaths[currentImageIndex])} loading="lazy" />
</div>

<ImageModal
  src={currentImage}
  alt={"foto's gite de la neuve forge"}
  isOpen={isOpen}
  closeModal={closeModal}
/>

<style>
  #gallery {
    flex: 2;

    .image {
      height: 40rem;
      width: 100%;
      border-radius: 30px;
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
