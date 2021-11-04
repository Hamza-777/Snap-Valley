<script>
  export let posts = '';

  import PostItem from './PostItem.svelte';
</script>

<div class="container">
  {#if posts}
    {#each posts as post (post.id)}
      <PostItem item={post} />
    {/each}
  {:else}
    <p>Currently there are no posts to show</p>
  {/if}
</div>
