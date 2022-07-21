<script>
	import Modal from './Modal.svelte'
	import Component1 from './Component1.svelte'
	import Component2 from './Component2.svelte'
	import Component3 from './Component3.svelte'
	import Component4 from './Component4.svelte'
	// initialise modal state and content
	let showModal = false;
	let modalContent;
	
	// pass in component as parameter and toggle modal state
	function toggleModal(component) {
		modalContent = component;
		showModal = !showModal;
	}
	
</script>
<svelte:head>
	<script src="https://cdn.tailwindcss.com"></script>
</svelte:head>
<section> 
<main class="container mx-auto w-[100vw] flex flex-row space-x-4">


<button class="bg-transparent" on:click={() => (toggleModal(Component1))}>
	<img src="https://via.placeholder.com/150">
	Open 1
</button>

<button on:click={() => (toggleModal(Component2))}>
	<img src="https://via.placeholder.com/150">
	Open 2
</button>
<button on:click={() => (toggleModal(Component3))}>
	<img src="https://via.placeholder.com/150">
	Open 3
</button>
<button on:click={() => (toggleModal(Component4))}>
	<img src="https://via.placeholder.com/150">
	Open 4
</button>
</main>
</section>
{#if showModal}
	<Modal on:click={toggleModal} {modalContent} />
{/if}
<style>
section {
	width: 100vw;
	height: 100vh;

}
main {
	display: flex;
	justify-content: center;
}
</style>