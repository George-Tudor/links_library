<script>
    export let title;
    export let description;
    export let url;
    export let imageUrl;
    export let userNotes;
    export let tags;
</script>

<article>
    <header>
        <h1>{title}</h1>
        <h2>{description}</h2>
        <h3>{url}</h3>
    </header>
    <div class="image">
        <img src="{imageUrl}" alt="{title} picture">
    </div>
    <div class="content">
        {#if userNotes !== undefined}
            <h3>Notes</h3>
            <p>{userNotes}</p>
        {/if}
        {#if tags !== undefined}
            <h3>Tags</h3>
            <p>{tags}</p>
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
    }

    header,
    .content,
    footer {
        padding: 1rem;
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
