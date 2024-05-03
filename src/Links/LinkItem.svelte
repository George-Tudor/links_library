<script>
    import {createEventDispatcher} from "svelte";

    export let link;
    const dispatch = createEventDispatcher();

</script>

<article>
    <button class="close-btn" on:click={() => dispatch("delete", link)}>&times;</button>
    <header>
        <h1>{link.title}</h1>
        <h2>{link.description}</h2>
        <h3>{link.url}</h3>
    </header>
    <div class="image">
        <img src="{link.imageUrl}" alt="{link.title} picture">
    </div>
    <div class="content">
        {#if link.userNotes !== undefined}
            <h3>Notes</h3>
            <p>{link.userNotes}</p>
        {/if}
        {#if link.tags !== undefined}
            <h3>Tags</h3>
            <p>{link.tags}</p>
        {/if}
    </div>
    <footer>
        <button>Add Tag</button>
        <button>Edit Notes</button>
    </footer>
</article>

<style>
    article {
        box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
        border-radius: 5px;
        background: white;
        margin: 1rem;
        position: relative;
    }

    header,
    .content,
    footer {
        padding: 1rem;
    }

    .close-btn {
        font-size: 16px;
        color: black;
        background-color: white;
        cursor: pointer;
        padding: 3px 6px;
        border-radius: 2px;
        position: absolute;
        right: 0;
    }


    .image {
        width: 100%;
        height: 14rem;
    }

    .image img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    h1 {
        font-size: 1.25rem;
        margin: 0.5rem 0;
        font-family: "Roboto Slab", sans-serif;
    }

    h2 {
        font-size: 1rem;
        color: #808080;
        margin: 0.5rem 0;
    }

    p {
        font-size: 1.25rem;
        margin: 0;
    }

    div {
        text-align: right;
    }
</style>
