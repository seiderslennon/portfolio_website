<script>
    export let image;
    export let title;
    export let description;
    export let link;     // The URL to navigate to
    export let audio;    // The optional .wav file URL
    export let year;     // The year for the project
  </script>
  
  <style>
    .portfolio-link {
      display: block;
      margin: 0 0 20px 0;
      text-decoration: none;
      color: inherit;
      break-inside: avoid;
    }

    .portfolio-item {
      /* keep the styles for hover, background, padding, etc. */
      background-color: rgba(255, 255, 255, 0.374);
      padding: 20px;
      border-radius: 5px;
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
      border-radius: 2px;
    }
  
    .portfolio-item h2 {
      margin: 20px 0 5px 0;
      font-size: 1.4rem;
      color: #2c3e50;
      font-family: 'Roboto Mono';
      font-weight: 450;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
  
    .portfolio-item p {
      margin: 0;
      font-size: 1.1rem;
      color: #7f8c8d;
      font-family: 'Roboto';
    }

    .portfolio-item audio {
      margin-top: 15px;
      width: 100%;
    }
  
    @media (max-width: 768px) {
      .portfolio-item h2 {
        font-size: 1.5rem;
      }
  
      .portfolio-item p {
        font-size: 0.9rem;
      }

      .portfolio-link {
        margin: 0 0 15px 0;
      }
    }
  </style>
  
  <!-- Wrap the entire item in an anchor tag -->
  <a class="portfolio-link" href={link} target="_blank" rel="noopener noreferrer">
    <div class="portfolio-item">
      <img src={image} alt={title} />
      <h2>
        <span>{title}</span>
        {#if year}
          <span class="year">{year}</span>
        {/if}
      </h2>
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
  