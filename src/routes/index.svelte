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

		basics = cards.slice(0, 6);
		holos = cards.slice(6, 12);
		galaxies = cards.slice(12, 15);
		radiant = cards.slice(15, 18);
		basicGallery = cards.slice(60, 63);
		vee = cards.slice(18, 21);
		veeUltra = cards.slice(21, 24);
		veeAlt = [...cards.slice(27, 30), ...cards.slice(33, 36)];
		veeMax = cards.slice(24, 27);
		veeMaxAlt = [cards[36], cards[31], cards[37]];
		veeStar = cards.slice(39, 42);
		trainerHolo = cards.slice(42, 48);
		rainbow = cards.slice(48, 51);
		gold = cards.slice(51, 60);
		veeGallery = cards.slice(63, 69);

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
					supertype={card.supertype}
					subtypes={card.subtypes}
					rarity={card.rarity}
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 1</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each holos as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype={card.supertype}
					subtypes={card.subtypes}
					rarity={card.rarity}
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 2</h2>

	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each galaxies as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype={card.supertype}
					subtypes={card.subtypes}
					rarity={card.rarity}
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 3</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each radiant as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype={card.supertype}
					subtypes={card.subtypes}
					rarity={card.rarity}
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 4</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each basicGallery as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype={card.supertype}
					subtypes={card.subtypes}
					rarity={card.rarity}
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 6</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each vee as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype={card.supertype}
					subtypes={card.subtypes}
					rarity={card.rarity}
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 7</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each veeUltra as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype={card.supertype}
					subtypes={card.subtypes}
					rarity={card.rarity}
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 8</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each veeAlt as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype={card.supertype}
					subtypes={card.subtypes}
					rarity={card.rarity}
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 9</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each veeMax as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype={card.supertype}
					subtypes={card.subtypes}
					rarity={card.rarity}
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 10</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each veeMaxAlt as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype={card.supertype}
					subtypes={card.subtypes}
					rarity={card.rarity}
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 11</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each veeStar as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype={card.supertype}
					subtypes={card.subtypes}
					rarity={card.rarity}
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 12</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each trainerHolo as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype={card.supertype}
					subtypes={card.subtypes}
					rarity={card.rarity}
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 13</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each rainbow as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype={card.supertype}
					subtypes={card.subtypes}
					rarity={card.rarity}
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 14</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each gold as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype={card.supertype}
					subtypes={card.subtypes}
					rarity={card.rarity}
				/>
			{/each}
		{/await}
	</CardList>

	<h2>Holofoil 15</h2>
	<CardList>
		{#await getCards()}
			loading...
		{:then cards}
			{#each veeGallery as card, id}
				<Card
					img={card.images.large}
					number={card.number}
					supertype={card.supertype}
					subtypes={card.subtypes}
					rarity={card.rarity}
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
