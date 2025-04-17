<script>
  import PortfolioItem from '$lib/components/PortfolioItem.svelte';
  
  // Flag to toggle between portfolio and about views
  let showPortfolio = true;
  
  const projects = [
    {
      image: '/deepDrawing.png',
      title: 'Deep Drawing',
      description: 'Current research project at the University of Michigan with professors Julie Zhu and John Granzow. Deep Drawing is an intermedia performance about the sound of drawing. Using live audio input captured from the human performer’s drawing/writing, the AI performer generates in real-time a prediction of what the drawing looks like.',
      // link: ''
    },
    {
      image: '/lator.png',
      title: 'Lator',
      description: 'Calculator + Oscillators. A simple calculator instrument that can be used to combine, modify, and play frequencies. This tool enables the user to work outside the confines of traditional scales, exploring acoustic beating effects and easily appling Pythagorean ratios. Built using p5.js with p5.sound.',
      link: 'https://lator-h5gfv8m5z-seiderslennons-projects.vercel.app/'
    },
    {
      image: '/project1.png',
      title: 'Electric Guitar Classification',
      description: 'Neural network classifier for determining the presence of electric guitar using a custom dataset of ~4000 Billboard Top 100 songs.',
      link: 'Electric Guitar Classification.pdf'
    },
    {
      image: '/finsta.png',
      title: 'Instagram Clone',
      description: 'Web application imitating the basic features of Instagram using client-side dynamic pages with a REST API.',
      link: 'http://ec2-3-145-178-247.us-east-2.compute.amazonaws.com/'
    },
    {
      image: '/project3.png',
      title: 'Preprocessing X-Ray Diffraction Images',
      description: 'Summer research project as an undergraduate researcher working under postdoctoral advisor Seunghee Oh at Professor Ashley Bucsek\'s materials science research lab.',
      link: 'https://github.com/seiderslennon/research_public'
    },
    {
      image: '/project2.png',
      title: 'Differentially Private SVM Learning',
      description: 'Final project for the course "Foundations of Fairness in Machine Learning". Partnered with another undergraduate, Meera Kumar, to design a post-processing algorithm for a differentially-private fair support vector machine classifier.',
      link: 'Differentially-Private Fair SVMs.pdf'
    },
    { 
      image: '/inanocean.png',
      title: 'Mix: "In an Ocean"',
      description: 'Mixing project for the song "In an Ocean", performed and recorded by musicians from University of Michigan School of Music, Theater and Dance.',
      audio: 'inanocean.wav'
    },
    { 
      image: '/percClassifier.png',
      title: 'Percussion Instrument Classifier',
      description: 'Simple random forest instrument classifier for three instruments: kick drum, snare drum, and hi-hat. Implemented using R\'s randomForest, tuneR and seewave libraries.',
      link: 'waveformanalysis.pdf'
    }
  ];
  
  // Toggle between portfolio and about view
  function toggleView() {
    showPortfolio = !showPortfolio;
  }
</script>

<svelte:head>
  <link href="https://fonts.googleapis.com/css2?family=League+Spartan:wght@100..900&family=Montserrat:ital,wght@0,100..900;1,100..900&family=Roboto+Mono:ital,wght@0,100..700;1,100..700&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap" rel="stylesheet">
</svelte:head>

<style>
  :global(body) {
    font-family: 'Roboto Mono', monospace;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4; 
    background: url('/graphy-copy2.png') repeat;
    background-size: 45px 90px;
    background-attachment: fixed; 
  }
  .header-container {
    text-align: left;
    padding: 10px 20px;
  }
  .header-content {
    max-width: 800px; 
    margin: 0 auto;
  }
  .main-title {
    font-family: 'Roboto Mono';
    font-size: 80px;
    font-weight: 600;
    letter-spacing: 1.5px;
    margin: 0;
    line-height: 1.2;
  }
  /* .main-name {
    font-family: 'Roboto';
    font-size: 28px;
    font-weight: 600;
    letter-spacing: 1.5px;
    margin: 0;
    line-height: 1.2;
    padding-left: 3.5px;
    color: rgb(181, 181, 181);
    cursor: pointer; 
  } */
  .main-name {
  font-family: 'Roboto';
  font-size: 24px;
  font-weight: 600;
  letter-spacing: 1.5px;
  margin: 0;
  line-height: 1.2;
  padding-left: 3.5px;
  color: Purple;
  text-decoration: underline;
  cursor: pointer;
  background: none;
  border: none;
  padding: 2px;
  margin-bottom: 10px;
}
  .bottom-right-text {
    position: static;  
    font-size: 0.85rem;
    text-align: right;
    padding-right: 5px;
    color: #333;      
  }
</style>

<!-- Header Section -->
<header id="home" class="header-container">
  <div class="header-content">
    <h1 class="main-title">Lennon Fairbanks Seiders</h1>
    <!-- Clicking the header toggles between views -->
    <button class="main-name" on:click={toggleView}>
      {showPortfolio ? 'Portfolio' : 'About'}
    </button>
  </div>
</header>

<!-- Conditional rendering of Portfolio or About Section -->
{#if showPortfolio}
  <section id="portfolio">
    {#each projects as project}
      <PortfolioItem 
        image={project.image} 
        title={project.title} 
        description={project.description} 
        link={project.link}
        audio={project.audio}
      />
    {/each}
  </section>
  <div class="bottom-right-text">
    coded + designed by Lennon Seiders
  </div>
{:else}
  <section id="about" style="max-width: 800px; margin: 0 auto;">
    <p>I am an undergraduate student at the University of Michigan, majoring in Computer Science and Data Science. I like building things and music.</p>
    <!-- <p><a href="https://github.com/seiderslennon" style="color: inherit; text-decoration: none; outline: none; -webkit-tap-highlight-color: transparent;">github.com/seiderslennon</a></p> -->
    <p><a href="https://www.linkedin.com/in/lennon-seiders/" style="color: inherit; text-decoration: none; outline: none; -webkit-tap-highlight-color: transparent;">linkedin.com/in/lennon-seiders</a></p>
    <p>seiderslennon@gmail.com</p>
  </section>
{/if}
