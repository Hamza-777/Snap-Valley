<script>
  export let posts;

  import PostItem from './PostItem.svelte';
</script>

<div class="container">
  {#each posts as post (post.id)}
    <PostItem item={post} />
  {/each}
</div>
