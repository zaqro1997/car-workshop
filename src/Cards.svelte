<script>
  const services = [
    { title: "სერვისი 1", description: "აღწერა 1" },
    { title: "სერვისი 2", description: "აღწერა 2" },
    { title: "სერვისი 3", description: "აღწერა 3" },
    { title: "სერვისი 1", description: "აღწერა 1" },
    { title: "სერვისი 2", description: "აღწერა 2" },
    { title: "სერვისი 3", description: "აღწერა 3" },
    { title: "სერვისი 1", description: "აღწერა 1" },
    { title: "სერვისი 2", description: "აღწერა 2" },
    { title: "სერვისი 3", description: "აღწერა 3" },
  ];
</script>

<div class="services">
  {#each services as service}
    <div class="service-card">
      <h3>{service.title}</h3>
      <p>{service.description}</p>
    </div>
  {/each}
</div>

<style lang="scss">
  .services {
    display: grid;
    padding: 0 20px;
    grid-template-columns: repeat(3, 1fr);
    gap: 25px;

    .service-card {
      background-color: #f00000;
      height: 370px;
      border-radius: 24px;

      &:hover {
        transform: translateY(-10px);
        transition: transform 0.4s ease;
      }

      @media (max-width: 768px) {
        &:hover {
          transform: none;
        }
      }
    }

    @media (max-width: 768px) {
      grid-template-columns: 1fr;
    }
  }
</style>
