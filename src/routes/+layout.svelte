<script>
	import "./../styles/global.css";
	import "./../styles/theme.css";
	import Header from "$lib/components/HeaderComponents/Header.svelte";
	import Footer from "$lib/components/Footer.svelte";
</script>

<Header />
<slot />
<Footer />
