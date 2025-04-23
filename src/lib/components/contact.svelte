<script>
  //icons
  import natuurhuisje from "$lib/icons/natuurhuisje.svg";
</script>

<div id="contact">
  <h3>Interesse of meer vragen over de gite, contacteer ons zeker</h3>
  <div id="cta">
    <div class="button">
      <a href="https://forms.gle/b1AZe5dRqyMp43vh6">Contacteer ons</a>
    </div>
    <div class="button">
      <a href="https://www.natuurhuisje.be/vakantiehuisje/69763"
        ><img src={natuurhuisje} /></a
      >
    </div>
  </div>
</div>

<style lang="scss">
  #contact {
    display: flex;
    flex-direction: column;
    flex: 1;
    margin-left: 2rem;
    padding: 3rem;
    border-radius: var(--borderRadius);
    background-color: var(--pink);
    color: var(--purple);
    font-family: Fraunces;
    font-size: 2.5rem;
  }

  #cta {
    flex: 1;
    display: flex;
    align-items: flex-end;
    justify-content: space-between;
  }

  .button {
    border-radius: 1rem;
    padding: 1rem 2rem;
    color: white;
    background-color: var(--purple);
    font-weight: 600;
    display: flex;
    align-items: center;
    justify-self: center;
    text-align: center;

    a {
      text-decoration: none;
      color: inherit;
      display: flex;
      align-items: center;
      justify-content: center;
      width: 100%;
      height: 100%;
      font-size: 2rem;

      img {
        width: 15rem;
        height: auto;
      }
    }
  }
</style>
