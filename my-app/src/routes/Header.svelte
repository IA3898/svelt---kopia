<script>
    import { page } from '$app/stores';
    import insta from '$lib/images/instagram.svg.png';
    import tik from '$lib/images/github.svg';
</script>

<header>


    <nav>
        <svg viewBox="0 0 2 3" aria-hidden="true">
            <path d="M0,0 L1,2 C1.5,3 1.5,3 2,3 L2,0 Z" />
        </svg>
        <ul>
            <li>
                <a href="https://www.instagram.com/techyumy"><img src={insta} alt="insta" /></a>
            </li>
            <!-- <li aria-current={$page.url.pathname.startsWith('/sverdle') ? 'page' : undefined}>
                <a href="/sverdle"><img src={logo} alt="SvelteKit" /></a>
            </li> -->
        </ul>
        <svg viewBox="0 0 2 3" aria-hidden="true">
            <path d="M0,0 L0,3 C0.5,3 0.5,3 1,2 L2,0 Z" />
        </svg>
    </nav>


</header>

<style>
    header {
        display: flex;
        justify-content: center; /* Align header items to the center horizontally */
        align-items: center; /* Align header items to the center vertically */
        height: 100%; /* Set the height of the header */
    }

    nav {
        display: flex;
        justify-content: center;
        align-items: center; /* Center items vertically */
        --background: rgba(255, 255, 255, 0.7);
            /* Set a large border-radius for more rounded corners */
    }

    svg {
        display: none; /* Hide the svg if it's not being used for layout */
    }

    ul {
    padding: 0.5rem 1rem; /* Add padding to increase the height and maintain spacing */
    margin: 0;
    display: flex;
    justify-content: center;
    align-items: center; /* Center list items vertically */
    list-style: none;
    background: var(--background);
    border-radius: 25px; /* Rounded corners for the navbar */
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2); /* Optional: Add a subtle shadow for depth */
}

    li {
        margin: 0 1rem; /* Add some space between the list items */
    }

    li[aria-current='page']::before {
        /* Adjustments for current page indicator */
        content: '';
        position: absolute;
        top: 100%;
        left: 50%;
        transform: translateX(-50%);
        border: 6px solid transparent;
        border-top-color: var(--color-theme-1);
    }

    nav a {
        display: flex;
        align-items: center; /* Center anchor contents vertically */
        padding: 0 0.5rem;
        font-weight: 700;
        font-size: 0.8rem;
        text-decoration: none;
        transition: color 0.2s linear;
    }

    nav a:hover {
        color: var(--color-theme-1);
    }

    nav img {
        width: auto; /* Maintain the original aspect ratio */
        height: 3rem; /* Set a fixed height to ensure all logos are the same size */
        padding: 0; /* Remove any padding that may be affecting size */
    }
</style>
