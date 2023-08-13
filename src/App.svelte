<script lang="ts">
  import Footprint from "./assets/footprint.json"
  import monthDefine from "./lib/month";
  import yearDefine from "./lib/year";
  import { Twitter, Facebook } from "svelte-share-buttons-component"
  
  const jsonLength = Object.keys(Footprint).length;
  let entry = Math.floor(Math.random() * jsonLength) + 1;

  function newFootprint() {
    entry = Math.floor(Math.random() * jsonLength) + 1;
  }

</script>

<main>
 
  <h1 class="text-red-600 font-bold text-6xl">
    Pheu Thai Digital Footprint
  </h1>
  <a href={Footprint[entry].link} target="_blank">
    <h1 class="text-3xl font-bold text-white mt-6">
      "{Footprint[entry].quote}" 
      <span class="italic font-normal text-xl">
        - {Footprint[entry].person} ({Footprint[entry].date.split("-")[2].replace("0", "")} {monthDefine(Footprint[entry].date.split("-")[1])} {yearDefine(Footprint[entry].date.split("-")[0])})
      </span>
    </h1>
  </a>

  <button class="mt-10 p-4 rounded text-blue-700 bg-white" on:click={newFootprint}>
    หาดิจิตอลฟุตพริ้นท์อันใหม่
  </button>

  <div class="text-white mt-3">
    แชร์ฟุตพริ้นท์นี้ได้ที่
    <Twitter class="share-button" text='ครั้งหนึ่ง{Footprint[entry].person}เคยพูดว่า "{Footprint[entry].quote}"' url={Footprint[entry].link}/>
    <Facebook class="share-button" quote='ครั้งหนึ่ง{Footprint[entry].person}เคยพูดว่า "{Footprint[entry].quote}"' url={Footprint[entry].link}/>
  </div>
</main>

