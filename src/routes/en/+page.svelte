<script lang="ts">
	import Experience from "$lib/components/experience.svelte";
	import Experiences from "$lib/components/experiences.svelte";
    import SkillProgress from "$lib/components/skill-progress.svelte";
    import { Progress } from "$lib/components/ui/progress";
    import { Github, Mail, PhoneCall, CircleUser, Phone, Sun, Moon, Printer, Link } from 'lucide-svelte';
    import * as Tooltip from "$lib/components/ui/tooltip";
	import { mode, toggleMode } from "mode-watcher";
	import Point from "$lib/components/point.svelte";
	import { PointType } from "../../interfaces.ts/point-type";

    function calculateAge() { // birthday is a date
        const birthday = new Date('1985-05-31T00:00:00');
        var ageDifMs = Date.now() - birthday.getTime();
        var ageDate = new Date(ageDifMs); // miliseconds from epoch
        return Math.abs(ageDate.getUTCFullYear() - 1970);
    }

  </script>

<div class="flex justify-center items-center h-full ">
<div class="max-w-screen-xl w-full h-full">
    <div class="flex space-x-0 space-y-2 lg:space-x-4 lg:space-y-0 print:space-y-0 flex-col print:flex-row lg:flex-row m-2 lg:m-4 print:m-1 h-full print:space-x-1">
        <div class="bg-card shadow-md rounded-sm print:shadow-transparent flex flex-col w-full lg:w-96 print:w-80 print:space-y-2">
            <div class="flex bg-card-alt rounded-t-sm justify-center items-center flex-col p-4 relative ">
                <img src="/photo.jpg" class="rounded-full w-32" alt="Portrait"/>
                <div class="pt-2 px-2 font-bold text-xl">Arnaud JEZEQUEL</div>
                <div class="py-2 text-muted-foreground font-bold text-md text-center">IT Project Manager</div>
                <div class="flex  space-x-2 print:hidden">
                    <Tooltip.Root>
                        <Tooltip.Trigger><a href="https://www.github.com/neckaros" class="hover:text-accent-foreground" target="_blank"><Github /></a></Tooltip.Trigger>
                        <Tooltip.Content>
                          <p>@neckaros</p>
                        </Tooltip.Content>
                    </Tooltip.Root>

                    <Tooltip.Root>
                        <Tooltip.Trigger><a href="mailto:arnaud.jezequel@gmail.com" class="hover:text-accent-foreground" target="_blank"><Mail /></a></Tooltip.Trigger>
                        <Tooltip.Content>
                          <p>arnaud.jezequel@gmail.com</p>
                        </Tooltip.Content>
                    </Tooltip.Root>
                    
                    <Tooltip.Root>
                        <Tooltip.Trigger><a href="tel:+33679790157" class="hover:text-accent-foreground" target="_blank"><Phone /></a></Tooltip.Trigger>
                        <Tooltip.Content>
                          <p>06 79 79 01 57</p>
                        </Tooltip.Content>
                    </Tooltip.Root>
                    <Tooltip.Root>
                        <Tooltip.Trigger><a href="javascript:if(window.print)window.print()" class="hover:text-accent-foreground"><Printer /></a></Tooltip.Trigger>
                        <Tooltip.Content>
                          <p>Print</p>
                        </Tooltip.Content>
                    </Tooltip.Root>
                    
                </div>
                <div class="flex flex-col w-full m-2 print:hidden">
                    <div class="flex"><div class="flex-1 font-bold">City:</div><div>
                        <Tooltip.Root>
                            <Tooltip.Trigger>Lyon, France</Tooltip.Trigger>
                            <Tooltip.Content>
                              <img src="/map.jpg" alt="Ouest lyonnais">
                            </Tooltip.Content>
                        </Tooltip.Root>
                        
                    </div></div>
                    <div class="flex"><div class="flex-1 font-bold">Age:</div><div>{calculateAge()}</div></div>
                </div>
                <div class="hidden print:flex flex-col w-full space-y-2 text-sm">
                    <div class="flex space-x-2"><CircleUser /><span class="font-bold">{calculateAge()} ans,  Lyon</span></div>
                    <a href="https://arnaud.jezequel.org" class="flex space-x-2" target="_blank"><Link /><span class="font-bold">arnaud.jezequel.org</span></a>
                    <a href="mailto:arnaud.jezequel@gmail.com" class="flex space-x-2" target="_blank"><Mail /><span class="font-bold">arnaud.jezequel@gmail.com</span></a>
                    <a href="tel:+33679790157" class="flex space-x-2" target="_blank"><PhoneCall /><span class="font-bold">+33 6 79 79 01 57</span></a>
                  <a href="https://www.github.com/neckaros" class="flex space-x-2" target="_blank"><Github /><span class="font-bold">@neckaros</span></a>
                </div>
                <button class="absolute top-0 right-0 p-3 print:hidden" onclick={() => toggleMode()}>
                    {#if $mode === "dark"}
                    <Sun />
                    {:else}
                    <Moon />
                    {/if}
                </button>
            </div>
           


            <div class="flex flex-col m-4 space-y-2">
                <SkillProgress value={100} name="French" />
                <SkillProgress value={90} name="English" />
            </div>
            <br/>

            <div class="flex flex-col m-4 space-y-2">
                <Point>Agility, Agility at scale</Point>
                <Point>Team Management</Point>
                <Point>Client relationships</Point>
            </div>
            <br/>
            <div class="flex flex-col m-4 space-y-2">
                <SkillProgress value={70} name="Front risk" />
                <SkillProgress value={90} name="Risk metrics" />
                <SkillProgress value={80} name="Credit derivatives " />
                <SkillProgress value={70} name="Equity derivatives" />
            </div>
            <br/>
            <div class="flex flex-col m-4 space-y-2">
                <SkillProgress value={100} name="Excel" />
				<SkillProgress value={80} name="LLM" />
            </div>

            
        <br/>

            <div class="flex flex-col m-4 space-y-2">
                <SkillProgress value={90} name="Javascript/TS" />
                <SkillProgress value={80} name="Rust" />
                <SkillProgress value={70} name="Swift" />
				<SkillProgress value={60} name="Python" />
                <SkillProgress value={60} name="Java/Kotlin" />
                <SkillProgress value={60} name="C#" />
                <SkillProgress value={60} name="Dart/Flutter" />
				<SkillProgress value={60} name="Databases (SQL, noSQl, VectorDB...)" />
            </div>
        </div>
        <div class="w-full flex flex-col space-y-2 lg:space-y-4 print:space-y-1">
            <Experiences titre={`Professional Experiences (${new Date().getFullYear() - 2009} years)`}>



<Experience titre="AI Specialist" societe="via Flowful.ai" debut="August 2025" fin="">
                    <div class="text-justify">Creation of chatbots and automation tools using LLM for private companies<br/>
                    <Point>Creation of AI Agents to answear employees technical and commercial questions using compagny knowledge</Point>
                    <Point>Help for xreztion of professional documents</Point>
                    <Point>Using librechat, langchain (python), RAG embeddings (postgre, pinecone...), ChatGPT, Claude and Gemini</Point>
                </Experience>


                <Experience titre="IT Program Director" societe="Société Générale, Paris" debut="May 2021" fin="Oct 2024">
                    <div class="text-justify">Redesign of the worldwide IT system for equity products and their derivatives for Société Générale's investment banking.<br/>
                        Real-time calculation of trading exposure and calculation of official risk metrics, and profit and loss for support functions.</div>
                    <Point>From ideation to initial production runs, including technical feasibility studies and a 'frugal' review of the budget and expectations.</Point>
                    <Point>55 million euros program over 8 years</Point>
                    <Point>Oversight of 6 streams with coordination between project managers and the business</Point>
                    <Point>Management of a team of 8 Developers and 4 Business Analysts.</Point>
                    <Point>Agile@Scale methodology</Point>
                    <Point>Budget monitoring and negotiation</Point>
                </Experience>
            
                <Experience titre="FRTB Project Team Leader" societe="Société Générale, Paris" debut="May 2017" fin="May 2021">
                    <div class="text-justify">In response to new European Central Bank regulation: redesign of market risk metrics.</div>
                    <Point>Work in agile with the business</Point>
                    <Point>Implementation of FRTB Metrics plus other regulatory metrics (EMIR, PRIIPS KID, MIFID...)</Point>
                    <Point>Team of 8 people</Point>
                    <Point>Scaled Agile methodology with P.I. (Program Increment: grouping of multiple sprints with management of interactions between program teams)</Point>
                </Experience>
            
                <Experience titre="Risk Catalog Manager" societe="Société Générale, Paris" debut="May 2014" fin="May 2017">
                    <Point>One developer in Paris and 3 in Bangalore, India</Point>
                    <Point>Responsible for Paris/India relationships</Point>
                </Experience>
            
                <Experience titre="Functional Analyst" societe="MWA Consultant for Société Générale, Paris" debut="Mar 2010" fin="May 2014">
                    <Point>Gathering and analysis of business requirements, implementation and test documentation for credit derivatives</Point>
                </Experience>
            
                <Experience titre="Excel/VBA Developer" societe="Intern at Dexia, Luxembourg" debut="Jan 2009" fin="Sept 2009">
                    <Point>Creation of an Excel VBA tool for portfolio managers to track positions</Point>
                </Experience>
            
            </Experiences>

           
            <Experiences titre="Personal projects">
                <Experience titre="Redseat">
                    <Point>Web Svelte application, Swift pour iOS et Kotlin pour Android TV</Point>
                    <Point>Server in Rust</Point>
                    <Point type={PointType.Link}><a href="https://www.redseat.cloud" target="_blank" class="underline hover:text-accent-foreground">https://www.redseat.cloud</a></Point>
                </Experience>
                <Experience titre="Flutter packages">
                    <Point>500 Likes, 94% de popularity on pub.dev and +100 favorites on Github</Point>
                    <Point type={PointType.Link}><a href="https://pub.dev/publishers/jezequel.org/packages" target="_blank" class="underline hover:text-accent-foreground">pub.dev/publishers/jezequel.org/packages</a></Point>
                </Experience>
            </Experiences>

            <Experiences titre="Studies">
                <Experience titre="Master Business School with specialization in Finance" societe="KEDGE Business School - Marseille" fin="2010">
                </Experience>
                <Experience titre="Bachelor of Arts Cross Cultural Management" societe="Leeds Metropolitan University - U.K." fin="2007">
                </Experience>
            </Experiences>

            <Experiences titre="Hobbies">
                Cinema, Tennis, Football
            </Experiences>

        </div>
      </div>
      
<a href="https://github.com/neckaros/arnaud-jezequel" target="_blank" class="print:hidden flex items-center justify-center m-2 italic font-mono text-sm">Open source by Arnaud JEZEQUEL - Sources</a>
</div>

</div>
