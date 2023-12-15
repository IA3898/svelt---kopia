<script>
import insta from '$lib/images/instagram.svg.png';
	import log from '$lib/images/log.jpg';

	const products = [
        { id: 1, name: 'Product 1', imgUrl: 'path/to/image1.jpg', amazonLink: 'https://amazon.com/product1' },
        { id: 2, name: 'Product 2', imgUrl: 'path/to/image2.jpg', amazonLink: 'https://amazon.com/product2' },
		{ id: 3, name: 'Product 3', imgUrl: 'path/to/image1.jpg', amazonLink: 'https://amazon.com/product1' },
        { id: 4, name: 'Product 4', imgUrl: 'path/to/image2.jpg', amazonLink: 'https://amazon.com/product2' },
		{ id: 5, name: 'Product 5', imgUrl: 'path/to/image1.jpg', amazonLink: 'https://amazon.com/product1' },
        { id: 6, name: 'Product 6', imgUrl: 'path/to/image2.jpg', amazonLink: 'https://amazon.com/product2' },
		{ id: 7, name: 'Product 7', imgUrl: 'path/to/image1.jpg', amazonLink: 'https://amazon.com/product1' },
        { id: 8, name: 'Product 8', imgUrl: 'path/to/image2.jpg', amazonLink: 'https://amazon.com/product2' },
		{ id: 9, name: 'Product 9', imgUrl: 'path/to/image1.jpg', amazonLink: 'https://amazon.com/product1' },
        { id: 10, name: 'Product 10', imgUrl: 'path/to/image2.jpg', amazonLink: 'https://amazon.com/product2' },
        // Add more products as needed
    ];
	
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<h1>
		<span class="welcome">
			<picture>
				<source srcset={log} type="image/webp" />
				<img src={log} alt="Welcome" />
				 
			</picture>
		</span>

		Tech Yumy
	</h1>

	<ul class="product-list">
		{#each products as product}
			<li class="product-item">
				<div class="product-content">
					<img class="product-image" src={product.imgUrl} alt={product.name} />
					<a href={product.amazonLink} target="_blank">{product.name}</a>
				</div>
				<!-- Separator is outside the flexbox that aligns image and text -->
				{#if product.id !== products.length} <!-- Avoid separator after last item -->
					<hr class="separator" />
				{/if}
			</li>
		{/each}
	</ul>



</section>

<style>

.product-list {
        list-style: none;
        padding: 0;
    }

	.product-content {
    display: flex;
    align-items: center;
    /* The rest of your styles for product alignment */
}

    .product-item {

        margin-bottom: 1em;
    }

    .product-image {
        width: 50px; /* Adjust as needed */
        height: 50px; /* Adjust as needed */
        border-radius: 50%; /* Circular image */
        margin-right: 1em;
    }

    .product-item a {
		
        text-decoration: none;
        color: #0073bb; /* Amazon blue, adjust as needed */
        /* Additional styling as needed */
    }
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
		padding: 2em; /* Added padding */
	}

	h1 {
		position: relative; /* Relative positioning to place the icon */
		text-align: center;
		font-size: 3em;
		font-weight: 300;
		margin: 0;
		padding-top: 5em; /* Make space for the icon */
		font-family: 'Roboto', sans-serif;
		color: #555; /* Darker font color for better contrast */
	}

	.welcome {
		display: block;
		position: absolute;
		width: 10%; /* Smaller width for an icon-like appearance */
		top: 0; /* Position at the top of the h1 */
		left: 50%; /* Center horizontally */
		transform: translateX(-50%);
		opacity: 0.8; /* Adjusted for a blend with the background */
		/*Make picture bigger */
		 width: 200px;
		
	}

	.welcome img {
		display: block;
		width: 100%;
		height: auto;
		;
		border-radius: 50%; /* Circular icon */
	}

	/* Assuming your navbar has a class `navbar`, add the following: */
	.navbar {
		border-radius: 25px; /* Rounded corners for the navbar */
		background-color: rgba(255, 255, 255, 0.3); /* Semi-transparent white for a "blended" effect */
		/* Additional styling as needed */
	}

	.separator {
	border: none;
	border-top: 1px solid rgba(0, 0, 0, 0.5); /* The '0.5' at the end controls the transparency */

    width: 100%; /* Full width of the container */
    margin-top: 10px; /* Space above the separator */
    margin-bottom: 10px; /* Space below the separator */
	opacity: 0.5; /* Adjusted for a blend with the background */
}

</style>
