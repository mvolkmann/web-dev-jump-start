<script>
  import Topic from './Topic.svelte';

  const topics = [
    {
      title: 'CSS Transitions',
      description: `
        CSS transitions provide a way to control
        animation speed when changing CSS properties.
        Instead of having property changes take effect immediately,
        you can cause the changes in a property
        to take place over a period of time.
      `
    },
    {
      title: 'CSS Flexible Box Layout',
      description: `
        CSS Flexible Box Layout is a module of CSS that defines a CSS box model
        optimized for user interface design, and the layout of items in
        one dimension.  In the flex layout model, the children of a
        flex container can be laid out in any direction, and can “flex” their
        sizes, either growing to fill unused space or shrinking to avoid
        overflowing the parent.  Both horizontal and vertical alignment of
        the children can be easily manipulated.
      `
    }
  ];
</script>

{#each topics as {title, description}}
  <Topic {title} {description} />
{/each}

<style>
  :global(body) {
    background-color: linen;
    font-family: sans-serif;
    padding: 1rem;
  }

  @media (max-width: 640px) {
    :global(body) {
      display: flex;
      flex-direction: column;
    }
  }
</style>
