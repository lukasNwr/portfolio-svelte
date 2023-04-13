<script>
  // @ts-nocheck
  import FaAt from "svelte-icons/fa/FaAt.svelte";
  import FaFacebook from "svelte-icons/fa/FaFacebook.svelte";
  import FaGithubAlt from "svelte-icons/fa/FaGithubAlt.svelte";
  import FaLinkedinIn from "svelte-icons/fa/FaLinkedinIn.svelte";
  import { scrollRef } from "svelte-scrolling";
  import { fade } from "svelte/transition";

  function handleEmailClick() {
    const emailAddress = "lukas.novorolnik@gmai.com";
    const subject = "Portfolio contact";
    const body = "";
    const mailtoLink = `mailto:${emailAddress}?subject=${encodeURIComponent(
      subject
    )}&body=${encodeURIComponent(body)}`;
    window.open(mailtoLink);
  }
</script>

<section id="about" class="about" use:scrollRef={"about"}>
  <div class="content-wrapper">
    <h1 class="title">About me</h1>
    <span class="about-text" transition:fade>
      My name is Lukas. I am passionate and slightly introverted person, who
      loves building things. When I was little, I loved building things with
      lego (and to be honest I still kinda do), because it allowed me to express
      my imagination and transform it into objects in real world. Later music
      took my full focus and I wanted to be a rock star, so I learned to play
      various musical instruments. These days, even though music is still deeply
      in my heart, after I saw couple of episodes of Mr. Robot, I realised that
      I want to learn to code and express myself in that way.
      <br />
      <br />I obtained my Bachelor’s degree in computer science and recently
      started my Master’s degree studies at the University of Southern Denmark
      in Computer Science. I am seeking for a developer role, where I could help
      a company to achieve their goals and perfect my skills as a developer and
      also as a person.
    </span>

    <div class="contact">
      <span
        >If you want to contact me or know more about me, you can to it here...</span
      >
      <div class="icons">
        <div class="gh-icon icon">
          <a href="https://github.com/lukasNwr">
            <FaGithubAlt />
          </a>
        </div>
        <div class="mail-icon icon">
          <button on:click={handleEmailClick}>
            <FaAt />
          </button>
        </div>
        <div class="fb-icon icon">
          <a href="https://www.facebook.com/lukas.novorolnik/">
            <FaFacebook />
          </a>
        </div>
        <div class="li-icon icon">
          <a href="https://www.linkedin.com/in/lukas-novorolnik-4575121aa/">
            <FaLinkedinIn />
          </a>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .contact {
    color: white;
    margin-top: 5rem;
    margin-bottom: 5rem;
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }

  .contact > span {
    font-size: 1rem;
  }

  .icons > .icon > * {
    transition: color 0.3s ease-in-out;
    cursor: pointer;
  }

  .icons > .icon:hover > * {
    color: rgba(222, 222, 222, 0.927);
  }

  .icons {
    display: flex;
    gap: 1.5rem;
  }

  .icon > * {
    color: rgba(133, 133, 133, 0.512);
    text-decoration: none;
  }

  .icon > button {
    background: none;
    border: none;
    height: 45px;
  }

  .icons > .gh-icon,
  .li-icon {
    height: 50px;
  }

  .fb-icon,
  .mail-icon {
    height: 45px;
  }

  .about {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100vw;
    min-height: 100vh;
    background-color: transparent;
  }

  .content-wrapper {
    width: 60vw;
  }

  .title {
    color: white;
    font-size: 4rem;
    font-family: "Alice";
  }

  .about-text {
    color: white;
  }

  @media screen and (max-width: 600px) {
    .content-wrapper {
      width: 70vw;
    }

    .title {
      font-size: 3rem;
    }
  }
</style>
