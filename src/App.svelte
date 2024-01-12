<script>
  import html2pdf from 'html2pdf.js'
  import Infos from './lib/Infos.svelte'
  import Profil from './lib/Profil.svelte'
  import Langs from './lib/Langs.svelte'
  import Master from './lib/Master.svelte'
  import Xp from './lib/Xp.svelte'
  import Skills from './lib/Skills.svelte'

  async function handlePrint() {

      const h = document.querySelectorAll('.remove-pdf');

      for (let i = 0; i < h.length; i++) {
        h[i].style.display = "none";
      }


      const element = document.getElementById('print');
      var opt = {
        margin: 0,
        html2canvas: { scale: 0.5 }
      };
      html2pdf().set().from(element).save();
  }

  // DATAS INFOS
  let dataInfos = {
    name: 'Tdy81',
    job: 'Dévelopeur front-end',
    age: '42 ans',
    address: 'Paris, France',
    email: 'email@contact.com',
    phone: '06.01.02.03.04',
    media: './avatar.jpg'
  }

// DATAS PROFIL
let dataProfil = "Je suis développeur front-end, 10 ans d'expérience à mon actif. J'ai collaboré sur divers projets digitaux pour de nombreux clients grands comptes issus de domaines variés. Ces expériences m'ont permis d'approfondir mes connaissances sur les différents aspects du développement Web: sites, applications, emails, builders, responsive design, animations, Wordpress..."

  // DATAS LANGUAGES
let dataLangs = [
  {
    name: "Anglais",
  }
]

// DATAS SKILLS
let dataSkills = [
  {
    name: "HTML",
  },
  {
    name: "CSS / SCSS",
  },
  {
    name: "Javascript",
  },
  {
    name: "notions PHP",
  },
  {
    name: "notions Twig",
  },
  {
    name: "Wordpress",
  },
  {
    name: "Bundlers",
  },
  {
    name: "Photoshop / Figma",
  }
]

// DATAS XP
let dataXp = [
  {
    name: "Développeur Front-end",
    place: "Freelance, Paris",
    date: "2019, présent",
    desc: "- Développement front dans une équipe agile utilisant les technologies HTML, CSS, JS",
  },
  {
    name: "Développeur Front-end",
    place: "Glucoz, Paris",
    date: "2017, 2019",
    desc: "- Développement front dans une équipe agile utilisant les technologies HTML, CSS, JS",
  },
  {
    name: "Développeur Front-end",
    place: "Freelance, Paris",
    date: "2009, 2016",
    desc: "- Développement front dans une équipe agile utilisant les technologies HTML, CSS, JS",
  },
  {
    name: "Graphiste / Régisseur",
    place: "Atelier Audiovisuel de Barbizon, Barbizon",
    date: "2003, 2007",
    desc: "- Collaboration avec une équipe créative pour développer des concepts audioviuels uniques",
  }
]

// DATAS MASTER
let dataMaster = [
  {
    name: "Intégrateur Web",
    place: "Gréta Tertiaire 77, Melun",
    date: "2007 - 2028",
    desc: "",
  },
  {
    name: "Graphiste PAO",
    place: "Gréta Tertiaire 77, Fontainebleau",
    date: "2001 - 2002",
    desc: "",
  },
  {
    name: "Brevet des métiers d'art graphisme",
    place: "Lycée Professionnel Congis sur therouanne",
    date: "1997 - 1999",
    desc: "",
  }
]
  
</script>

<div>
  <h1 style="padding: 30px;" class="remove-pdf">CV Builder - Svelte.js</h1>
  <div id="print">

    <div id="app-content">

      <Infos bind:dataInfos showEdit={false} showCollapse={true} />

      <div class="row">
        <div class="col">
          <Profil bind:dataProfil showEdit={false} showCollapse={true} />
          <br>
          <Skills bind:dataSkills showEdit={false} showCollapse={true} />
        </div>
        <div class="col">
          <Xp bind:dataXp showEdit={false} showCollapse={true}/>
        </div>
        <div class="col">
          <Master bind:dataMaster showEdit={false} showCollapse={true}/>
          <Langs bind:dataLangs showEdit={false} showCollapse={true}/>
        </div>
      </div>
    </div>

    <div id="app-sidebar" class="remove-pdf">
      <button class="btn-pdf" on:click={handlePrint}>Download PDF</button>
      <Infos bind:dataInfos showEdit={true} showCollapse={false} />
      <Profil bind:dataProfil showEdit={true} showCollapse={false} />
      <Skills bind:dataSkills showEdit={true} showCollapse={false}/>
      <Xp bind:dataXp showEdit={true} showCollapse={false}/>
      <Master bind:dataMaster showEdit={true} showCollapse={false}/>
      <Langs bind:dataLangs showEdit={true} showCollapse={false}/>
    </div>

  </div>
</div>
