<script lang="ts">
  export let name: string;
  export let icon: string;
  export let color: string = "#363636";
  export let url: string;
</script>

<a href={url} target="_blank">
  <div class="link-icon" style="background-color: {color}">
    <i class={icon} />
  </div>
  <div class="link-name">
    {name}
  </div>
</a>

<style>
  a {
    display: flex;
    color: white;
    text-decoration: none;
    text-align: center;
    transition: filter 0.3s;
  }

  a:hover {
    filter: brightness(120%);
  }

  .link-icon {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 50px;

    font-size: 120%;

    padding: 5px;
    margin-right: 3px;
    border-top-left-radius: 5px;
    border-bottom-left-radius: 5px;
  }

  .link-name {
    flex: 1;
    padding: 15px;
    border-top-right-radius: 5px;
    border-bottom-right-radius: 5px;
    background-color: #363636;
  }
</style>
