<script>
	export let segment;
</script>

<style>
	nav {
		border-bottom: 1px solid var(--primary-color);
		font-weight: 300;
		padding: 0 1em;
		display: flex;
		justify-content: space-between;
	}

	ul {
		margin: 0;
		padding: 0;
	}

	/* clearfix */
	ul::after {
		content: '';
		display: block;
		clear: both;
	}

	li {
		display: block;
		float: left;
	}

	[aria-current] {
		position: relative;
		display: inline-block;
	}

	[aria-current]::after {
		position: absolute;
		content: '';
		width: calc(100% - 1em);
		height: 5px;
		background-color: var(--primary-color);
		display: block;
		bottom: -1px;
	}

	a {
		text-decoration: none;
		padding: 6px 0.5em 1em 0.5em;
		display: block;
	}

</style>

<nav>
	<ul>
		<li><a aria-current="{segment === undefined ? 'page' : undefined}" href=".">home</a></li>
		<li><a aria-current="{segment === 'about' ? 'page' : undefined}" href="about">about</a></li>

		<!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
		<!-- <li><a rel=prefetch aria-current="{segment === 'blog' ? 'page' : undefined}" href="blog">blog</a></li> -->
	</ul>
</nav>
