<script>
	import "./../styles/global.css";
	import "./../styles/theme.css";
	import Header from "$lib/components/HeaderComponents/Header.svelte";
	import Footer from "$lib/components/Footer.svelte";
	import BackToTop from "$lib/components/BackToTop.svelte";
</script>

<BackToTop />
<Header />
<slot />
<Footer />
