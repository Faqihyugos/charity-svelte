<script>
  import { onMount } from "svelte";
  import CharityList from "../components/CharityList.svelte";
  import Header from "../components/Header.svelte";
  import Welcome from "../components/Welcome.svelte";
  import Promo from "../components/Promo.svelte";
  import Footer from "../components/Footer.svelte";
  

  let title = "Charity";
  let charities = [];

  onMount(async function () {
    const res = await fetch("https://charity-api-bwa.herokuapp.com/charities");
    charities = await res.json();
  });
</script>

<Header />
<Welcome />
<CharityList {charities} />
<Promo />
<Footer />
