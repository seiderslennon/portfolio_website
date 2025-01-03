<script>
    import PortfolioItem from '$lib/components/PortfolioItem.svelte';
    
  
    const projects = [
      {
        image: '/project1.png',
        title: 'Electric Guitar Classification in Popular Music Recordings',
        description: 'Training a neural network classifier to determine the presence of electric guitar on a dataset of ~4000 Billboard Hot 100 songs.',
        link: 'Electric Guitar Classification.pdf'
      },
      {
        image: '/project2.png',
        title: 'Differentially Private SVM Learning',
        description: 'Final project for the course "Foundations of Fairness in Machine Learning". Parternered with another undergraduate, Meera Kumar, to design a post-processing algorithm for a differentially-private fair support vector machine classifier, and make formal guarantees for its violation of fairness and error upper bound.',
        link: 'Differentially-Private Fair SVMs.pdf'
      },
      {
        image: '/project3.png',
        title: 'Peak Removal in X-Ray Diffraction Images',
        description: 'Summer research project as an undergraduate researcher working under postdoctoral advisor Seunghee Oh at Professor Ashley Bucsek\'s materials science research lab.',
        link: 'X-ray_Diffraction.pdf'
      },
      { /*In an Ocean*/
        image: '/inanocean.png',
        title: 'Mix: "In an Ocean"',
        description: 'Mixing project for the song "In an Ocean", performed and recorded by musicians from University of Michigan School of Music, Theater and Dance.',
        link: '',
        audio: 'inanocean.wav'
      },
      { /*Percussion Classifier*/
        image: '/percClassifier.png',
        title: 'Percussion Instrument Classifier',
        description: 'Random forest instrument classifier for three instruments: kick drum, snare drum, and hi-hat.',
        link: 'waveformanalysis.pdf'
      }
    //   { /*Aplifier*/
    //     image: '',
    //     title: '',
    //     description: '',
    //     link: ''
    //   }
    ];
  </script>
  
  <style>
    .header-container {
      padding: 3rem 2rem;
      background-color: #f8f9fa;
      text-align: center;
      margin-bottom: 2rem;
    }
    
    .header-content {
      max-width: 1200px;
      margin: 0 auto;
    }
    
    .main-title {
      font-size: 2.5rem;
      margin-bottom: 1rem;
      color: #333;
    }
    </style>
  
  <!-- Header Section -->
  <header id="home" class="header-container">
    <div class="header-content">
      <h1 class="main-title">Application Portfolio - Lennon Seiders</h1>
    </div>
  </header>
  
  <!-- Portfolio Sections -->
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
  