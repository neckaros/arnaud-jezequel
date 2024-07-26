<script lang="ts">
	import SkillProgress from "$lib/components/skill-progress.svelte";
    import { Progress } from "$lib/components/ui/progress";
import { Github, Mail, Check } from 'lucide-svelte';
  </script>

<div class="flex justify-center items-center h-full">
<div class="max-w-screen-xl w-full h-full">
    <div class="grid grid-cols-[300px_1fr] m-4 h-full">
        <div class="bg-card shadow-md rounded-sm p-2 flex flex-col">
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
                <div class="flex"><Check class="text-accent-foreground" />Agilité, Agilité à l'echelle</div>
                <div class="flex"><Check class="text-accent-foreground" />Management d'équipe</div>
            </div>

            <div class="flex flex-col m-2 space-y-2">
                <SkillProgress value={100} name="Excel" />
            </div>

            
        

            <div class="flex flex-col m-2 space-y-2">
                <SkillProgress value={90} name="Javascript/TS" />
                <SkillProgress value={70} name="Rust" />
                <SkillProgress value={70} name="Swift" />
                <SkillProgress value={60} name="Java/Kotlin" />
                <SkillProgress value={60} name="C#" />
                <SkillProgress value={60} name="Dart/Flutter" />
            </div>
           
        </div>
        <div class="ml-4 flex flex-col space-y-4">
            <div class="bg-card shadow-md rounded-sm p-2">
                <div class="font-mono font-bold text-xl">Experiences professionnelles</div>
                <div>Société Générale</div>
                
            </div>
            
            <div class="bg-card shadow-md rounded-sm p-2">
                <div class="font-mono font-bold text-xl">Études</div>
                <div>Master KEDGE Marseille</div>
                <div>Bachelor of Arts en management cross-culturel</div>
                
            </div>

        </div>
      </div>
</div>
</div>