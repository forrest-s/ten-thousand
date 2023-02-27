<script>
    import GamesHeader from "$lib/components/GamesHeader.svelte";
</script>

<section>
	<GamesHeader />
    <main>Games</main>
    <aside>
        <slot />
    </aside>
</section>

<style>
    section {
        display: grid;
        grid-template-columns: repeat(2, auto);
        grid-template-rows:  repeat(2, auto);
    }
</style>