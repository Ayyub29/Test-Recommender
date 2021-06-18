<script>
	// export let name;
	import Navbar from './components/Navbar.svelte';
	import Card from './components/Card.svelte';

	export let cards = [
		{ t: 'Sapi Jawa A', a:'Sapi', d: 'Sapi yang dikasih makan buah blueberry', s:'https://duniasapi.com/media/k2/items/cache/878af4972e07916863ae909a162bf74b_XL.jpg', v:0 },
		{ t: 'Sapi Jawa B', a:'Sapi',  d: 'Sapi yang dikasih makan buah strawberry', s:'https://duniasapi.com/media/k2/items/cache/75b44b0e9c2e5d305fa323c6c51d3476_Generic.jpg', v:0},
		{ t: 'Sapi Bali A', a:'Sapi',  d: 'Sapi yang bisa nari kecak', s:'https://dutatv.com/wp-content/uploads/2020/07/250720-sapi-1029x620.jpg', v:0},
		{ t: 'Kambing Kidal', a:'Kambing',  d: 'Kambing yang kaki kanannya dipotong', s:'https://peternakan.kaltimprov.go.id/upload/artikel/medium_126743419354774364d9d2e.kambing_qurban_aqiqah.jpg', v:0},
		{ t: 'Kambing Jantan', a:'Kambing',  d: 'Kambing yang tanduknya ada 3', s:'https://statik.tempo.co/data/2020/01/12/id_905226/905226_720.jpg', v:0},
		{ t: 'Unta Berpunuk 3', a:'Unta',  d: 'Unta biasanya dibakar atau dijadiin sate.', s:'https://static.republika.co.id/uploads/images/inpicture_slide/unta-_120529132220-232.jpg', v:0},
		{ t: 'Domba Berbulu', a:'Domba',  d: 'Serigala berbulu Domba tapi ga ganteng', s:'https://cdn1-production-images-kly.akamaized.net/54Je29zEa1o8j0K1XilvY23JdA0=/640x640/smart/filters:quality(75):strip_icc():format(jpeg)/kly-media-production/medias/1632750/original/007472200_1498216544-Domba6.jpg', v:0},
		{ t: 'Domba Jahil', a:'Domba',  d: 'Bukan Shaun the sheep tapi emang jahil aja', s:'https://cdn.pixabay.com/photo/2017/08/03/18/49/wolf-in-sheeps-clothing-2577813_1280.jpg', v:0},
	];

	function handleCount(event) {
		cards[event.detail.iter].v = event.detail.value;
		cards = cards.sort(function(a, b){return b.v - a.v});
	}
</script>

<Navbar/>

<main>
	{#each cards as { t, s, d, v, a }, i}
		<Card on:message={handleCount} bind:title={t} imageDesc={a} imageSource={s} description={d} v={v} i={i}/>
	{/each}
</main>

<style>
	main{
		display:flex;
		flex-wrap: wrap;
		background-color: beige;
		align-items: center;
		text-align: center;
		justify-content: center;
	}
</style>