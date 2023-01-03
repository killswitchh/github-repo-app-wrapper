<script>
	let URLS = {
		REACT: 'https://github-repo-finder-react.netlify.app/',
		QWIK: 'https://github-repo-finder-qwik.netlify.app/',
		ANGULAR: 'https://github-repo-finder-angular.netlify.app/',
		SVELTE: 'https://github-repo-finder-svelte.netlify.app/',
		VUE: 'https://github-repo-finder-vue.netlify.app/'
	};

	let FRAMEWORKS = {
		REACT: {
			displayName: 'React',
			frameworkURL: 'https://reactjs.org/',
			projectURL: URLS.REACT
		},
		VUE: {
			displayName: 'Vue',
			frameworkURL: 'https://vuejs.org/',
			projectURL: URLS.VUE
		},
		ANGULAR: {
			displayName: 'Angular',
			frameworkURL: 'https://angular.io/',
			projectURL: URLS.ANGULAR
		},
		SVELTE: {
			displayName: 'Svelte Kit',
			frameworkURL: 'https://kit.svelte.dev/',
			projectURL: URLS.SVELTE
		},
		QWIK: {
			displayName: 'Qwik City',
			frameworkURL: 'https://qwik.builder.io/',
			projectURL: URLS.QWIK
		}
	};
	/**
	 * @type {{ displayName: string; frameworkURL: string; projectURL: string; } | null}
	 */
	let selectedFramework = null;

	/**
	 * @param {{displayName : string, frameworkURL: string, projectURL: string}} framework
	 */
	function urlChange(framework) {
		selectedFramework = framework;
	}
</script>

<nav>
	<ul>
		<li><a href="/" on:click={() => urlChange(FRAMEWORKS.REACT)}>React</a></li>
		<li><a href="/" on:click={() => urlChange(FRAMEWORKS.QWIK)}>Qwik</a></li>
		<li><a href="/" on:click={() => urlChange(FRAMEWORKS.ANGULAR)}>Angular</a></li>
		<li><a href="/" on:click={() => urlChange(FRAMEWORKS.SVELTE)}>Svelte</a></li>
		<li><a href="/" on:click={() => urlChange(FRAMEWORKS.VUE)}>Vue</a></li>
	</ul>
</nav>
{#if selectedFramework != null}
	<section>
		This page was built using {selectedFramework.displayName}. Click
		<a href={selectedFramework.frameworkURL} target="_blank" rel="noreferrer"> here</a> to know more
		about the framework.
	</section>
	<iframe
		src={selectedFramework.projectURL}
		frameborder="0"
		allowtransparency
		style="width:100%;height: calc(100vh + 15px); border: 1px solid black;"
		title="dashboard"
	/>
{/if}

<style>
	ul {
		list-style-type: none;
		margin: 0;
		padding: 0;
		overflow: hidden;
		background-color: #333333;
	}

	li {
		float: left;
	}

	li a {
		display: block;
		color: white;
		text-align: center;
		padding: 16px;
		text-decoration: none;
	}

	li a:hover {
		background-color: #111111;
	}
</style>
