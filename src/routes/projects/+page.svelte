<script>
  // import Card from "../../components/project-card.svelte";
  import { scrollRef } from "svelte-scrolling";
  import Card from "../../components/card.svelte";
</script>

<section id="work" class="projects" use:scrollRef={"work"}>
  <h3 class="title">Some of my works...</h3>
  <div class="cards">
    <Card
      title="Emdit"
      imageName="Emdit_welcome_1"
      github={true}
      livePage={true}
      description="Emdit is a simple online editor for markdown text with live previews, importing and exporting files and simple and intuitive UI."
      gitUrl="https://github.com/lukasNwr/markdown-editor/tree/main"
      liveUrl="https://markdown-editor-cyan.vercel.app/"
    />
    <Card
      title="Project Ellen"
      imageName="ellen"
      github={true}
      livePage={false}
      description="Project Ellen is a simple 2D action game in style the old Alien Breed games, where you have through the level to kill the boss and save the space station!"
      gitUrl="https://github.com/lukasNwr/markdown-editor/tree/main"
      liveUrl=""
    />
    <Card
      title="Humanoid Robot"
      imageName="robot_1"
      github={true}
      livePage={true}
      description="This project was done as a school assignment. The goal was to create a website that would allow to create animation for 3D robot and then play, export and import this animation."
      gitUrl="https://glitch.com/edit/#!/pg-lukasnovorolnik"
      liveUrl="https://pg-lukasnovorolnik.glitch.me"
    />
    <Card
      title="Emdit"
      imageName="Emdit_welcome_1"
      github={true}
      livePage={true}
      description="Emdit is a simple online editor for markdown text with live previews, importing and exporting files and simple and intuitive UI."
      gitUrl="https://github.com/lukasNwr/markdown-editor/tree/main"
      liveUrl="https://markdown-editor-cyan.vercel.app/"
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
