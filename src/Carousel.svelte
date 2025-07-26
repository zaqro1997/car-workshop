<script>
  import Carousel from "svelte-carousel";
  import audi from "./media/logos/audi.png";
  import bmw from "./media/logos/BMW.png";
  import cadillac from "./media/logos/Cadillac.png";
  import ford from "./media/logos/Ford.png";
  import gm from "./media/logos/gm.png";
  import honda from "./media/logos/Honda.png";
  import infinity from "./media/logos/Inifiniti.png";
  import jaguar from "./media/logos/Jaguar.png";
  import landRover from "./media/logos/Land-Rover.png";
  import lexus from "./media/logos/Lexsus.png";
  import mercedes from "./media/logos/merc.png";
  import mini from "./media/logos/mini.png";
  import mitsubishi from "./media/logos/Mitsubishi.png";
  import porsche from "./media/logos/porsche.png";
  import subaru from "./media/logos/Subaru.png";
  import toyota from "./media/logos/Toyota.png";
  import volvo from "./media/logos/volvo.png";
  import volkswagen from "./media/logos/VW.png";

  const logos = [
    audi,
    bmw,
    cadillac,
    ford,
    gm,
    honda,
    infinity,
    jaguar,
    landRover,
    lexus,
    mercedes,
    mini,
    mitsubishi,
    porsche,
    subaru,
    toyota,
    volvo,
    volkswagen,
  ];
</script>

<Carousel
  particlesToShow={5}
  particlesToScroll={2}
  autoplay
  autoplayDuration={2000}
  arrows={false}
>
  {#each logos as logo}
    <div class="card">
      <img src={logo} alt="Car Logo" />
    </div>
  {/each}
</Carousel>

<style>
  .card {
    padding: 8px;
    display: flex;
    justify-content: center;

    img {
      @media (max-width: 768px) {
        width: 50%;
      }
    }
  }
</style>
