<script>
  import { createEventDispatcher } from 'svelte';
  import { fade, scale } from 'svelte/transition';
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
      <div in:scale out:fade={{ duration: 500 }}>
        <PostItem item={post} on:on-delete={handleDelete} />
      </div>
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
