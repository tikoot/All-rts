<script>
  import LightButton from "../UI/Buttons/LightButton.svelte"
</script>

<section class="bg-background-primary py-10 max-md:py-2">
  <div class="divider">
    <div class="shadow" />
    <div class="flex items-center">
      <h1
        class="relative flex-1 max-h-[200px] text-white max-sm:text-[16px] max-sm:py-6 max-md:pl-4 max-md:text-[20px] max-lg:pl-12 max-lg:text-[25px] max-lg:py-10 max-xl:text-[35px] max-xl:pl-20 text-[40px] pl-[220px] font-woodford py-16"
      >
        DOWNLOAD THE GAME NOW!
      </h1>
      
      <LightButton
        text="Download"
        href="/"
        class="py-6 px-7 max-lg:px-4 max-sm:py-2 max-sm:px-4 ml-8 max-md:mr-4 max-lg:mr-12 mr-40"
      />
    </div>
  </div>
</section>

<style>
  .divider {
    position: relative;
    z-index: 10;
    background: linear-gradient(268deg, #ad7636 -1.99%, #4b261a 102.16%);
  }
  .divider::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 5px;
    background: #e3b26d;
    background: linear-gradient(
      271deg,
      rgba(177, 100, 76, 0) 12.88%,
      #e39e6d 65.58%
    );
  }

  .shadow {
    position: absolute;
    top: 0;
    right: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(450deg, rgba(0, 0, 0, 0) 0%, #190e0a 90%);
  }
</style>
