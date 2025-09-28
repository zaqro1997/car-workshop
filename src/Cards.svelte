<script>
  import Phone from "./Phone.svelte";

  const services = [
    { title: "პროგრამირება დიაგნოსტიკა ელექტროობა", description: "ძრავის და კოლოფის პროგრამირება, DPF(საჟავოის) პრორგამულად გაუქმება,  სთეიჯების ჩაწერა, კომპიუტერის კლონირება, კომპიუტერული დიაგნოსტიკა,ელექტროობის პრობლემის მოგვარება...", tel: '599908345' },
    { title: "სამღებრო", description: "დეტალების დამუშავება და შეღებვა,მანქანის მთლიანად შეღებვა", tel: '555563569' },
    { title: "სათუნუქე სამუშაოები", description: "რობოტზე მანქანის გაჭიმვა თუნუქის დეტალების გასწორება", tel: '558863535'},
    { title: "პლასტმასის აღდგენა", description: "ნებისმიერი დაზიანების პლასტმასის აღდგენა,მანქანის დაშლა-აწყობა ",tel: '598710831' },
    { title: "პოლირება", description: "მანქანის პოლირება, ფარების აღდგენა პოლირება", tel:'551309944'},
  ];
</script>

<div class="services">
  {#each services as service}
    <div class="service-card">
      <h3>{service.title}</h3>
      <p>{service.description}</p>
      {#if service?.tel}
        <a href={`tel:${service.tel}`} class="service-phone">
          <Phone color="#fff" />
            {service.tel}
          </a>
      {/if}
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
      padding: 0 8px;
      display: flex;
      flex-direction: column;
      align-items: center;
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

      .service-phone {
        display: flex;
        gap: 8px;
        padding-bottom: 8px;
        margin-top: auto;
        align-items: center;
      }
    }

    @media (max-width: 768px) {
      grid-template-columns: 1fr;
    }
  }
</style>
