<script>
  // import Card from "../../components/project-card.svelte";
  import { scrollRef } from "svelte-scrolling";
  import Card from "../../components/card.svelte";
</script>

<section id="work" class="projects" use:scrollRef={"work"}>
  <h3 class="title">Some of my projects...</h3>
  <div class="cards">
    <Card
      title="Project Ellen"
      imageName="project-ellen-tn"
      github={true}
      livePage={false}
      description="Project Ellen is a simple 2D action game in style the old Alien Breed games, where you have through the level to kill the boss and save the space station!"
      gitUrl="https://github.com/lukasNwr/markdown-editor/tree/main"
      liveUrl=""
    />
    <Card
      title="Books App"
      imageName="books-tn"
      github={true}
      livePage={false}
      description="Books is a simple Flutter application for searching books on Google Books. It allows you to search books by title, author or by using your camera to scan barcode of the book you want to search on Google Books."
      gitUrl="https://github.com/lukasNwr/Books-app"
      liveUrl=""
    />
    <Card
      title="Emdit"
      imageName="emdit-tn"
      github={true}
      livePage={true}
      description="Emdit is a simple online editor for markdown text with live previews, importing and exporting files and simple and intuitive UI."
      gitUrl="https://github.com/lukasNwr/markdown-editor/tree/main"
      liveUrl="https://markdown-editor-cyan.vercel.app/"
    />
    <Card
      title="Humanoid Robot"
      imageName="robot-tn"
      github={true}
      livePage={true}
      description="This project was done as a school assignment. The goal was to create a website that would allow to create animation for 3D robot and then play, export and import this animation."
      gitUrl="https://glitch.com/edit/#!/pg-lukasnovorolnik"
      liveUrl="https://pg-lukasnovorolnik.glitch.me"
    />
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
    gap: 1rem;
  }

  .title {
    width: 60vw;
    color: white;
    font-size: 2.5rem;
    font-family: "Alice";
  }

  .cards {
    width: 65vw;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 2rem;
  }

  @media only screen and (max-width: 1090px) {
    .cards {
      width: 80vw;
    }
  }

  @media only screen and (max-width: 600px) {
    .title {
      font-size: 2rem;
      width: 70vw;
    }
  }
</style>
