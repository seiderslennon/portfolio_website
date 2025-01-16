<script>
    import PortfolioItem from '$lib/components/PortfolioItem.svelte';
    
  
    const projects = [
      {
        image: '/project1.png',
        title: 'Electric Guitar Classification',
        description: 'Neural network classifier for determining the presence of electric guitar usinga custom dataset of ~4000 Billboard Top 100 songs.',
        link: 'Electric Guitar Classification.pdf'
      },
      {
        image: '/project3.png',
        title: 'Preprocessing X-Ray Diffraction Images',
        description: 'Summer research project as an undergraduate researcher working under postdoctoral advisor Seunghee Oh at Professor Ashley Bucsek\'s materials science research lab.',
        link: 'https://github.com/seiderslennon/research_public'
      },
      { /*In an Ocean*/
        image: '/inanocean.png',
        title: 'Mix: "In an Ocean"',
        description: 'Mixing project for the song "In an Ocean", performed and recorded by musicians from University of Michigan School of Music, Theater and Dance.',
        // link: '',
        audio: 'inanocean.wav'
      },
      {
        image: '/project2.png',
        title: 'Differentially Private SVM Learning',
        description: 'Final project for the course "Foundations of Fairness in Machine Learning". Parternered with another undergraduate, Meera Kumar, to design a post-processing algorithm for a differentially-private fair support vector machine classifier, and make formal guarantees for its violation of fairness and error upper bound. Both Meera and I are responsible for each part of this project, although my work prioritized the algorithm while hers prioritized fairnes violation measurement',
        link: 'Differentially-Private Fair SVMs.pdf'
      },
      { /*Percussion Classifier*/
        image: '/percClassifier.png',
        title: 'Percussion Instrument Classifier',
        description: 'Simple random forest instrument classifier for three instruments: kick drum, snare drum, and hi-hat. Implemented using R\'s randomForest, tuneR and seewave libraries.',
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
  
  <svelte:head>
    <!-- <link
      href="https://fonts.googleapis.com/css2?family=League+Spartan:wght@100..900&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap" 
      rel="stylesheet"
    /> -->
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
      /* background: #050a44f1;
      color: #ffffffff; */
      text-align: left;
      padding: 60px 20px;
      
      /* box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1); */
      /* margin-bottom: 20px; */
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
  
      /* color: 0 2px 5px rgb(255, 255, 255); */
      /* text-shadow: 0 2px 5px rgba(0, 0, 0, 0.3); */
    }

    .main-name {
      font-family: 'Roboto';
      font-size: 28px;
      font-weight: 600;
      letter-spacing: 1.5px;
      margin: 0;
      line-height: 1.2;
      padding-left: 3.5px;
      color:rgb(181, 181, 181);
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
      <h2 class="main-name"> Portfolio</h2>
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

  <div class="bottom-right-text">
    coded + designed by Lennon Seiders
  </div>
  