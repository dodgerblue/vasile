<script>
	import Header from "./Header.svelte";
	import User from "./User.svelte";
	import Categories from "./Categories.svelte";
	import Government from "./Government.svelte";
	import ImgPage from "./ImgPage.svelte";
	let currentPage = "index";
	const goBack = () => (currentPage = "index");
</script>

<main>
	<Header />
	<User />
	{#if currentPage != "index"}
	<div class="back-button">
		<button  on:click={goBack}>BACK</button>
	</div>
	{/if}
	{#if currentPage == "index"}
		<Categories bind:page={currentPage} />
	{:else if currentPage == "government"}
		<Government />
	{:else if currentPage == "weather"}
		<ImgPage source="weather.png" />
	{:else if currentPage == "food"}
		<ImgPage source="restaurants.png" />
	{:else if currentPage == "transport"}
		<ImgPage source="transport.png" />
	{/if}
</main>

<style>
.back-button {
	text-align: center;
}
</style>
