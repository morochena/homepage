<script>
  import { shortcut } from "./shortcut.js";

  const feeds = [
    { name: "Feedly", url: "https://feedly.com" },
    { name: "Lobste.rs", url: "https://lobste.rs" },
    { name: "Hckrnews", url: "https://hckrnews.com" },
    { name: "Reddit", url: "https://reddit.com" },
  ];

  const goToURL = (url) => {
    window.open(url, "_blank");
  };
</script>

<div class="flex flex-col items-center align-center justify-center">
  <h1 class="text-3xl text-white font-bold">Links</h1>

  <ul class="text-lg text-white m-4">
    {#each feeds as feed, index}
      <li class="border-2 border-zinc-500 rounded p-2 mb-2">
        <a
          use:shortcut={{ control: true, code: `Digit${index + 1}`, callback: () => goToURL(feed.url) }}
          href={feed.url}
          class="text-white"
        >
          ({index + 1}) {feed.name}</a
        >
      </li>
    {/each}
  </ul>
</div>
