

<div class="flex flex-col justify-between bg-black h-[126px]">
    <div class="mt-8  border-t-2 border-white ">
  </div>
      <header class="flex items-center justify-between xl:ml-32 xl:mr-32 ml-10 mr-10  sm:mb-0">
        
        <div>
          <a href="https://loyolaccj.org" >
            <div class="flex items-center justify-between">
              
 
            </div>
        </a>
        </div>
        <div class="flex items-center  ">
        <div>
            
            </div>
          <div class="hidden sm:block lg:space-x-8 space-x-6">
          
        


            {#each headerNavLinks as link}
              <span                   id={link.title} class=' border-white hover: hover:border-b-2 hover:border-b-lblue-500 xl:text-xl font-mono text-bold '>
              <a
                href={link.href}
                class="p-1  font-bold"
              >
                {link.title}
              </a>
              </span>
              {/each}
          </div>

          
        </div>
        <div class="lg:mr-3 lg:hidden">
  
    

              </div>


      </header>
      <div class=" border-t-2 border-white ">
      <div class=' bg-black'></div>
  </div>

    </div>