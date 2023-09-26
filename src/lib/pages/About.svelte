<script lang="ts">
  import Link from "$lib/components/Link.svelte";
  import Page from "$lib/components/Page.svelte";
  import Text from "$lib/components/Text.svelte";
  import { primaryBackground } from "$lib/utils/constants";

  export let backgroundClass = primaryBackground;
</script>

<Page id="about" title="About me" {backgroundClass}>
  <Text>
    <p class="indent-8">Hey, I'm Pakorn, aka Win, Wynn.</p>
    <p class="indent-8">
      I am a fast-learner, self-taught developer. I have been graduated from Electrical Engineering but 
      I found myself not suitable for this job. I prefer to coding so I have eager to learn it. 
      Because of that I started with front-end web developer. my learnings have been mainly from 2 sources: 
      FreeCodeCamp website and Udemy's courses. Here this is my
      <Link url="https://www.freecodecamp.org/certification/WynnPakorn/javascript-algorithms-and-data-structures">
        JavaScript Algorithms and Data Structures certification.
      </Link>
    </p>
    <p class="indent-8">
      I have an understanding of basic of web development and currently learning Svelte and Tailwind framework with myself. 
      So I looking for job that mainly use that 2 framework mentioned above. 
    </p>
  </Text>
</Page>
