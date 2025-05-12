<script>
  let reviews = [
    {
      name: "Robrecht",
      date: "2023-10-13",
      nature_rating: 5,
      general_rating: 9,
      review:
        "Eindeloos wandelen in bossen en langs weides. Hier wordt men echt één met de natuur! ",
    },
    {
      name: "Dimitri",
      date: "2023-09-01",
      nature_rating: 5,
      general_rating: 9,
      review:
        "Prachtige en rustgevende omgeving waar je enkel de natuur hoort.",
    },
    {
      name: "Nicole",
      date: "2023-08-14",
      nature_rating: 5,
      general_rating: 9,
      review:
        "Een mooie privé vijver, netjes verzorgt. Met leuke zitjes. Een plek om echt te ontspannen.",
    },
    {
      name: "Antoine",
      date: "2023-06-02",
      nature_rating: 5,
      general_rating: 9,
      review: "Magnifique propriété dans un endroit calme et paisible",
    },
    {
      name: "Robrecht",
      date: "2023-10-13",
      nature_rating: 5,
      general_rating: 9,
      review:
        "Eindeloos wandelen in bossen en langs weides. Hier wordt men echt één met de natuur! ",
    },
  ];
</script>

<div>
  {#each reviews as review}
    <p id="scroll-text">
      <span>{review.name}</span>
      {review.general_rating} / 10
      {review.review}
    </p>
  {/each}
</div>

<style lang="scss">
  #scroll-text {
    -moz-animation: my-animation 20s linear infinite;
    -webkit-animation: my-animation 20s linear infinite;
    animation: my-animation 20s linear infinite;
  }

  @keyframes my-animation {
    from {
      -moz-transform: translateX(200%);
      -webkit-transform: translateX(200%);
      transform: translateX(200%);
    }
    to {
      -moz-transform: translateX(-200%);
      -webkit-transform: translateX(-200%);
      transform: translateX(-200%);
    }
  }

  div {
    position: relative;
    width: 100vw;
    margin-top: var(--gap);
    margin-bottom: 5rem;
    background-color: var(--blue);
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  span {
    color: var(--darkGreen);
    font-family: "Fraunces", serif;
    font-weight: 800;
  }

  p {
    min-width: 70vw;
    color: var(--darkGreen);
    padding: 2rem;
    font-size: 2rem;
  }
</style>
