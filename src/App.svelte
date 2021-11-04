<script>
  import Header from './components/Header.svelte';
  import PostForm from './components/PostForm.svelte';
  import PostList from './components/PostList.svelte';

  let posts = [
    {
      id: 1,
      image:
        'https://images.ctfassets.net/hrltx12pl8hq/61DiwECVps74bWazF88Cy9/2cc9411d050b8ca50530cf97b3e51c96/Image_Cover.jpg?fit=fill&w=480&h=270',
      text: 'blablabla',
    },
    {
      id: 2,
      image:
        'https://images.ctfassets.net/hrltx12pl8hq/61DiwECVps74bWazF88Cy9/2cc9411d050b8ca50530cf97b3e51c96/Image_Cover.jpg?fit=fill&w=480&h=270',
      text: 'blavlabla',
    },
    {
      id: 3,
      image:
        'https://images.ctfassets.net/hrltx12pl8hq/61DiwECVps74bWazF88Cy9/2cc9411d050b8ca50530cf97b3e51c96/Image_Cover.jpg?fit=fill&w=480&h=270',
      text: 'blablavla',
    },
  ];

  const addPost = (e) => {
    posts = [e.detail, ...posts];
  };
</script>

<main>
  <Header />
  <PostForm on:new-post={addPost} />
  <PostList {posts} />
</main>
