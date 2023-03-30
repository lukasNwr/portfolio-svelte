<script>
  // @ts-nocheck

  import { scrollRef } from "svelte-scrolling";
  import Footer from "../../components/footer.svelte";
  import Header from "../../components/header.svelte";
  import About from "../about/+page.svelte";
  import Hero from "../hero/+page.svelte";
  import Projects from "../projects/+page.svelte";

  let blob;

  function handlePointerMove(e) {
    const { clientX, clientY } = e;
    blob.animate(
      {
        left: `${clientX}px`,
        top: `${clientY}px`,
      },
      { duration: 15000, fill: "forwards" }
    );
  }
</script>

<svelte:body on:mousemove={handlePointerMove} />

<div class="blob-wrapper">
  <div id="blob" bind:this={blob} />
</div>
<div id="blur" />
<Header />
<section id="home" class="home" use:scrollRef={"home"}>
  <Hero />
  <About />
  <Projects />
  <Footer />
</section>

<style>
  .blob-wrapper {
    height: 100%;
    width: 100%;
    position: fixed;
    z-index: -1;
  }

  #blob {
    /* background: linear-gradient(to right, rgb(244, 218, 47), rgb(133, 74, 251)); */
    background: linear-gradient(
      -45deg,
      #eed45294,
      #e98f7370,
      #e5739f65,
      #51adcfae,
      #63d4ba9b
    );
    background-size: 200% 200%;
    height: 20rem;
    aspect-ratio: 1;
    position: absolute;
    z-index: -2;
    left: 50%;
    top: 50%;
    translate: -50% -50%;
    border-radius: 50%;
    animation: blob-animation 20s infinite;
  }

  #blur {
    height: 100%;
    width: 100%;
    position: fixed;
    z-index: -1;
    backdrop-filter: blur(200px);
  }

  @keyframes blob-animation {
    from {
      rotate: 0deg;
      background-position: 0% 50%;
    }
    25% {
      scale: 1.2 1.3;
    }

    50% {
      scale: 1 1.6;
      background-position: 100% 50%;
    }

    75% {
      scale: 1.1 1.3;
    }
    to {
      rotate: 360deg;
      background-position: 0% 50%;
    }
  }
</style>
