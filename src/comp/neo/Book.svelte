<script>
import { append } from 'svelte/internal';

    import * as books from './../../data/book.json';
    let book = books.books;
    export let value;

    let isbn = book[value].isbn;
    let title = book[value].title;
    let subtitle = book[value].subtitle;
    let author = book[value].author;
    let published = book[value].published;
    let publisher = book[value].publisher;
    let pages = book[value].pages;
    let description = book[value].description;
    let website = book[value].website;
    let pdf = book[value].downloads[0].link;
    let thumbnail = book[value].thumbnail;

    
</script>

<label for={isbn}>
    <input type="radio" class="man" id={isbn} name="book">
    <article>
        <div class="front">
            <img src={thumbnail} alt={title}>
            <div class="data">
                <a class="title" href={pdf}>{title}</a>
                <p class="author">{author} | {publisher}</p>
            </div>
        </div>
        <div class=diff>
            <div class="back">
                <button class="close" onclick="document.getElementById({isbn}).checked=false"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M16.3394 9.32245C16.7434 8.94589 16.7657 8.31312 16.3891 7.90911C16.0126 7.50509 15.3798 7.48283 14.9758 7.85938L12.0497 10.5866L9.32245 7.66048C8.94589 7.25647 8.31312 7.23421 7.90911 7.61076C7.50509 7.98731 7.48283 8.62008 7.85938 9.0241L10.5866 11.9502L7.66048 14.6775C7.25647 15.054 7.23421 15.6868 7.61076 16.0908C7.98731 16.4948 8.62008 16.5171 9.0241 16.1405L11.9502 13.4133L14.6775 16.3394C15.054 16.7434 15.6868 16.7657 16.0908 16.3891C16.4948 16.0126 16.5171 15.3798 16.1405 14.9758L13.4133 12.0497L16.3394 9.32245Z" fill="currentColor"/> <path fill-rule="evenodd" clip-rule="evenodd" d="M1 12C1 5.92487 5.92487 1 12 1C18.0751 1 23 5.92487 23 12C23 18.0751 18.0751 23 12 23C5.92487 23 1 18.0751 1 12ZM12 21C7.02944 21 3 16.9706 3 12C3 7.02944 7.02944 3 12 3C16.9706 3 21 7.02944 21 12C21 16.9706 16.9706 21 12 21Z"fill="currentColor"/></svg></button>
                <div class="box">
                    <div class="info">
                        <header>
                            <img src={thumbnail} alt={title}>
                            <div>
                                <span class="title">{title}</span>
                                <span class="author">{subtitle} | {author}</span>
                                <br>
                                <span class="prevtext">ISBN</span>
                                <p>{isbn}</p>
                                <span class="prevtext">Fehca de publicacion</span>
                                <p>{published}</p>
                                <span class="prevtext">Editorial</span>
                                <p>{publisher}</p>
                                <span class="prevtext">Paginas</span>
                                <p>{pages}</p>
                                <span class="prevtext">Website</span>
                                <a href={website}>Here</a>
                            </div>
                        </header>
                        <h3>Descripcion</h3>
                        <p>{description}</p>
                        <h3>Descargar</h3>
                        <div id="download">
                            {#each book[value].downloads as type, i }
                                <a class="downloadFile" href={book[value].downloads[i].link}>{book[value].downloads[i].type}</a>
                            {/each}
                        </div>
                    </div>
                </div>
                <a href={pdf} class="read">Leer ahora</a>
            </div>
        </div>
    </article>
</label>


<style>
    p{margin: 0; word-wrap: break-word;}
    br{margin-top:1rem; display:block}
    label{
        width: calc(100% - 10px);
        height: 80px;
        padding: 5px;
        display: flex;
        align-items: center;
    }label article .front{
        display: grid;
        grid-template-columns: 15% 1fr;
        text-align: left;
        padding: 5px 0;
        justify-content: left;
        align-items: center;
    }label article .front img{
        width: 100%;
        height: auto;
    }label article .front .data{
        padding-left: 5px;
    }label article .front .data .title{
        font-weight: 600;
        font-size: 1em;
        color: #333;
        display:block;
        text-decoration: none;
    }label article .front .data .author{
        opacity: .7;
        display:block;
        font-size: .9em;
    }label article .diff{
        display: none;
        position: absolute;
        width: 100%;
        height: 100%;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        background: #1f1f1f91;
        justify-content: center;
        align-items: center;
        z-index: 9;
    }label article .diff .close{
        background: none;
        border: none;
        position: absolute;
        top: .5rem;
        right: 1em;
    }label article .diff .back{
        position: relative;
        display: flex;
        max-width: 500px;
        height: calc(80% - 6rem);
    }label article .diff .back .box {
        padding: 1rem;
        display: flex;
        text-align: left;
        border-radius: 5px;
        flex-direction: column;
        background: #f1f1f1;
        overflow-y: auto;
    }label article .diff .back .info{
        padding-bottom: 3rem;
    }label article .diff .back .info header{
        display: grid;
        grid-template-columns: 40% 1fr;
        text-align: left;
        margin-bottom: 1rem;
        font-size: 1em;
        font-weight: 300;

    }label article .diff .back .info header div{
        padding-left: 10px;
    }label article .diff .back .info header .title{
        font-size: 2em;
        font-weight: 600;
        display:block;
        padding-right: 1rem;
        color: #222;
    }label article .diff .back{
        position: relative;
    }label article .diff .back .info img{
        width: 100%;
        height: auto;
        display: inline-block;
    }label article .diff .back .read{
        position: absolute;
        bottom: .5rem;
        padding: .5rem 1.6rem;
        text-align: center;
        width: 120px;
        right: 1.5rem;
        background: red;
        font-weight: 600;
        color: white;
    }label article .diff .back .info .prevtext{
        display: block;
        color: #333;
        opacity: 1;
        font-weight: 600;
        font-size: .99em;
    }label article .diff .back .info p{
        padding-left: 7px;
        font-size: .9em;
    }
    .man{
        display: none;
    }
    .man:checked ~ article{
        background: #000
    }.man:checked ~ article .diff{
        display: flex;
    }

    .downloadFile{
        padding: 8px 10px;
        background: #444;
        color: white;
        font-size: .9em;
        font-weight: 600;
        margin-left: 5px;
    }
    @media (max-width: 640px){
        label article .front{
            border-bottom: 1px solid #eeeeee;
        }.man:checked ~ article .diff .back{
            position: absolute;
            max-width: calc(100% - 2rem);
            padding: 1.5rem 1rem;
            height: 90vh;
            display: flex;
            border-radius: 15px 15px 0px 0px;
            flex-direction: column;
            bottom: -10px;
            left: 0;
            background: #f1f1f1;
        }label article .diff .back .close{
            position: absolute;
            top:.5rem;
            left: 0;
            right: 0;
            width: 20%;
            margin: auto;
            padding: 4px;
            height: 3px;
            background: #ddd;
            border-radius: 10px;
        }label article .diff .back .close svg{
            display: none;
        }label article .diff .back .read{
            position: absolute;
            width: 100%;
            bottom: 1rem;
            padding: 1rem 2rem;
            margin: 0 .5rem;
            width: calc(100% - 5rem);
            left: 0;
            background: red;
            font-weight: 600;
            color: white;
        }label article .diff .back .info header{
            font-size: .8em;
            font-weight: 300;
        }label article .diff .back .info header .title{
            font-size: 1.7em;
        }

        label article .diff .info .header p{
            font-size: .8em;
        }
    }
</style>