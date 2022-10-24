<script>
  import ChapterSection from "$lib/components/DetailComponents/ChapterSection.svelte";
  import ChapterContentLeft from "$lib/components/DetailComponents/ChapterContentLeft.svelte";
  import ChapterContentRight from "$lib/components/DetailComponents/ChapterContentRight.svelte";
  import StandardHero from "$lib/components/DetailComponents/StandardHero.svelte";
  import StandardNavigation from "$lib/components/DetailComponents/StandardNavigation.svelte";
  import StandardNavigationLink from "$lib/components/DetailComponents/StandardNavigationLink.svelte";
  import Header from "../../lib/components/Header.svelte";
  import Content from "../../lib/components/Content.svelte";
  import Footer from "../../lib/Footer.svelte";

  export let data;

  console.log(data.standard.data.chapters);

  // console.log(data.standard.data.title);

  console.log(data.standard.data.chapters);

  let mybutton = document.getElementById("myBtn");

  window.onscroll = function () {
    scrollFunction();
  };

  function scrollFunction() {
    if (
      document.body.scrollTop > 20 ||
      document.documentElement.scrollTop > 20
    ) {
      mybutton.style.display = "block";
    } else {
      mybutton.style.display = "none";
    }
  }

  // When the user clicks on the button, scroll to the top of the document
  function topFunction() {
    document.header.scrollTop = 0;
    document.documentElement.scrollTop = 0;
  }
</script>

<Header />

<StandardHero
  standardHeaderTitle={data.standard.data.title}
  standardHeaderIntroduction={data.standard.data.introduction}
  standardNumber={data.standard.data.standardnumber}
/>

{#each data.standard.data.chapters as chapter, i}
  <ChapterSection
    chapterTitle={chapter.data.title}
    chapterNumber={`${data.standard.data.standardnumber}.${i + 1}`}
    chapterUID={chapter.uid}
  >
    <ChapterContentLeft contentLeft={chapter.data.contentleft} />
    <ChapterContentRight contentRight={chapter.data.contentright} />
  </ChapterSection>
{/each}
<button onclick="topFunction()" id="myBtn" title="Go to top"
  >Terug naar boven</button
>

<Footer />

<style>
  #myBtn {
    color: black;
    background-color: var(--color-cmd-yellow);
    bottom: 20px;
    right: 30px;
    float: right;
    position: sticky;
    top: 0;
    border: none;
    border-radius: 4px;
    border: 2px solid var(--color-black);
    padding: 15px;
  }
  /* #myBtn {
    display: none;
    position: fixed;
    bottom: 20px;
    right: 30px;
    z-index: 99;
    font-size: 18px;
    border: none;
    outline: none;
    background-color: var(--color-cmd-yellow);
    color: black;
    cursor: pointer;
    padding: 15px;
    border-radius: 4px;
    border: 2px solid var(--color-black);
  }
*/
  #myBtn:hover {
    background-color: #555;
  }
</style>
