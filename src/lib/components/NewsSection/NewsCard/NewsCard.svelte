<script>
  import line from "../../../../assets/icons/line.svg"
  import NewsImage from "../NewsImage/NewsImage.svelte"
  import { goto } from "$app/navigation"
  export let imageSrc
  export let logoSrc
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-static-element-interactions -->
<section class="news-card" on:click={() => goto("/card-details")}>
  <div class="image-container">
    <NewsImage src={imageSrc} {logoSrc} />
  </div>
  <div class="content">
    <div>
      <h2 class="title font-cormorantSC">Lorem ipsum dolo...</h2>
      <img src={line} alt="line" class="line pb-2" />
      <p class="description">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam id
        sapien orci.
      </p>
    </div>
    <span class="date font-gilroyBold">1/10/2024</span>
  </div>
</section>

<style>
  .news-card {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    overflow: hidden;
    max-width: 402px;
    height: 462px;
    transition: transform 0.3s ease;
    background: white;
  }

  .image-container {
    width: 100%;
    height: 55%;
    overflow: hidden;
    background: linear-gradient(206deg, #fdf2c8 48.52%, #cfa487 102.62%);
    padding: 2px;
  }

  .content {
    position: relative;
    height: 45%;
    padding: 7px 15px 15px 15px;
    background: linear-gradient(206deg, #fdf2c8 48.52%, #cfa487 102.62%);
    color: white;
  }

  .title {
    color: #562a1d;
    font-size: 35px;
    font-style: normal;
    font-weight: 600;
    line-height: normal;
    letter-spacing: 2px;
  }

  .description {
    color: #75513f;
    font-size: 18px;
    font-weight: 400;
    line-height: 1.2;
  }

  .date {
    position: absolute;
    bottom: 10px;
    left: 15px;
    color: #562a1d;
    font-size: 18px;
    font-weight: 400;
  }

  @media (hover: hover) {
    .news-card:hover {
      transform: scale(1.05);
      box-shadow: 0 8px 12px rgba(0, 0, 0, 0.15);
    }
  }

  @media (max-width: 1200px) {
    .title {
      font-size: 30px;
      letter-spacing: 2.85px;
    }
    .description {
      font-size: 14px;
    }
    .date {
      font-size: 14px;
    }
  }

  @media (max-width: 768px) {
    .news-card {
      max-width: 320px;
      height: 400px;
    }

    .title {
      font-size: 28px;
      letter-spacing: 2.85px;
    }

    .content {
      padding: 7px 10px 10px 10px;
    }
  }

  @media (max-width: 480px) {
    .news-card {
      max-width: 260px;
      height: 350px;
    }

    .title {
      font-size: 24px;
      letter-spacing: 2.5px;
    }

    .description {
      font-size: 0.85rem;
    }

    .date {
      font-size: 0.75rem;
    }
  }
</style>
