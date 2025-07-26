<script lang="ts">
  import Cards from "./Cards.svelte";
  import Carousel from "./Carousel.svelte";
  import Dpf from "./Dpf.svelte";
  import logo from "./media/logo.jpg";
  import Phone from "./Phone.svelte";

  let ref: HTMLDivElement;

  function serviceClick() {
    if (ref) {
      ref.scrollIntoView({ behavior: "smooth" });
    }
  }

  function locationClick() {
    window.location.href = "https://goo.gl/maps/LuumHugs435EHdJN9";
  }
</script>

<main>
  <header>
    <img src={logo} alt="Logo" />
    <h1>ორმოტორსი</h1>
  </header>
  <div class="container-with-image">
    <div class="subtitle">
      <h2>ორმოტორსი</h2>
      <p>თქვენი პიტსტოპი პრემიუმ ავტომომსახურებისთვის</p>
    </div>
    <div class="action-buttons">
      <button onclick={locationClick}>მისამართი</button>
      <button onclick={serviceClick}>სერვისები</button>
      <a href="tel:+995599908345" class="button">
        <Phone />
        599 908 345</a
      >
    </div>
  </div>

  <div class="cards-container">
    <h2>ჩვენ ვაკეთებთ</h2>
    <Carousel />
  </div>
</main>

<div class="services" bind:this={ref}>
  <h2>სერვისები</h2>

  <Cards />
</div>

<!-- <Dpf /> -->

<style lang="scss">
  main {
    width: 100%;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    background-color: white;
  }

  header {
    width: 100%;
    height: 60px;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #fff;
    margin: 1em;

    img {
      width: 50px;
      height: 50px;
      margin-right: 20px;
    }

    h1 {
      color: black;
      font-weight: bold;
      @media (max-width: 768px) {
        font-size: 16px;
      }
    }
  }

  .container-with-image {
    width: 100%;
    height: 60%;
    background-image: url("/background.png");
    background-position: center center;
    background-size: cover;
    padding-bottom: 10em;

    .subtitle {
      display: flex;
      flex-direction: column;
      align-items: center;
      color: #ffffff;
      text-shadow: 0 3px 0 #f70000;
      font-family: "Saira", Sans-serif;
      font-size: 36px;
      font-weight: 600;
      margin-top: 10%;

      h2 {
        color: #f70000;
        text-shadow: none;
      }

      h2,
      p {
        margin: 8px 0;
        text-align: center;

        @media (max-width: 768px) {
          font-size: 16px;
        }
      }
    }
    .action-buttons {
      margin-top: 40px;
      display: flex;
      justify-content: center;
      gap: 20px;

      button,
      .button {
        text-align: center;
        text-decoration: none;
        cursor: pointer;
        border-style: solid;
        border-width: 0;
        border-color: #666;
        background-color: #fff;
        color: #f70000;
        border-radius: 3px;
        padding: 16px 0;
        font-size: 16px;
        font-weight: 600;
        width: 18%;
        font-weight: 600;
      }

      .button {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 4px;
      }

      button:hover,
      .button:hover {
        :global(svg) {
          fill: #fff;
        }
        background-color: #f70000;
        color: #fff;
        transition: background-color 0.3s ease;
      }

      @media (max-width: 768px) {
        flex-direction: column;
        align-items: center;
        gap: 10px;

        button,
        .button {
          width: 255px;
          padding: 12px 0;
        }
      }
    }
  }

  .cards-container {
    margin: 2em 0;

    h2 {
      margin-top: 0;
      text-align: center;
      color: black;
      font-weight: bold;
      font-size: 30px;
      @media (max-width: 768px) {
        font-size: 16px;
      }
    }
  }

  .services {
    h2 {
      text-align: center;
      color: white;
      font-weight: bold;
      font-size: 30px;
      @media (max-width: 768px) {
        font-size: 16px;
      }
    }
  }
</style>
