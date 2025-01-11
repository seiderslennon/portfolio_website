<script>
    export let image;
    export let title;
    export let description;
    export let link;     // The URL to navigate to
    export let audio;    // The optional .wav file URL
  </script>
  
  <style>
    .portfolio-link {
      display: block;
      max-width: 800px;
      margin: 0 auto 40px;
      text-decoration: none;
      color: inherit;
    }

    .portfolio-item {
      /* keep the styles for hover, background, padding, etc. */
      background-color: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }
  
    .portfolio-item:hover {
      transform: translateY(-2px);
      box-shadow: 0 10px 5px rgba(48, 25, 25, 0.2);
      cursor: pointer;
    }
  
    .portfolio-item img {
      width: 100%;
      height: auto;
      border-radius: 8px;
    }
  
    .portfolio-item h2 {
      margin-top: 20px;
      font-size: 1.9rem;
      color: #2c3e50;
      font-family: 'Roboto Mono';
      font-weight: 450;
    }
  
    .portfolio-item p {
      margin-top: 10px;
      font-size: 1.1rem;
      color: #7f8c8d;
      font-family: 'Roboto';
    }
  
    @media (max-width: 768px) {
      .portfolio-item h2 {
        font-size: 1.5rem;
      }
  
      .portfolio-item p {
        font-size: 0.9rem;
      }
    }
  </style>
  
  <!-- Wrap the entire item in an anchor tag -->
  <a class="portfolio-link" href={link} target="_blank" rel="noopener noreferrer">
    <div class="portfolio-item">
      <img src={image} alt={title} />
      <h2>{title}</h2>
      <p>{description}</p>
  
      {#if audio}
        <!-- Only render audio if we have an audio prop -->
        <audio controls>
          <source src={audio} type="audio/wav" />
          Your browser does not support the audio element.
        </audio>
      {/if}
    </div>
  </a>
  