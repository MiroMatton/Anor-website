<script>
  // import all gallery images
  const images = import.meta.glob("$lib/images/gallery/*.{jpg,png,gif,jpeg}");

  // Extract the paths of the images into an array
  let imagePaths = Object.keys(images);

  let currentImageIndex = 0;

  // Change image every 5 seconds
  const interval = setInterval(() => {
    currentImageIndex = (currentImageIndex + 1) % imagePaths.length;
  }, 5000);
</script>

<div id="gallery">
  <img src={imagePaths[currentImageIndex]} alt="foto's anor" class="image" />
</div>

<style>
  #gallery {
    flex: 2;

    .image {
      height: 40rem;
      width: 100%;
      border-radius: 30px;
    }
  }
</style>
