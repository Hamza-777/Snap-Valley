<script>
  export let disabled;
</script>

<button type="submit" {disabled}>Post</button>

<style>
  button {
    width: 75px;
    height: 35px;
    border-radius: 10px;
    border: none;
    outline: none;
    background-color: #6ddccf;
    cursor: pointer;
  }

  button:disabled {
    background-color: #777;
    cursor: auto;
    color: #000;
  }
</style>
