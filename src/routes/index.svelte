<script>
    let filename
    const getCurrentFile = input => {
        const split = input.split(/[\\/]/)
        return split.splice(split.length - 2, split.length).join('/')
    }
    try {
        // Should output `server/server.js` if run inside Node
        filename = getCurrentFile(__filename)
    } catch (error) {
        console.log(error)
        // Should output something like `client/client.c11ed98a.js` if run inside browser
        filename = getCurrentFile(document.scripts[document.scripts.length-1].src)
    }
    const style = `<style location="${filename}">p { color: blue; }</style>`
</script>

<style>
	h1, figure, p {
		text-align: center;
		margin: 0 auto;
	}

	h1 {
		font-size: 2.8em;
		text-transform: uppercase;
		font-weight: 700;
		margin: 0 0 0.5em 0;
	}

	figure {
		margin: 0 0 1em 0;
	}

	img {
		width: 100%;
		max-width: 400px;
		margin: 0 0 1em 0;
	}

	p {
		margin: 1em auto;
	}

	@media (min-width: 480px) {
		h1 {
			font-size: 4em;
		}
	}
</style>

<svelte:head>
	<title>Sapper project template</title>
    {@html style}
</svelte:head>

<h1>Great success!</h1>

<figure>
	<img alt='Success Kid' src='successkid.jpg'>
	<figcaption>Have fun with Sapper!</figcaption>
</figure>

<p><strong>Try editing this file (src/routes/index.svelte) to test live reloading.</strong></p>
