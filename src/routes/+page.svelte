<script>
  import { onMount } from 'svelte';
  let scrollY = 0;
  let innerHeight = 0;

  // STEP MAPPING:
  // 300vh per step gives the card 100vh to enter, 100vh to stay, and 100vh to exit 
  // while the map remains stationary.
  $: currentStep = Math.floor(scrollY / (innerHeight * 3)); 
</script>

<svelte:window bind:scrollY={scrollY} bind:innerHeight={innerHeight} />

<section class="intro-screen" style:opacity={currentStep <= 1 ? 1 : 0} style:pointer-events={currentStep <= 1 ? 'auto' : 'none'}>
  <div class="intro-content">
    
    <div class="intro-text-wrapper" style:opacity={currentStep === 0 ? 1 : 0}>
      <h1 class="intro-title">The Hunt for Veerappan</h1>
      <div class="intro-scroll-hint">Scroll to follow the trail</div>
    </div>

    <div class="intro-text-wrapper" style:opacity={currentStep === 1 ? 1 : 0}>
      <h2 class="intro-subtitle">The Man and the Manhunt</h2>
      <p class="intro-paragraph">
      <strong>Koose Munisamy Veerappan</strong> was a master of the jungle who eluded the Special Task Forces for over twenty years. 
      Wanted for <strong>poaching, smuggling, and murder,</strong> he became the center of a manhunt that spilled across state lines. 
      But his true shield wasn't just the villagers, but it was his understanding of the <strong>forest and loopholes</strong> within the state bureaucracy.
      </p>
    </div>

  </div>
</section>

<div class="map-container" style:opacity={currentStep >= 2 ? 1 : 0}>
  
  <img 
    src="./Assets/base_with_area.png" 
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
    alt="Gopinatham" 
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
    src="./Assets/end_map.png" 
    alt="Endgame" 
    class="map-layer" 
    style:opacity={currentStep === 7 ? 1 : 0} 
  />
</div>

<div class="content">
  <section class="long-step spacer"></section>
  <section class="long-step spacer"></section>

  <section class="long-step">
    <div class="text-card">
      <h1>The Southern Frontier</h1>
      <p>The hunt spanned the <strong>tri-state border</strong> a landscape where administrative lines were as tangled as the forest itself. For decades, these lines were the state's only tool.</p>
    </div>
  </section>

  <section class="long-step">
    <div class="text-card">
      <h1>The Empire of Forests</h1>
      <p> Between these states lies a large, connected forest landscape. Police accounts in the 1990s put his primary operating zone at roughly <strong>6,000 sq km (est.) of terrain </strong> that provided a natural "stealth mode" where aerial surveillance failed against the dense canopy.</p>
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
      <h1>The End Game</h1>
      <p> On 18 October 2004, Veerappan was killed in an STF operation (often referred to as Operation Cocoon) near Papparapatti in Dharmapuri district, Tamil Nadu, after being lured out under the pretext of medical treatment in an ambulance. <strong>The end came fast once he was outside the terrain that had protected him.</strong> </p>
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

  /* INTRO: #e5faad Background */
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

  /* MAP SYSTEM (The stationary background) */
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
    /* 1.4s weighted cross-fade for the Shifting Grounds feel */
    transition: opacity 1.4s cubic-bezier(0.4, 0, 0.2, 1);
  }

  /* NARRATIVE SCROLLING (The traveling cards) */
  .content { position: relative; z-index: 10; }
  
  .long-step {
    height: 300vh; /* Increased to ensure the map stays static while the card travels */
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
    /* Shifting Grounds card entry/exit fade */
    transition: opacity 0.8s ease, transform 1s ease-out;
  }

  h1 { font-size: 2.2rem; margin-top: 0; font-weight: 800; color: #000; margin-bottom: 1.5rem; letter-spacing: -1px; }
  /*.highlight h1 { border-bottom: 5px solid #FF4500; } */
  p { line-height: 1.8; font-size: 1.3rem; color: #333; margin: 0; }
</style>