<script>
import Nav from './lib/Nav.svelte';
import FormSettings from './lib/FormSettings.svelte';
import FormInfos from './lib/FormInfos.svelte';
import Infos from './lib/Infos.svelte';
import Contact from './lib/Contact.svelte';
import Profil from './lib/Profil.svelte';
import FormXp from './lib/FormXp.svelte';
import Xp from './lib/Xp.svelte';
import FormMs from './lib/FormMs.svelte';
import Masters from './lib/Masters.svelte';
import FormSkills from './lib/FormSkills.svelte';
import Skills from './lib/Skills.svelte';
import FormLangs from './lib/FormLangs.svelte';
import Langs from './lib/Langs.svelte';
import FormInterests from './lib/FormInterests.svelte';
import Interests from './lib/Interests.svelte';
import FormCheckout from './lib/FormCheckout.svelte';

// TAB
let currentTab = 5;

// SETTINGS
let settingsType = 0;
let settingsTheme = "theme-1";
let settingsFont = "font-serif";

// INFOS
let infos = [
  {
    name: 'John Doe',
    job: 'Senior UX Designer',
    address : 'Numéro et Nom de rue',
    cp : 'Code postal',
    city : 'Ville',
    email : 'hello@gmail.com',
    phone : '06 00 00 00 00',
    avatar: '',
    desc: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam.'
  }
]

// XP
let xps = [
  {
    job: "Nom de métier",
    location: "Nom de l'entreprise, Paris",
    dateStart: "2020",
    dateEnd: "2024",
    desc: "- Lorem ipsum dolor sit amet, consectetur adipiscing elit\n- Donec posuere nisl quis bibendum pretium.\n- Aliquam sit amet ante vel risus fermentum mollis.",
    show: false,
  },
  {
    job: "Nom de métier",
    location: "Nom de l'entreprise, Paris",
    dateStart: "2020",
    dateEnd: "2024",
    desc: "- Lorem ipsum dolor sit amet, consectetur adipiscing elit\n- Donec posuere nisl quis bibendum pretium.\n- Aliquam sit amet ante vel risus fermentum mollis.",
    show: false,
  },
  {
    job: "Nom de métier",
    location: "Nom de l'entreprise, Paris",
    dateStart: "2020",
    dateEnd: "2024",
    desc: "- Lorem ipsum dolor sit amet, consectetur adipiscing elit\n- Donec posuere nisl quis bibendum pretium.\n- Aliquam sit amet ante vel risus fermentum mollis.",
    show: false,
  },
  {
    job: "Nom de métier",
    location: "Nom de l'entreprise, Paris",
    dateStart: "2020",
    dateEnd: "2024",
    desc: "- Lorem ipsum dolor sit amet, consectetur adipiscing elit\n- Donec posuere nisl quis bibendum pretium.\n- Aliquam sit amet ante vel risus fermentum mollis.",
    show: true,
  }
]

// MASTER
let masters = [
  {
    title: "Formation Intégrateur Web",
    location: "Paris",
    dateStart: "2008",
    dateEnd: "2009",
    show: true,
  },
  {
    title: "Formation UX Designer",
    location: "Paris",
    dateStart: "2007",
    dateEnd: "2008",
    show: true,
  }
]

// SKILLS
let skills = [
  {name: 'Polyvalent', show: false},
  {name: 'Esprit d’équipe', show: false},
  {name: 'Autonome', show: false},
  {name: 'Sens de l’organisation', show: true}
]

// LANGS
let langs = [
  {name: 'Français', show: true},
  {name: 'Anglais', show: true},
]

// INTERETS
let interests = [
  {name: 'Sport', show: true},
  {name: 'Cinéma', show: true},
  {name: 'Musique', show: true},
]

</script>

<div class="fixed top-0 left-0 w-24 h-full px-4 py-8 flex flex-col items-center">
  <Nav bind:currentTab />
</div>

<div class="ml-24">
  <div class="lg:flex">
    <div class="lg:basis-1/3 py-8 px-4 lg:h-screen overflow-auto">
      {#if currentTab === 5}
        <FormSettings bind:settingsType bind:settingsFont bind:currentTab />
      {:else if currentTab === 0}
        <FormInfos bind:infos bind:currentTab />
      {:else if currentTab === 1}
        <FormXp bind:xps bind:currentTab />
      {:else if currentTab === 2}
        <FormMs bind:masters bind:currentTab />
      {:else if currentTab === 3}
        <FormSkills bind:skills bind:currentTab /> 
      {:else if currentTab === 6}
        <FormLangs bind:langs bind:currentTab />        
      {:else if currentTab === 7}
        <FormInterests bind:interests bind:currentTab /> 
      {:else if currentTab === 8}
        <FormCheckout bind:currentTab /> 
      {/if}
    </div>
    <div class="lg:basis-2/3 py-8 px-4">
      <div id="app-preview" class="border rounded-lg">
        <div id="wrap-preview" class="type-{settingsType} {settingsTheme} {settingsFont}">
          {#if settingsType === 0}
            <div class="flex">
              <div class="basis-2/3 p-4 col-left">
                <Infos bind:infos />
                <Profil bind:infos />
                <Xp bind:xps />
              </div>
              <div class="basis-1/3 p-4 col-right">
                <Contact bind:infos />
                <Skills bind:skills />
                <Masters bind:masters />
                <Langs bind:langs />
                <Interests bind:interests />
              </div>
            </div>  
          {:else if settingsType === 1} 
          <div class="flex items-end">
            <div class="basis-1/3 p-4 text-right col-left">
              <Contact bind:infos />
            </div>
            <div class="basis-2/3 p-4 col-right">
              <Infos bind:infos />
            </div>
          </div>
          <div class="flex">
            <div class="basis-1/3 p-4 text-right col-left">
              <Masters bind:masters />
              <Skills bind:skills />
              <Langs bind:langs />
              <Interests bind:interests />
            </div>
            <div class="basis-2/3 p-4 col-right">
              <Profil bind:infos />
              <Xp bind:xps />
            </div>
          </div>  
          {:else if settingsType === 2} 
          <div class="flex">
            <div class="basis-1/3 p-4 col-left">
              <Infos bind:infos />
              <Contact bind:infos />
              <Skills bind:skills />
              <Langs bind:langs />
              <Interests bind:interests />
            </div>
            <div class="basis-2/3 p-4 col-right">
              <Profil bind:infos />
              <Xp bind:xps />
              <Masters bind:masters />
            </div>
          </div>   
          {/if}
        </div>
      </div>
    </div>
  </div>
</div>
