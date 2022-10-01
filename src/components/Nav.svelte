<script lang="ts">
  const songs = [
    {
      id: "valsa",
      title: "Valsa",
    },
    {
      id: "meandro",
      title: "Meandro",
    },
    {
      id: "terra-de-ninguém",
      title: "Terra de ninguém",
    },
    {
      id: "história-de-acordar",
      title: "História de acordar",
    },
    {
      id: "nobre-ruína",
      title: "Nobre Ruína",
    },
    {
      id: "terra-de-ninguém-1",
      title: "Terra de ninguém",
    },
    {
      id: "entretanto",
      title: "Entretanto",
    },
    {
      id: "se-eu-me-bastasse",
      title: "Se eu me bastasse",
    },
    {
      id: "sigo-o-caminho",
      title: "Sigo o caminho",
    },
    {
      id: "natal-segundo-isaías",
      title: "Natal segundo Isaías",
    },
  ];

  let hidden = true;

  function toggleNav() {
    if (hidden) {
      hidden = false;

      document.querySelector("body").style.overflow = "hidden";
    } else {
      hidden = true;

      document.querySelector("body").style.overflow = "auto";
    }
  }
</script>

<button class="toggle-btn" on:click={toggleNav}>
  <span />
  <span />
  <span />
</button>
<nav class="nav" class:hide-nav={hidden}>
  {#each songs as song}
    <a class="link" href={`#${song.id}`} on:click={toggleNav}>{song.title}</a>
  {/each}
</nav>

<style>
  .hide-nav {
    display: none;
  }
  .toggle-btn {
    position: fixed;
    top: 24px;
    right: 16px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    width: 1.2em;
    height: 1em;
    border: 0;
    background: none;
    padding: 0;
    z-index: 2;
  }
  .toggle-btn span {
    width: 100%;
    height: 2px;
    display: block;
    background-color: var(--color-offwhite);
  }
  .nav {
    position: fixed;
    top: 0;
    bottom: 0;
    width: 100%;
    height: 100%;
    padding: 16px;
    background-color: var(--color-offblack);
  }
  .link {
    display: block;
    width: fit-content;
    color: var(--color-offwhite);
    margin-bottom: 16px;
  }

  @media screen and (min-width: 1000px) {
    .hide-nav {
      display: block;
    }
    .toggle-btn {
      display: none;
    }
    .nav {
      width: 200px;
      left: 36px;
      top: 24px;
      background-color: none;
    }
    .link {
      color: var(--color-faint-white);
    }
  }
</style>
