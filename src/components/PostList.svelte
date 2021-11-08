<script>
  import { createEventDispatcher } from 'svelte';
  export let posts = '';
  import PostItem from './PostItem.svelte';

  let dispatch = createEventDispatcher();

  const handleDelete = (e) => {
    dispatch('delete-post', e.detail);
  };
</script>

<div class="container">
  {#if posts.length}
    {#each posts as post (post.id)}
      <PostItem item={post} on:on-delete={handleDelete} />
    {/each}
  {:else}
    <p>Currently there are no posts to show</p>
  {/if}
</div>

<style>
  p {
    color: white;
  }
</style>
