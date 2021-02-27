<script>

</script>

<nav>
    <span class="nav-title">BookMe</span>
    <input type="checkbox" id="icon-menu" class="menu-icon">
    <label class="text-menu-icon" for="icon-menu">
        <svg
        width="24"
        height="24"
        viewBox="0 0 24 24"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M4 6C4 5.44772 4.44772 5 5 5H19C19.5523 5 20 5.44772 20 6C20 6.55228 19.5523 7 19 7H5C4.44772 7 4 6.55228 4 6Z"
          fill="currentColor"
        />
        <path
          d="M4 18C4 17.4477 4.44772 17 5 17H19C19.5523 17 20 17.4477 20 18C20 18.5523 19.5523 19 19 19H5C4.44772 19 4 18.5523 4 18Z"
          fill="currentColor"
        />
        <path
          d="M11 11C10.4477 11 10 11.4477 10 12C10 12.5523 10.4477 13 11 13H19C19.5523 13 20 12.5523 20 12C20 11.4477 19.5523 11 19 11H11Z"
          fill="currentColor"
        />
      </svg>
    </label>
    <ul class="m1">
        <li><a class="nav-link" href="/">Home</a></li>
        <li><a class="nav-link" href="/">Categorias</a></li>
        <li><a class="nav-link" href="#?">Buscar</a></li>
        <li><a class="nav-link" href="/">Ingresar</a></li>
    </ul>
</nav>

<style>
    nav{
        padding: .2rem .8rem;
        position: relative;
        display: flex;
        align-items: center;
        justify-content: space-between
    }
    nav * {
        display: inline-block;
    }

    .nav-title{
        font-weight: 900;
        font-size: 1.7em;
        color: #292929;
        font-variant: small-caps;
    }
    .nav-link{
        color: #292929;
        opacity: .9;
        text-decoration: none;
        font-weight: 500;
        padding: 0 5px;
    }
    .menu-icon, .text-menu-icon{
        display: none;
    }

    .m1{
        margin: 0;
    }

    @media (max-width: 640px) {
        .text-menu-icon{display: inline-block;}
        .nav-title{
            font-size: 1.5em;
        }
		.m1 {
            position: absolute;
            right: 0;
            top: 35px;
			display: none;
            flex-direction: column;
            padding: 0 1rem;
            background: #fff;
            z-index: 9;
            padding-bottom: .5rem;
		}.m1 li{
            padding: .3rem 0;
        }

        .menu-icon:checked ~ .m1 {
            display: flex;
        }
	}

</style>