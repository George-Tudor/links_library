<script>

    import LinkItem from "./LinkItem.svelte";

    export let links;
</script>

<section id="links">
    {#each links as link}
        <LinkItem
                title={link.title}
                description={link.description}
                url={link.url}
                imageUrl={link.imageUrl}
                notes={link.notes}
                tags={link.tags}
            />
    {/each}
</section>

<style>
    section {
        width: 100%;
        display: grid;
        grid-template-columns: 1fr;
        grid-gap: 1rem;
    }

    @media (min-width: 768px) {
        section {
            grid-template-columns: repeat(2, 1fr);
        }
    }
</style>
