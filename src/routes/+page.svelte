<script lang="ts">
	import Experience from "$lib/components/experience.svelte";
	import Experiences from "$lib/components/experiences.svelte";
import SkillProgress from "$lib/components/skill-progress.svelte";
    import { Progress } from "$lib/components/ui/progress";
import { Github, Mail, Check, Link } from 'lucide-svelte';
  </script>

<div class="flex justify-center items-center h-full">
<div class="max-w-screen-xl w-full h-full">
    <div class="flex space-x-0 space-y-4 lg:space-x-4 lg:space-y-0 flex-col lg:flex-row m-4 h-full">
        <div class="bg-card shadow-md rounded-sm p-2 flex flex-col w-full lg:w-96">
            <div class="flex justify-center items-center flex-col m-2">
                <img src="/photo.jpg" class="rounded-full w-32" alt="Portrait"/>
                <div class="pt-2 px-2 font-bold text-xl">Arnaud JEZEQUEL</div>
                <div class="text-muted-foreground font-bold text-md">Responsable projet informatique</div>
                <div class="flex  space-x-2 m-2">
                    <a href="https://www.github.com/neckaros" class="hover:text-accent-foreground" target="_blank"><Github /></a>
                    
                    <a href="mailto:arnaud.jezequel@gmail.com" class="hover:text-accent-foreground" target="_blank"><Mail /></a>
                </div>
                <div class="flex flex-col w-full m-2">
                    <div class="flex"><div class="flex-1 font-bold">Ville:</div><div>Lyon</div></div>
                    <div class="flex"><div class="flex-1 font-bold">Age:</div><div>{new Date().getFullYear() - 1985}</div></div>
                </div>
                <div>
                </div>
            </div>
           


            <div class="flex flex-col m-2 space-y-2">
                <SkillProgress value={100} name="Français" />
                <SkillProgress value={90} name="Anglais" />
            </div>

            <div class="flex flex-col m-2 space-y-2">
                <div class="flex"><Check class="text-accent-foreground mr-2" />Agilité, Agilité à l'echelle</div>
                <div class="flex"><Check class="text-accent-foreground mr-2" />Management d'équipe</div>
            </div>

            <div class="flex flex-col m-2 space-y-2">
                <SkillProgress value={100} name="Excel" />
            </div>

            
        

            <div class="flex flex-col m-2 space-y-2">
                <SkillProgress value={90} name="Javascript/TS" />
                <SkillProgress value={80} name="Rust" />
                <SkillProgress value={70} name="Swift" />
                <SkillProgress value={60} name="Java/Kotlin" />
                <SkillProgress value={60} name="C#" />
                <SkillProgress value={60} name="Dart/Flutter" />
            </div>
           
        </div>
        <div class="w-full flex flex-col space-y-4">
            <Experiences titre="Experiences professionnelles">
               
                <Experience titre="Directeur de programme en informatique" societe="Société Générale" debut="Mai 2021" fin="Oct 2024">
                    <div class="text-justify">Refonte du système informatique pour les produits actions et leur dérivés pour la banque d'investissement de la Société Générale.<br/>Calcul en temps réel de l'exposition pour le trading et calcule des métriques officielles de risque et de pertes et profits pour les fonctions support.</div>
                    <div class="flex"><Check class="text-accent-foreground mr-2" />Programme de 55 millions d'euros</div>
                    <div class="flex"><Check class="text-accent-foreground mr-2" />Suivi de 6 streams avec des gestionnaire de projets</div>
                    <div class="flex"><Check class="text-accent-foreground mr-2" />Méthodologie Agile</div>
                    <div class="flex"><Check class="text-accent-foreground mr-2" />Suivi et néfociation des budgets</div>
                </Experience>
                <Experience titre="Responsable équipe projet FRTB" societe="Société Générale" debut="Mai 2018" fin="Mai 2021">
                    <div class="text-justify">En réponse à une nouvelle réglementation de la Banque Centrale Européenne: refonte des métriques de risque de marché.</div>
                    <div class="flex"><Check class="text-accent-foreground mr-2" />Équipe de 8 personnes</div>
                    <div class="flex"><Check class="text-accent-foreground mr-2" />Méthodologie Agilité à l'echelle avec des P.I. (Program Increment: regroupement de plusieurs sprints avec gestion des interactions entre les équipes du programme)</div>
                </Experience>
                <Experience titre="Analyste fonctionnel" societe="Consultant MWA pour Société Générale"  debut="Mar 2010" fin="Mai 2013">
                    <div class="flex"><Check class="text-accent-foreground mr-2" />Receuille et étude des demandes du business</div>
                    <div class="flex"><Check class="text-accent-foreground mr-2" />Implémentation et cahier de test</div>
                </Experience>
                
            </Experiences>

           
            <Experiences titre="Projets personnels">
                <Experience titre="Redseat">
                    <div class="flex"><Check class="text-accent-foreground mr-2" />Application web en svelte, Swift pour iOS et Kotlin pour Android TV</div>
                    <div class="flex"><Check class="text-accent-foreground mr-2" />Serveur en Rust</div>
                    <div class="flex"><Link class="text-accent-foreground mr-2" /><a href="https://www.redseat.cloud" target="_blank" class="underline">https://www.redseat.cloud</a></div>
                </Experience>
                <Experience titre="Flutter packages">
                    <div class="flex"><Check class="text-accent-foreground mr-2" />500 Likes et 94% de popularité sur pub.dev</div>
                    <div class="flex"><Check class="text-accent-foreground mr-2" />+100 favoris sur Github</div>
                    <div class="flex"><Link class="text-accent-foreground mr-2" /><a href="https://pub.dev/publishers/jezequel.org/packages" target="_blank" class="underline">pub.dev/publishers/jezequel.org/packages</a></div>
                </Experience>
            </Experiences>

            <Experiences titre="Études">
                <Experience titre="Master Ecole de management spécialisation Finance" societe="KEDGE Business School - Marseille" fin="2010">
                </Experience>
                <Experience titre="Bachelor of Arts Cross Cultural Management" societe="Leeds Metropolitan University - Angleterre" fin="2007">
                </Experience>
            </Experiences>

        </div>
      </div>
</div>
</div>