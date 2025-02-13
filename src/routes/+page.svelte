<script lang="ts">
	import Experience from "$lib/components/experience.svelte";
	import Experiences from "$lib/components/experiences.svelte";
    import SkillProgress from "$lib/components/skill-progress.svelte";
    import { Progress } from "$lib/components/ui/progress";
    import { Github, Mail, PhoneCall, CircleUser, Phone, Sun, Moon, Printer, Link } from 'lucide-svelte';
    import * as Tooltip from "$lib/components/ui/tooltip";
	import { mode, toggleMode } from "mode-watcher";
	import Point from "$lib/components/point.svelte";
	import { PointType } from "../interfaces.ts/point-type";

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
                <div class="py-2 text-muted-foreground font-bold text-md text-center">Responsable Projets informatiques</div>
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
                    <div class="flex"><div class="flex-1 font-bold">Ville:</div><div>
                        <Tooltip.Root>
                            <Tooltip.Trigger>Lyon, France</Tooltip.Trigger>
                            <Tooltip.Content>
                              <img src="/map.jpg" alt="Ouest lyonnais">
                            </Tooltip.Content>
                        </Tooltip.Root>
                        
                    </div></div>
                    <div class="flex"><div class="flex-1 font-bold">Age:</div><div>{calculateAge()} ans</div></div>
                </div>
                <div class="hidden print:flex flex-col w-full space-y-2 text-sm">
                    <div class="flex space-x-2"><CircleUser /><span class="font-bold">{calculateAge()} ans,  Lyon</span></div>
                    <div class="flex space-x-2"><Link /><span class="font-bold">arnaud.jezequel.org</span></div>
                    <div class="flex space-x-2"><Mail /><span class="font-bold">arnaud.jezequel@gmail.com</span></div>
                    <div class="flex space-x-2"><PhoneCall /><span class="font-bold">+33 6 79 79 01 57</span></div>
                  <div class="flex space-x-2"><Github /><span class="font-bold">@neckaros</span></div>
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
                <SkillProgress value={100} name="Français" />
                <SkillProgress value={90} name="Anglais" />
            </div>

            <div class="flex flex-col m-4 space-y-2">
                <Point>Agilité, Agilité à l'echelle</Point>
                <Point>Management d'équipe</Point>
                <Point>Relations clients</Point>
            </div>

            <div class="flex flex-col m-4 space-y-2">
                <SkillProgress value={100} name="Excel" />
            </div>

            
        

            <div class="flex flex-col m-4 space-y-2">
                <SkillProgress value={90} name="Javascript/TS" />
                <SkillProgress value={80} name="Rust" />
                <SkillProgress value={70} name="Swift" />
                <SkillProgress value={60} name="Java/Kotlin" />
                <SkillProgress value={60} name="C#" />
                <SkillProgress value={60} name="Dart/Flutter" />
            </div>
        </div>
        <div class="w-full flex flex-col space-y-2 lg:space-y-4 print:space-y-1">
            <Experiences titre={`Experiences professionnelles (${new Date().getFullYear() - 2009} ans)`}>
               
                <Experience titre="Directeur de programme en informatique" societe="Société Générale" debut="Mai 2021" fin="Oct 2024">
                    <div class="text-justify">Refonte du système informatique pour les produits actions et leurs dérivés pour la banque d'investissement de la Société Générale.<br/>Calcule en temps réel de l'exposition pour le trading et calcule des métriques officielles de risques, et de pertes et profits pour les fonctions support.</div>
                    <Point>De l'idéation aux premières mises en production, en passant par l'étude de faisabilité technique et revue "frugale" du budget et des attendus</Point>
                    <Point>Programme de 55 millions d'euros sur 8 ans</Point>
                    <Point>Suivi de 6 streams avec des gestionnaires de projets</Point>
                    <Point>Management d'une équipe de 8 Développeurs et 4 Business analysts</Point>
                    <Point>Méthodologie Agile à l'echelle</Point>
                    <Point>Suivi et négociation des budgets</Point>
                </Experience>
                <Experience titre="Responsable équipe projet FRTB" societe="Société Générale" debut="Mai 2017" fin="Mai 2021">
                    <div class="text-justify">En réponse à une nouvelle réglementation de la Banque Centrale Européenne: refonte des métriques des risques de marché.</div>
                    <Point>Équipe de 8 personnes (Développeurs et Business analysts)</Point>
                    <Point>Méthodologie Agilité à l'échelle avec des P.I. (Program Increment: regroupement de plusieurs sprints avec gestion des interactions entre les équipes du programme)</Point>
                    <Point>Implémentation des métriques spécifiques FRTB et autres demandes du régulateur (EMIR, PRIIPS KID, MIFID...)</Point>  
                </Experience>
                <Experience titre="Responsable catalogue" societe="Société Générale"  debut="Mai 2014" fin="Mai 2017">
                    <Point>Un developpeur à Paris et 3 à Bangalore en Inde</Point>
                    <Point>Responsable des relations Paris/Inde</Point>
                </Experience>
                <Experience titre="Analyste fonctionnel" societe="Consultant MWA pour Société Générale"  debut="Mar 2010" fin="Mai 2014">
                    <Point>Recueil et étude des demandes du business, Implémentation et cahier de tests</Point>
                </Experience>
                <Experience titre="Développeur Excel/VBA" societe="Stagiaire chez Dexia, Luxembourg"  debut="Jan 2009" fin="Sept 2009">
                    <Point>Création d'un outil Excel en VBA de suivi des positions pour les gestionnaires de portefeuilles</Point>
                </Experience>
            </Experiences>

           
            <Experiences titre="Projets personnels">
                <Experience titre="Redseat">
                    <Point>Application web en Svelte, Swift pour iOS et Kotlin pour Android TV</Point>
                    <Point>Serveur en Rust</Point>
                    <Point type={PointType.Link}><a href="https://www.redseat.cloud" target="_blank" class="underline hover:text-accent-foreground">https://www.redseat.cloud</a></Point>
                </Experience>
                <Experience titre="Flutter packages">
                    <Point>500 Likes, 94% de popularité sur pub.dev et +100 favoris sur Github</Point>
                    <Point type={PointType.Link}><a href="https://pub.dev/publishers/jezequel.org/packages" target="_blank" class="underline hover:text-accent-foreground">pub.dev/publishers/jezequel.org/packages</a></Point>
                </Experience>
            </Experiences>

            <Experiences titre="Études">
                <Experience titre="Master Ecole de Management spécialisation Finance" societe="KEDGE Business School - Marseille" fin="2010">
                </Experience>
                <Experience titre="Bachelor of Arts Cross Cultural Management" societe="Leeds Metropolitan University - Angleterre" fin="2007">
                </Experience>
            </Experiences>

            <Experiences titre="Hobbies">
                Cinéma, Tennis, Football
            </Experiences>

        </div>
      </div>
      
<a href="https://github.com/neckaros/arnaud-jezequel" target="_blank" class="print:hidden flex items-center justify-center m-2 italic font-mono text-sm">Open source by Arnaud JEZEQUEL - Sources</a>
</div>

</div>
