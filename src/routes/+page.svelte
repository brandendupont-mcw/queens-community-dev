<script lang="ts">
  import Link from './../lib/components/link.svelte'
  import { scaleOrdinal } from 'd3-scale'; 
  import { forceX, forceY, forceCollide,  forceManyBody, forceCenter  } from 'd3-force';
  import HeroImage from "../lib/components/heroImage.svelte"
  import Block from './../lib/components/block.svelte';
  import TextBlock from './../lib/components/text.svelte';
  import PopOverMobile from './../lib/components/popoverMobile.svelte';
  import Menu from './../lib/components/collapsiblemenu.svelte';
  import CommunityGrants from './../lib/components/communityGrants.svelte'
  import Map from './../lib/components/mapbox/map.svelte'
  import Calendar2 from './../lib/components/charts/calendar.svelte';
  import mobilemap from './mobile-map.png';
  import MediaQuery from "../lib/components/mediaquery.svelte";
  import { ScrollArea } from "$lib/components/ui/scroll-area/index.js";
  import calendarimage from "$lib/assets/images/calendar.png"

  const categoryColor = scaleOrdinal([
    '#ffbf00',
    '#00aeff',
  ]);


    import youthImage from '$lib/assets/images/summer_internship.jpg';

    let currentStep;
    const steps = [    "<p>This chart depicts defendant's that have been served with trespass notices under the Queens Merchants Business Improvement Program. With</p>", "<p> We conducted an initial analysis of this program's effectiveness. To do so, we selected 174 individuals served with trespass notices who had been subject to the tresspass notice for at least up to one year. This gives us enough time to get a sense of arrest patterns under this program. </p>", 
     "<p>We find that 87% of individuals have been served with trespass notices and are not arrested at that same location again. </p>",  "<p>Conversely, 13% are rearrested at the same location. Business's can now partner with law enforcement and the Queens DA's Office to address recidivist's who continue to steal from the same location. </p>"];

  

    function unclump() {
    groupBy = false;
}
  function clump() {
    groupBy = true;

  }
  
    $: if (currentStep == 0) {
      unclump();

    } 
    else if (currentStep == 1) {
      unclump();
    }
    else if (currentStep == 2) {
      clump();
    } else if (currentStep == 3) {
      clump();
    }

// this is code around



 



  let groupBy = false;
  $: reheatSimulation({ groupBy });

  let alpha = .8;

  const xForce = forceX().strength(0.1);
  const yForce = forceY().strength(0.1);
  const chargeForce = forceManyBody().strength(1);
  const collideForce = forceCollide();
  const centerForce = forceCenter();

  function reheatSimulation(args: Record<string, any> = {}) {
    const _ = args;
    alpha = 1.0;
  }

  let isSelected = 1


  import  dots  from './rearrest_retail_theft.csv';



  
  import { Button } from "$lib/components/ui/button";
  import  data  from './detention-eligible-by-county-detention-eligible-by-county (1).csv';







  import Scroller from '$lib/components/scroller.svelte';

 </script>


<HeroImage />

<div class="sm:sticky xl:top-[1vh] 2xl:top-[10vh] z-50 sm:float-right float-none md:block hidden ">
  <Menu/>
</div>

<div class=" sm:hidden sticky top-0 z-50">
  <div class="flex items-center justify-between space-x-4 pr-4 bg-black mb-10 ">
    <h4 class="text-sm font-semibold text-white p-3 ">Table of Contents</h4>
    <PopOverMobile />     

   </div>
</div>



<Block>
  
  <TextBlock>
    <div class="first-letter:text-7xl first-letter:text-black first-letter:font-sans first-letter:pr-1 first-letter:pb-1 first-letter:float-left ">
      The first contact that an individual has with a prosecutor should not occur in a courtroom or during a crisis. It should happen in a welcoming environment—such as a community event—where individuals can learn about available resources and services that the prosecutor’s office has to offer. That means prosecutors getting out into the community, listening to citizens, and building long-term relationships.      
</div>
</TextBlock>

<TextBlock>
  <div class="first-letter:text-7xl first-letter:text-black first-letter:font-sans first-letter:pr-1 first-letter:pb-1 first-letter:float-left ">
</div>
</TextBlock>


<TextBlock>
  Toward this goal, the Community Partnerships Division in the Queens County DA's Office takes a multi-faceted approach to community engagement – providing opportunities for citizens to work collaboratively with the Office to make a positive contribution to Queens County. The Division reaches out to civic and non-profit organizations, develops programs, sponsors and co-sponsors events, and engages with every neighborhood throughout the borough of Queens.
</TextBlock>


</Block>

<h2 id="community-map" class="text-2xl mt-10 font-semibold pt-4 pb-4 mx-auto max-w-[600px]  ">
  <div class="ml-2 mr-2 sm:ml-0 sm:mr-0">
  Attending Over ~4,000 Events Across Queens, the Community Partnerships Division Is Deeply Engaged in the Community </div>
</h2>
<div class="mx-auto max-w-[600px]  flex-row align-items-center gap-2 sm:flex hidden">
  <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
    <path stroke-linecap="round" stroke-linejoin="round" d="M15.042 21.672 13.684 16.6m0 0-2.51 2.225.569-9.47 5.227 7.917-3.286-.672Zm-7.518-.267A8.25 8.25 0 1 1 20.25 10.5M8.288 14.212A5.25 5.25 0 1 1 17.25 10.5" />
  </svg>
  
  Move your cursor off the map to continue to scroll through the report.
</div>
<div class="mx-auto max-w-[600px] flex flex-row align-items-center gap-2 sm:hidden block ml-2 mr-2">

  
  The interactive map is best viewed on a desktop screen.
</div>
<span class="sm:block hidden">
<Map >
</Map>
</span>
<img src={mobilemap} class="w-[300px] h-[435px] mx-auto sm:hidden block mb-6 mt-6" />
<Block>
  

  <TextBlock>
    Over the past five years, staff in the Office participated in approximately 4,000 public events - from community presentations on domestic violence at St. Mary & St. Antonios Coptic Orthodox Church in Ridgewood, to community board meetings and precinct council meetings across the borough, to community-based celebrations of Lunar New Year, Black History Month, Hispanic Heritage, Women’s History, Asian American Pacific Islander Heritage, Jewish American Heritage and more.
  </TextBlock>


  <h2 id="active-presence" class="text-4xl font-semibold pt-4 pb-4 mt-10">
    Since 2020, the Queens County DA's Office has had a Large and Active Presence in the Community
  </h2>

<TextBlock>
  Nearly every day of the year, the Queens County DA's Office is in the community, demonstrating its ongoing commitment to strengthening positive ties across the borough. Through this approach, the Office has successfully engaged the Queens community, fostering an environment where residents feel empowered to reach out to the Office for more than just assistance with law enforcement-related issues.
</TextBlock>

</Block>

  
  <div class="pt-10 ">
    <h2 id="" class="text-2xl font-semibold pt-4 pb-2 mx-auto max-w-[850px] ">
      <div class="sm:mr-0 sm:ml-0 ml-2 mr-2">
      Every Week of the Year the Queens County DA's Office is in the Community
      
    </h2>
    <div id="anchor-detention-release-changed" class="text-md pb-3  mx-auto max-w-[850px]">
      <div class="sm:mr-0 sm:ml-0 ml-2 mr-2">
      The calendar shows daily events attended by the Queens County DA's Office Community Partnerships Division.  It details the time commitment the Office invests in being accessible to the community.
    </div>
    </div>
  </div>

<TextBlock>
  <div style="max-width: 800px; margin: 0 auto;">
  <iframe title="" aria-label="Scatter Plot" id="datawrapper-chart-NWyfH" src="https://datawrapper.dwcdn.net/NWyfH/6/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="444" data-external="1"></iframe><script type="text/javascript">window.addEventListener("message",function(a){if(void 0!==a.data["datawrapper-height"]){var e=document.querySelectorAll("iframe");for(var t in a.data["datawrapper-height"])for(var r,i=0;r=e[i];i++)if(r.contentWindow===a.source){var d=a.data["datawrapper-height"][t]+"px";r.style.height=d}}});</script>
  </div>
</TextBlock>


 

<Block>


    <h2 id="youth-dev-crim-prevention" class="text-4xl font-semibold pt-4 pb-4">
      The Queens County DA's Office Invests Millions in Youth Development and Crime Prevention
    </h2>
<TextBlock>
  A prosecutor’s office has a role in the community that is broader than simply processing cases.  As an organization deeply rooted in its local community, the prosecutor’s office has an opportunity to use its human capital and resources to improve the long-term social, economic, and cultural well-being of the community - to act as a stabilizing force in civic life.  In addition to engaging the community through community events, the Queens County DA's Office also supports the community through Violence Prevention and Youth Development Grants.
</TextBlock>

<TextBlock>
  In 2024, the Office announced $2.75 million in funding for 34 community-based organizations for the second phase of the Office's Community Youth Development and Crime Prevention Project (CYDCPP), which seeks to foster positive relationships between communities and law enforcement, reduce youth crime, improve young people's self-confidence, increase exposure to positive adult role models, and strengthen academic performance and school attendance. Since 2021, the Office has provided $5.45 million in funding for the community.
</TextBlock>

</Block>

<div class="mx-auto grid place-content-center mt-16 max-w-800px">
  <img src={youthImage} alt='interns' class="sm:h-[600px]" /> 
  </div>
  <div class="mx-auto grid place-content-left max-w-[780px] text-xs text-gray-600 mb-16">
   Photo by: Queens DA's Office
  </div>
<Block>

<h2 id="anchor-detention-release-changed" class="text-3xl font-semibold pt-4 pb-4">
  $5.45M Million Invested From 2021-2024
</h2>

<TextBlock>
  Click the right or left arrows to view the many organizations the Queens County DA's Office has supported.
</TextBlock>


</Block>



  <CommunityGrants />



<Block>





<h2 id="youth-empowerment-unit" class="text-4xl font-semibold pt-4 pb-4">
  The Youth Empowerment Unit is in Every School District in Queens
</h2>

<TextBlock>
  A primary focus of the Office lies in supporting and encouraging youth. The Youth Empowerment Unit engaged over 40,000 young people across Queens County since 2022. The Unit’s programs are designed to cultivate young minds, strengthening their ability to think critically and communicate with mastery, thereby empowering them to navigate challenges and obstacles with confidence and maturity.  Community members may contact the Queens County DA’s Office to obtain more information about various educational programs offered by the Office, including: the Student Advisory Council; Legal Explorers Program; Hope and Leadership Academy; Summer Internship Program; and Court Tours Program.  The Office provides trainings and presentations to youth on topics including: workforce readiness skills for careers in law and law enforcement; positive police interaction; building healthy teenage relationships; internet safety; bullying; hate crimes; human trafficking; raising the age; bail reform; and immigration policy.
</TextBlock>

<TextBlock>
  <div class="mb-10 mt-10">
    <iframe title="The Youth Empowerment Unit is Active in Every School District in Queens (Copy)" aria-label="Choropleth map" id="datawrapper-chart-e1LDk" src="https://datawrapper.dwcdn.net/e1LDk/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="799" data-external="1"></iframe><script type="text/javascript">window.addEventListener("message",function(a){if(void 0!==a.data["datawrapper-height"]){var e=document.querySelectorAll("iframe");for(var t in a.data["datawrapper-height"])for(var r,i=0;r=e[i];i++)if(r.contentWindow===a.source){var d=a.data["datawrapper-height"][t]+"px";r.style.height=d}}});</script>

</TextBlock>



</Block>
 

<style>


  /* Scrollytelling CSS */
  .step {
    height: 90vh;
    display: flex;
    place-items: center;
    justify-content: center;
  }

  .step-content {
    background: whitesmoke;
    color: #ccc;
    border-radius: 5px;
    padding: 0.5rem 1rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    transition: background 500ms ease;
    box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.2);
    z-index: 10;
    max-width: 400px;
  }

  .step.active .step-content {
    background: white;
    color: black;
  }
</style>