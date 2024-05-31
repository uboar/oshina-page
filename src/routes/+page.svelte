<script lang="ts">
  import markdownit from "markdown-it";
  import description from '../assets/description.md?raw';

  const mdParser = markdownit();
  const CIRCLE_LOGO_URL =
    "https://r2.uboar.net/ubopage%2Foshina-futabastep.webp";

  const OSHINAGAKI_TITLE_TEXT = "お品書き";
  const OSHINAGAKI_SUBTITLE_TEXT = "ふたばすてっぷ 2024.6.2";
  const OSHINAGAKI_SUBTITLE_HREF = "https://futabastep.net";

</script>

<svelte:head>
  <title>壇松間おしながき</title>
  <meta property="og:title" content="壇松間おしながき" />
</svelte:head>

<div class="screen">
  <div class="flex flex-col justify-center gap-1">
    <h1
      class="text-center text-4xl font-bold tracking-widest text-white drop-shadow-lg"
    >
      {OSHINAGAKI_TITLE_TEXT}
    </h1>
    <a
      class="text-center text-xl tracking-widest text-white underline drop-shadow-lg hover:no-underline"
      target="_blank"
      href={OSHINAGAKI_SUBTITLE_HREF}>{OSHINAGAKI_SUBTITLE_TEXT}</a
    >
    <img src={CIRCLE_LOGO_URL} alt="oshina" class="oshina" />
    <div class="self-center text-center prose w-full mb-64">
      {@html mdParser.render(description)}
    </div>
  </div>
</div>
<div class="bottom-link">
  <a
    class=" m-2 w-fit rounded-full border bg-white px-3 text-slate-600 drop-shadow transition-all hover:-translate-y-px hover:bg-transparent hover:text-white hover:shadow-xl"
    href="https://uboar.net"
  >
    uboar.net
  </a>
</div>

<style lang="postcss">
  /* https://www.joshwcomeau.com/gradient-generator/ */
  .screen {
    width: 100svw;
    height: 100svh;
    @apply bg-cover bg-fixed bg-center bg-no-repeat overflow-x-hidden;
    background-color: #8BC6EC;
    background-image: linear-gradient(209deg, #8BC6EC 0%, #9599E2 100%);
  }

  .oshina {
    @apply my-4 self-center align-middle drop-shadow md:w-1/2;
  }

  .bottom-link {
    @apply fixed bottom-4 flex w-full justify-center;
  }
</style>
