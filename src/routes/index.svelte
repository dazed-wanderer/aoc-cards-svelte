<script>
	import CardList from './list/cards.svelte';
	import Card from '$lib/components/card.svelte';

	let basics;
	let holos;
	let galaxies;
	let radiant;
	let basicGallery;
	let vee;
	let veeUltra;
	let veeAlt;
	let veeMax;
	let veeMaxAlt;
	let veeStar;
	let trainerHolo;
	let rainbow;
	let gold;
	let veeGallery;

	const getCards = async () => {
		let promiseArray = [];

		let cardFetch = await fetch('/data.json');
		let cards = await cardFetch.json();
		window.cards = cards;

		basics = cards.slice(0, 24);
		holos = cards.slice(0, 24);
		galaxies = cards.slice(0, 24);
		radiant = cards.slice(0, 24);
		basicGallery = cards.slice(0, 24);
		vee = cards.slice(0, 24);
		veeUltra = cards.slice(0, 24);
		veeAlt = cards.slice(0, 24);
		veeMax = cards.slice(0, 24);
		veeMaxAlt = cards.slice(0, 24);
		veeStar = cards.slice(0, 24);
		trainerHolo = cards.slice(0, 24);
		rainbow = cards.slice(0, 24);
		gold = cards.slice(0, 24);
		veeGallery = cards.slice(0, 24);

		return cards;
	};
</script>

<main>
	<header>
		<h1>AoC Cards Test</h1>
	</header>

	<h2>Common &amp; Uncommon</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each basics as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype='pokémon'
					subtypes='basic'
					rarity='common' 
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 1</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each radiant as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype='pokémon'
					subtypes={card.subtypes}
					rarity='rare holo v'
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 2</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each basicGallery as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype='pokémon'
					subtypes={card.subtypes}
					rarity='rare holo vmax'
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 3</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each vee as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype='pokémon'
					subtypes={card.subtypes}
					rarity='rare holo vstar'
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 4</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each veeUltra as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype='pokémon'
					subtypes={card.subtypes}
					rarity='rare ultra'
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 5</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each veeMax as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype='pokémon'
					subtypes={card.subtypes}
					rarity='rare rainbow'
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 6</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each veeMaxAlt as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype='pokémon'
					subtypes={card.subtypes}
					rarity='rare rainbow alt'
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 7</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each veeStar as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype='pokémon'
					subtypes={card.subtypes}
					rarity='rare secret'
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 8</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each trainerHolo as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype='pokémon'
					subtypes={card.subtypes}
					rarity='radiant'
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 9</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each rainbow as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype='pokémon'
					subtypes={card.subtypes}
					rarity='rare holo v'
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 10</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each gold as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype='pokémon'
					subtypes={card.subtypes}
					rarity='rare holo v'
				/>
			{/each}
		{/await}
	</CardList>
</main>

<style>
	main {
		color: white;
		padding: 50px;
		max-width: 1200px;
		margin: auto;
	}

	header {
		margin-bottom: 4rem;
		display: grid;
		grid-template-columns: 1fr;
		grid-gap: 30px;
		max-width: 900px;
		margin: auto;
	}

	header h2 {
		margin-top: 0;
		font-weight: 100;
	}

@media screen and (min-width: 600px) {
	header {
		grid-template-columns: 50% 1fr;
	}
	.showcase {
		grid-column: 2;
		grid-row: 2/4;
	}
	.intro, .info {
		grid-column: 1;
	}
}

	@media screen and (min-width: 900px) {
		header {
			grid-template-columns: 60% 1fr;
		}
	}

	.showcase {
		z-index: 99;
		max-width: min(330px, 80vw);
		margin: auto;
	}

	h1 {
		margin-top: 0;
		margin-bottom: 0.25em;
	}

	p {
		margin: 0 0 0.25em;
		line-height: 1.5;
	}

	p.small {
		font-size: 0.875rem;
		opacity: 0.75;
	}

	h1,
	h2,
	h3 {
		font-family: 'Roboto Condensed';
	}

	h2 {
		margin-top: 4em;
		margin-bottom: 0.25em;
	}

	h2 + p,
	h2 + p + p {
		font-style: italic;
		margin-bottom: 1em;
	}

	hr {
		border: none;
		background: white;
		height: 1px;
		opacity: 0.25;
		margin: 1em -1em;
	}

	h1 sup {
		font-weight: 300;
		font-size: 0.5em;
	}

	h2 sup {
		font-weight: 300;
		font-size: 0.75em;
	}

	mark {
		background: #006065;
		color: white;
		font-style: italic;
		font-weight: bold;
		padding-inline: 0.25em;
		border-radius: 3px;
	}

	:global(*) {
		box-sizing: border-box;
	}

	:global(body, html) {
		height: 100%;
		padding: 0;
		margin: 0;
		scroll-behavior: smooth;
	}

	:global(body) {
		font-family: 'Roboto';
		background-color: rgb(57, 60, 66);
	}
</style>
