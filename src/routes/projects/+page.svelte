<script>
  // import Card from "../../components/project-card.svelte";
  import { scrollRef } from "svelte-scrolling";
  import Card from "../../components/card.svelte";
</script>

<section id="work" class="projects" use:scrollRef={"work"}>
  <h3 class="title">Some of my works...</h3>
  <div class="cards">
    <Card />
    <Card />
    <Card />
    <Card />
  </div>
</section>

<style>
  .projects {
    width: 100%;
    padding-bottom: 5rem;
    padding-top: 5rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 2rem;
  }

  .title {
    width: 50%;
    color: white;
    font-size: 2.5rem;
    font-family: "Alice";
  }

  .cards {
    width: 65%;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 2rem;
  }
</style>
