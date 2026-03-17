<script>
  import { onMount } from 'svelte';
  let scrollY = 0;
  let innerHeight = 0;

  // STEP MAPPING:
  $: currentStep = Math.floor(scrollY / (innerHeight * 3)); 
</script>

<svelte:window bind:scrollY={scrollY} bind:innerHeight={innerHeight} />

<section class="intro-screen" style:opacity={currentStep <= 1 ? 1 : 0} style:pointer-events={currentStep <= 1 ? 'auto' : 'none'}>
  <div class="intro-content">
    
    <div class="intro-text-wrapper" style:opacity={currentStep === 0 ? 1 : 0}>
      <h1 class="intro-title">The Veerappan Story</h1>
      <p class="intro-paragraph">He was a poacher. A smuggler. A murderer wanted by two states. But was also the reason this forest survived.</p>
      <div class="intro-scroll-hint">Scroll to follow the trail</div>
    </div>

    <div class="intro-text-wrapper" style:opacity={currentStep === 1 ? 1 : 0}>
      <h2 class="intro-subtitle">The Man and the Manhunt</h2>
      <p class="intro-paragraph">
      For over twenty years, <strong>Koose Munisamy Veerappan</strong> ran a criminal empire from inside this forest. 
      Wanted for poaching, smuggling, and over 184 murders, he became the <strong>most hunted man in India.</strong> 
      Thousands of officers. Helicopters, informants, special task forces. None of it worked.
      </p>
    </div>

  </div>
</section>

<div class="map-container" style:opacity={currentStep >= 2 ? 1 : 0}>
  
  <img 
    src="./Assets/two_state.png" 
    alt="Regional" 
    class="map-layer" 
    style:opacity={currentStep === 2 ? 1 : 0} 
  />

  <img 
    src="./Assets/base_area_1.png" 
    alt="Empire" 
    class="map-layer" 
    style:opacity={currentStep === 3 ? 1 : 0} 
  />

  <img 
    src="./Assets/base_area_2.png" 
    alt="Gopinatham" 
    class="map-layer" 
    style:opacity={currentStep === 4 ? 1 : 0} 
  />

  <img 
    src="./Assets/base_area_riv.png" 
    alt="Gopinatham River" 
    class="map-layer" 
    style:opacity={currentStep === 5 ? 1 : 0} 
  />

  <video 
    src="./Assets/desktop.mp4" 
    class="map-layer" 
    autoplay 
    muted 
    loop 
    playsinline
    style:opacity={currentStep === 6 ? 1 : 0}
  >
    <track kind="captions" />
  </video>

  
   <img 
    src="./Assets/Dum.png" 
    alt="Gopinatham River" 
    class="map-layer" 
    style:opacity={currentStep === 7 ? 1 : 0} 
  />

   <div 
    class="map-layer solid-green-bg" 
    style:opacity={currentStep === 8 ? 1 : 0}>
  </div>

  <img 
    src="./Assets/end_game.png" 
    alt="Endgame" 
    class="map-layer" 
    style:opacity={currentStep === 9 ? 1 : 0} 
  />

<img 
    src="./Assets/tree_cv.png" 
    alt="Endgame" 
    class="map-layer" 
    style:opacity={currentStep === 10 ? 1 : 0} 
  />  
</div>

<div class="content">
  <section class="long-step spacer"></section>
  <section class="long-step spacer"></section>

  <section class="long-step">
    <div class="text-card">
      <h1>The Southern Frontier</h1>
      <p>The hunt spanned the <strong>two-state border</strong> a landscape where administrative lines were as tangled as the forest itself.</p>
    </div>
  </section>

  <section class="long-step">
    <div class="text-card">
      <h1>The Empire of Forests</h1>
      <p> Between these states lies a large, connected forest landscape. Police accounts in the 1990s put his primary operating zone at roughly <strong>15,000 sq km (est.) of terrain </strong> that provided a natural "stealth mode" where aerial surveillance failed against the dense canopy.</p>
    </div>
  </section>

  <section class="long-step">
    <div class="text-card highlight">
      <h1>Born on the Edge</h1>
      <p>This is Gopinatham village where Veerappan was born. By living exactly on the border, he turned a bureaucratic line into a door, slipping through jurisdictions whenever the chase got too close.</p>
    </div>
  </section>

  <section class="long-step">
    <div class="text-card highlight">
      <h1>Jurisdiction Game</h1>
      <p> He played the "Jurisdictional Game." When Karnataka police chased him, he simply rafted 100 meters across the water into Tamil Nadu. The police, bound by state laws, had to stop at the bank. He didn't hide in the trees; he hid in the blind spots of bureaucracy. </p>
    </div>
  </section>

  <section class="long-step">
    <div class="text-card highlight">
      <h1>The Friction</h1>
      <p> The Special Task Force (STF) was confined to the few paved roads like the Dimbam Ghat, a choke point with 27 hairpin bends. Veerappan moved through ancient elephant corridors and goat paths that appeared on no government map. While police crawled at 20 km/h on the road, he moved perpendicular to them, invisible and unreachable. </p>
    </div>
  </section>

  <section class="long-step">
    <div class="text-card highlight">
      <h1>The "Forest King"</h1>
      <p> Veerappan didn’t just survive the jungle; he weaponized the poverty within it. To the outside world, he was a smuggler. But inside that 15,000 sq km bubble, he became the "Forest King". He became the primary employer through his smuggling syndicate. He became the local justice system, ruling through a terrifying mix of Robin Hood-style patronage and brutal executions. </p>
    </div>
  </section>

  <section class="long-step">
    <div class="intermission-text">
      <h2>The Cost of Trust</h2>
      <p>
        While the state brought helicopters, one man brought humanity. <strong>P. Srinivas</strong>, an Indian Forest Service officer, took an entirely different approach. Instead of raiding the villages, he rebuilt their ruined temple, started a medical dispensary, and gave the locals honest jobs. 
      </p>
      <p>
        By treating the villagers as citizens rather than suspects, Srinivas began dismantling the <strong>"Forest King's"</strong> socio-cultural shield, gaining the one thing the police never had: <strong>the locals' trust</strong>. Recognizing this as an existential threat, Veerappan tricked Srinivas into an unarmed meeting and brutally murdered him in 1991. It was tragic proof that the true battleground wasn't the forest; it was the people.
      </p>
    </div>
  </section>

  <section class="long-step">
    <div class="text-card highlight">
      <h1>The End Game</h1>
      <p> Operation Cocoon finally worked because the police realized they couldn't beat him inside his own ecosystem. They couldn't out-navigate him in the terrain, and they couldn't break his socio-cultural grip on the locals. The only way to win was to sever him from both. They lured him out of the canopy and away from his people, ending a 20-year reign on an empty, paved road.</p>
    </div>
  </section>

 <section class="long-step">
    <div class="text-card highlight">
      <h1>"What happened to the forest"</h1>
      <p> Here is the forest in 2000 vs the same forest in 2010. Six years after his death. For decades, Veerappan’s presence made the MM Hills a "no-go" zone for state. While he poached ivory and sandalwood, his violence inadvertently shielded the core forest from large-scale development. Human encroachment and infrastructure are now thining the margins of a terrain once protected by terror. </p>
    </div>
  </section>

</div>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
    background-color: #000;
    font-family: 'Georgia', serif;
    overflow-x: hidden;
  }

  /* INTRO */
  .intro-screen {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #e5faad; 
    z-index: 100;
    text-align: center;
    transition: opacity 1.2s cubic-bezier(0.4, 0, 0.2, 1);
  }

  .intro-content { position: relative; width: 100%; height: 100%; display: flex; justify-content: center; align-items: center; }

  .intro-text-wrapper {
    position: absolute;
    max-width: 850px;
    padding: 2rem;
    transition: opacity 1s cubic-bezier(0.4, 0, 0.2, 1);
  }

  .intro-title { font-size: 5rem; font-weight: 900; color: #383838; letter-spacing: -3px; }
  .intro-subtitle { font-size: 2.5rem; font-weight: 800; color: #383838; margin-bottom: 1.5rem; }
  .intro-paragraph { font-size: 1.5rem; color: #383838; line-height: 1.7; opacity: 0.9; }
  .intro-scroll-hint { margin-top: 4rem; color: #383838; letter-spacing: 0.1rem; font-size: 0.9rem; font-weight: 500; opacity: 0.5; }

  /* MAP SYSTEM */
  .map-container {
    position: sticky;
    top: 0;
    height: 100vh;
    width: 100%;
    z-index: 1;
    background: black;
  }

  .map-layer {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: contain;
    transition: opacity 1.4s cubic-bezier(0.4, 0, 0.2, 1);
  }

  /* The Solid Green Map Layer */
  .solid-green-bg {
    background-color: #e5faad;
    z-index: 0;
  }

  /* NARRATIVE SCROLLING */
  .content { position: relative; z-index: 10; }
  
  .long-step {
    height: 300vh; 
    display: flex;
    flex-direction: column;
    justify-content: center; 
    align-items: center;
  }

  .spacer { height: 300vh; }

  .text-card {
    background: rgba(255, 255, 255, 0.98);
    color: #1a1a1a;
    padding: 3.5rem;
    max-width: 550px;
    border-radius: 2px;
    box-shadow: 0 40px 100px rgba(0,0,0,0.6);
    transition: opacity 0.8s ease, transform 1s ease-out;
  }

  h1 { font-size: 2.2rem; margin-top: 0; font-weight: 800; color: #000; margin-bottom: 1.5rem; letter-spacing: -1px; }
  p { line-height: 1.8; font-size: 1.3rem; color: #333; margin: 0; }

  /* Styling for the Intermission Text (No shadows or background) */
  .intermission-text {
    max-width: 800px;
    text-align: center;
    color: #2c2c2c;
    padding: 2rem;
  }

  .intermission-text h2 {
    font-size: 2.5rem;
    margin-bottom: 1.5rem;
    font-weight: 700;
  }

  .intermission-text p {
    font-size: 1.25rem;
    line-height: 1.8;
    margin-bottom: 1.5rem;
    color: #2c2c2c;
  }

  .intermission-text strong {
    font-weight: 700;
    color: #1a1a1a;
  }
</style>