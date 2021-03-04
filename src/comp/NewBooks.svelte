<script>
    import * as books from './../data/book.json';
    import Book from './neo/Book.svelte';
</script>

<section>
    <div class="favorites">
    {#each books.books as isbn, value }
        <Book value={value}/>
	{/each}
    </div>
    <Book value={3}/>
</section>

<style>
    section{
        width: 100%;
        display: grid;
        overflow: hidden;
        align-content: start;
        margin: 1.5rem 0;
    }

    .favorites{
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
        grid-template-rows: 1fr 1fr;
        align-items: center;
        justify-content: center;
        scroll-snap-type: x proximity;

    }
    @media (max-width: 940px){
        .favorites{
            grid-template-columns: 1fr 1fr 1fr 1fr ;
            grid-template-rows: 1fr 1fr 1fr;
            overflow-x: hidden;
        }
    }
    @media (max-width: 840px){
        .favorites{
            grid-template-columns: 1fr 1fr 1fr ;
            grid-template-rows: 1fr 1fr 1fr;
            height: 260px;
            overflow-x: hidden;
        }
    }
    @media (max-width: 740px){
        .favorites{
            grid-template-columns: 1fr 1fr ;
            grid-template-rows: 1fr 1fr 1fr;
            overflow-x: hidden;
        }
    }
    @media (max-width: 640px){
        .favorites{
            grid-template-columns: 1fr ;
            grid-template-rows: 1fr 1fr 1fr;
            overflow-x: hidden;
        }
    }

</style>