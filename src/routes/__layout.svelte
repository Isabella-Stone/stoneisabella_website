<script>
    import Socials from '../components/socials.svelte';
    import { page } from "$app/stores";
    import '../app.css';
</script>

<svelte:head>
    <title>Isabella Stone</title>
</svelte:head>   

<style>
    ul {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        list-style: none
    }

    nav a {
        float: none;
        color: #000000;
        text-align: center;
        padding: 14px 16px;
        text-decoration: none;
        /* font-size: 17px; */
        font-size: 1.2vw;
    }

    nav a:hover {
        background-color: rgb(237, 232, 232);
        color: black;
    }

    .active {
        color: black;
        background-color: rgb(196, 193, 193);
    }

    .container {
        display: grid;
        font-family: "Montserrat", sans-serif;
        place-items: center;  
        text-align: center;
        padding-right: 15px;
    }

    .title {
        font-weight: 800;
        font-size: 1.5vw;
        text-transform: uppercase;
    }

    html {
        height: 100%;
        box-sizing: border-box;
    }

    body {
        position: relative;
        margin: 0;
        min-height: 100%;
        padding-bottom: 4.74rem;
        box-sizing: inherit;
    }

    main {
        width: 80%;
        margin: 0 auto;
        padding-top: 32px;
    }

    footer {
        padding: 35px; 
        position:absolute;
        right: 0;
        left: 0;
        bottom: 0;        
    }

    /* adjust styling for smaller screens */
    @media (max-width: 820px) {
        .container {
            display: grid;
            font-family: "Montserrat", sans-serif;
            place-items: center;  
            text-align: center;
            padding-right: 15px;
            padding-top: 15px;
        }

        nav a {
            font-size: 2.5vw;
        }
    }
</style>

<!-- svelte-ignore a11y-missing-attribute -->
<html>
    <div class="container">
        <h1 class="title">
            <nav>
                <ul>
                    <li> <a class:active={$page.url.pathname === "/"} sveltekit:prefetch href="/">Home</a> </li>
                    <li> <a class:active={$page.url.pathname === "/about"} sveltekit:prefetch href="/about">About Me</a> </li>
                    <li> <a class:active={$page.url.pathname === "/resume"} sveltekit:prefetch href="/resume">Resume</a> </li>
                    <li> <a class:active={$page.url.pathname === "/projects"} sveltekit:prefetch href="/projects">My Projects</a> </li>
                </ul>
            </nav>
        </h1>
    </div>
   
    <body>
        <main>
            <slot />
        </main>
    </body>
    
    <footer>
        <Socials />
    </footer>
</html>


