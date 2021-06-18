<script lang="ts">
    export let title, imageDesc, imageSource, description, v, i;
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();
    function handleClick() {
      v += 1;
      dispatch('message', {
			  value: v,
        iter:i
		  });
    }
</script>

<main>
  <div class="card">
    <div class="title">{title}</div>
    <div>
        <img class="image" alt={imageDesc} src={imageSource}/>
    </div>
    <div class="text">
        <p class="desc">{description}</p>
    </div>
    <button on:click="{handleClick}" class="button">Click Here ({v}) </button>
  </div>
</main>

<style>
  .card{
    padding: 5px 5px;
    border-radius: 20px;
    border: 1px solid black;
    display: inline-block;
    margin: 15px 15px;
    font-size: 1rem;
    font-weight:600;
    background-color: pink;
    align-items: center;
    text-align: center;
    max-width: 350px !important;
    max-height: 350px;
  }
  .title {
    text-align: center;
    color:black;
    font-weight:700;
  }
	.image{
    display: inline-block;
    width: min(200px, 75%) !important;
    margin: 10px auto;
    border: 5px solid white;
  }
  .button{
    background-color:khaki;
    border-radius: 8px;
    border-color:black;
  }
</style>