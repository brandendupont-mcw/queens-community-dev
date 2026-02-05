
<script>

const authors = ["Patrick Griffin", 'Branden DuPont',"Don Stemen","Dave Olson","Amanda Ward", ]

const credit ="Photo by: Queens County DA's Office"
const logo1 ="https://live.staticflickr.com/65535/53180586213_c2b8352ee0_4k.jpg"
const logo5 ="https://live.staticflickr.com/65535/52958044188_9e5026e0f8_b.jpg"
const logo2 ="https://live.staticflickr.com/65535/52958044188_9e5026e0f8_b.jpg"
const logo3 = "https://live.staticflickr.com/65535/53765406032_51920c548a_b.jpg"
const logo4 ="https://live.staticflickr.com/65535/52958045238_8897b90922_b.jpg"


import logo from '$lib/assets/images/20230801_185355.jpg';

//import logo from '$lib/assets/images/capitol.jpg';
//import logo from '$lib/assets/images/pfa-report-image-2.png';
</script>
<div class="max-w-4xl  lg:max-w-full sm:pb-[100px]" >
  

    <section class="overflow-hidden bg-black lg:grid lg:grid-cols-2 ">
      <div class="relative sm:hidden">
      <img
      alt="Image of Queens"
      src={logo }
      aria-label="Image of Queens"
      class=" w-full h-[200px] sm:hidden "
    />
    <div class="absolute bottom--6 right-2  ">
    <div class="text-white text-[8px] floating-right sm:block"><div class="" >{credit}</div></div>
  </div>
</div>
      <div class="p-8 md:p-12   grid place-items-center">
        
        <div class="sm:mt-10">
        <div class="mx-auto max-w-xl grid sm:text-left">
          <h2 class="font-mono  text-white  2xl:text-5xl lg:text-4xl  text-4xl font-sans mb-6 ">
            Across Queens, the DA Centers the Community in Public Safety
          </h2>
          <p class="text-gray-300 xl:text-base  text-sm">
            The Queens County District Attorney’s Office seeks to re-imagine the relationship between the prosecutor’s office and the residents of Queens County by being an integral part of the community. Through numerous initiatives — including the creation of the Community Partnerships Division, the Youth Empowerment Unit, and the distribution of Violence Prevention and Youth Development Grants — the Office is working collaboratively across neighborhoods to create and realize a sustainable future for Queens.

          </p>
          
          <span class="  font-semibold text-white mt-4"> </span> 
          <ul class="flex flex-row  flex-wrap text-white ">
            <li class="font-semibold text-white pr-1 xl:text-base  text-xs ">By:</li> 

               <li class="flex flex-wrap max-w-sm" >

                 <dl class=" font-semibold xl:text-base  text-xs">
                  The Queens County DA's Office
                   <dd>

                   </dd>
            
                 </dl>
               </li>

           </ul>
    
    
                    <div class='mt-2'>
                      <dd class=" sm:text-sm  text-xs  text-white ">
                        <time >
                          Report Updated: 2/5/2026
                        </time>
                      </dd>
                    </div>
    
        </div>
    </div>
      </div>
    
    <div class='relative sm:block hidden'>
      <img
        alt="Image of the Illinois State Capitol by Andrew Adams"
        src={logo }
        aria-label="Image of the Illinois State Capitol by Andrew Adams"
        class=" w-full   md:h-[450px] lg:h-[450px] xl:h-[600px] 2xl:h-[650px]"
      />
      <div class="absolute bottom-2 right-2  ">
      <div class="text-white text-xs floating-right"><div class="" >{credit}</div></div>
    </div>
      </div>
      
    </section>
    

    
    </div>