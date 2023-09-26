<script lang="ts">
  import Card from "$lib/components/Card.svelte";
  import Page from "$lib/components/Page.svelte";
  import { neutralBackground } from "$lib/utils/constants";
  import collapse from 'svelte-collapse'
  
  type Skill = {
    title:string;
    image:string;
    active:boolean;
  }
  let skills: Array<Skill> = [
    {title : "HTML",image : "skills/html.png" ,active : false},
    {title : "CSS",image : "skills/css.png" ,active : false},
    {title : "Javascript",image : "skills/javascript.png" ,active : false},
    {title : "Jquery",image : "skills/jquery.png" ,active : false},
    {title : "Typescript",image : "skills/typescript.png" ,active : false},
    {title : "Bootstrap",image : "skills/bootstrap.svg" ,active : false},
    {title : "Svelte",image : "skills/svelte.png" ,active : false},
    {title : "Tailwind",image : "skills/tailwind.png" ,active : false}
  ];

  export let backgroundClass = neutralBackground;

  function active (index:number){
    if (skills[index].active === false){
      skills = skills.map((skill, i) => ({ ...skill, active: i === index }))
    }    
    else {
    skills[index].active = false
  }
 }
  
</script>

<Page id="skills" title="My Skills" {backgroundClass}>
  <div class="container mx-auto grid max-w-screen-xl gap-4 md:grid-cols-4 sm:grid-cols-2">
    {#each skills as skill,i}
      <Card>
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <!-- svelte-ignore a11y-no-static-element-interactions -->
        <div on:click={() => {active(i)}} class="text-2xl font-medium text-center ">
          {skill.title}
        </div>
        <div use:collapse={{open:skill.active}}>
          <img src = {skill.image} alt=""/>
        </div>
      </Card>
    {/each}
  </div>
 
</Page>
