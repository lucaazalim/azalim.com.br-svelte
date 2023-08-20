<script lang="ts">
  import SocialLink from "$lib/SocialLink.svelte";

  let avatar: string;
  let name: string;
  let bio: string;

  fetch("https://api.github.com/users/lucaazalim")
    .then((response) => response.json())
    .then((data) => {
      avatar = data.avatar_url;
      name = data.name;
      bio = data.bio;
    });
</script>

<main>
  <header>
    <img id="avatar" src={avatar} />
    <h1 id="name">{name}</h1>
    <p id="bio">{bio}</p>
  </header>
  <div id="links">
    <SocialLink
      name="GitHub"
      icon="fa-brands fa-github"
      color="#333"
      url="https://github.com/lucaazalim"
    />
    <SocialLink
      name="LinkedIn"
      icon="fa-brands fa-linkedin"
      color="#0077B5"
      url="https://www.linkedin.com/in/luca-azalim-04153999/"
    />
    <SocialLink
      name="Twitter"
      icon="fa-brands fa-twitter"
      color="#1DA1F2"
      url="https://twitter.com/lucaazalim"
    />
    <SocialLink
      name="Threads"
      icon="fa-solid fa-at"
      color="#333"
      url="https://www.threads.net/@lucaazalim"
    />
    <SocialLink
      name="Instagram"
      icon="fa-brands fa-instagram"
      color="#E1306C"
      url="https://www.instagram.com/lucaazalim"
    />
    <SocialLink
      name="Comidas do Luca"
      icon="fa-solid fa-burger"
      color="#E1306C"
      url="https://www.instagram.com/comidasdoluca/"
    />
    <SocialLink
      name="Filmes e séries assistidos"
      icon="fas fa-film"
      color="#1da666"
      url="https://docs.google.com/spreadsheets/d/15niBHmP8eMCLUAH7XefBBk2QyjQj0X57hQSq8tQXaQ0/edit#gid=991418092"
    />
    <SocialLink
      name="Rede Sky"
      icon="fa-solid fa-heart"
      url="https://redesky.com/"
    />
  </div>
</main>

<style>
  :global(body, html) {
    font-family: "Roboto", sans-serif;
    background-color: #020202;
    color: #e7e7e7;

    display: flex;
    justify-content: center;
    align-items: center;
  }

  main {
    max-width: 500px;
    margin: 10px;
  }

  header {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  #avatar {
    width: 200px;
    border-radius: 50%;
    margin-bottom: 1rem;
  }

  #name {
    margin: 0;
  }

  #bio {
    text-align: center;
  }

  #links {
    display: grid;
    gap: 1rem;
  }
</style>
