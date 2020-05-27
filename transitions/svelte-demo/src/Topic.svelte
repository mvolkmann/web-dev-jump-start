<script>
  export let title;
  export let description;

  let show = false;

  $: classes = 'topic' + (show ? ' show' : '');

  const handleClick = () => (show = !show);
</script>

<div class="{classes}">
  <header>
    <div class="title">{title}</div>
    <button class="toggle" on:click="{handleClick}">&#x25b6;</button>
  </header>
  <section>{description}</section>
</div>

<style>
  .topic {
    box-shadow: 5px 5px 5px #666;
    display: inline-block;
    background-color: cornflowerblue;
    border-radius: 1rem;
    color: white;
    margin: 0 1rem 1rem 0;
    padding: 1rem;
    vertical-align: top;
    width: 350px;
  }

  .topic > header {
    display: flex;
    justify-content: space-between;
    align-items: center;

    font-size: 1.5rem;
    font-weight: bold;
  }

  .topic > header > button {
    background-color: transparent;
    border: none;
    color: inherit;
    font-size: 2rem;
    margin: 0;
    outline: none;
    transition-duration: 0.5s;
    transition-property: transform;
    transform: rotate(0deg);
  }

  .topic.show > header > button {
    transform: rotate(90deg);
  }

  .topic > section {
    background-color: orange;
    margin-top: 0;
    max-height: 0;
    padding: 0 0.5rem;
    overflow-y: hidden;
    transition-duration: 0.5s;
    transition-property: margin-top, max-height, padding;
  }

  .topic.show > section {
    margin-top: 1rem;
    max-height: 100vh;
    padding-bottom: 0.5rem;
    padding-top: 0.5rem;
  }
</style>
