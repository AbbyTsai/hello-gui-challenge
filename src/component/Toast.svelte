<script>
	import { createEventDispatcher } from 'svelte';


	const dispatch = createEventDispatcher();

	export let yell;
	
	function deleteYell(id) {
		dispatch('change', {
			id
		});
	}
	
	setTimeout(function() {
      deleteYell(yell.id)
   }, 1000)
</script>


<p class='say' style="transform: rotate({yell.rotation}deg) ">
	
	<a href={yell.ref}>{yell.yell}</a>
</p>

<style>
	p {
		background:pink;
		width: 200px;
		animation: slide-in 2s;

	}
	@keyframes slide-in {
  0% {
    transform: translateY(-1em) rotate(-0.5turn) scale(0.5);
  }
  20%,
  100% {
    transform: translateY(0) rotate(10deg) scale(1);
  }
}
	@keyframes fade-in {
  from { opacity: 0 }
}

</style>