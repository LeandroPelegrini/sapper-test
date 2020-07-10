<script>
  import { posts } from "../posts.js";
  
  let darkmode;
  const d = new Date("2010-08-05");
  var monthNames = [
    "Janeiro",
    "Fevereiro",
    "Março",
    "Abril",
    "Maio",
    "Junho",
    "Julho",
    "Augosto",
    "Septembro",
    "Outubro",
    "Novembro",
    "Decembro",
  ];
  var dayNames = [
    "Domingo",
    "Segunda-feira",
    "Terça-feira",
    "Quarta-feira",
    "Quinta-feira",
    "Sexta-feira",
    "Sábado",
  ];
  var date = new Date();
  var day = date.getDate();
  var month = monthNames[date.getMonth()];
  var weekday = dayNames[date.getDay()];
  var year = date.getFullYear();
</script>

<style>
  *,
  *:after,
  *:before {
    box-sizing: border-box;
  }

  a {
    color: var(--primary-color);
    text-decoration: none;
    -webkit-transition: var(--transition-animation);
    transition: var(--transition-animation);
  }
  a:hover,
  a:visited,
  a:focus {
    color: var(--primary-color);
  }

  p {
    margin-top: 0;
    margin-bottom: 20px;
    text-align: justify;
    text-justify: inter-word;
  }


  /**************************************
    Header of Paper
**************************************/
  header {
    text-align: center;
    position: relative;
  }
  header h1.news_paper_title {
    margin: 0;
  }
  header h1.news_paper_title a {
    font-family: "Playfair Display", serif;
    font-weight: 900;
    font-size: 60px;
    text-transform: uppercase;
    display: inline-block;
    line-height: 60px;
    margin: 15px 0;
    cursor: pointer;
    color: var(--primary-color);
    -webkit-transition: var(--transition-animation);
    transition: var(--transition-animation);
  }
  header h1.news_paper_title a:hover {
    color: var(--secondary-color);
  }
  header .news_paper_location {
    font-weight: 600;
    border-bottom: 1px solid var(--primary-color);
    border-top: 1px solid var(--primary-color);
    padding: 10px 0 10px 0;
    margin: 20px 0;
  }

  .news_paper_title::before {
    content: "";
    color: red;
    width: 200px;
    height: 200px;
  }

  @media only all and (max-width: 600px) {
    header h1.news_paper_title a {
      font-size: 40px;
      line-height: 40px;
      margin: 5px 0;
    }
  }
  /**************************************
    Content Area of Newspaper
**************************************/
  .headline {
    text-align: center;
    line-height: normal;
    font-family: "Playfair Display", serif;
    display: block;
    margin: 0 auto;
  }
  .headline h2.title {
    font-weight: 400;
    font-style: italic;
    font-size: 22px;
  }
  .headline h2.title:hover {
    color: var(--secondary-color);
  }
  .headline h3.writer {
    font-weight: 700;
    font-size: 12px;
  }
  .headline h3.writer:hover {
    color: var(--secondary-color);
  }
  .headline h3.writer:before {
    border-top: 1px solid var(--primary-color);
    content: "";
    width: 100px;
    height: 7px;
    display: block;
    margin: 0 auto;
  }
  .headline h3.writer:after {
    border-bottom: 1px solid var(--primary-color);
    content: "";
    width: 100px;
    height: 10px;
    display: block;
    margin: 0 auto;
  }

  .button a {
    display: inline-block;
    background: transparent;
    border: 1px solid var(--primary-color);
    color: var(--primary-color);
    font-size: 16px;
    padding: 10px 15px;
  }
  .button a:hover,
  .button a:focus,
  .button a:active {
    background: var(--green-color);
    border: 1px solid var(--green-color);
    color: var(--white-color);
  }

  /**************************************
    Images & iframes
**************************************/
  figure {
    cursor: pointer;
    margin: 0 0 20px;
    -webkit-filter: grayscale(100%);
    filter: grayscale(100%);
    -webkit-transition: var(--transition-animation);
    transition: var(--transition-animation);
  }
  figure img {
    max-width: 100%;
    height: auto;
  }
  figure figcaption {
    font-style: italic;
    font-size: 12px;
    text-align: left;
    -webkit-transition: var(--transition-animation);
    transition: var(--transition-animation);
  }
  figure figcaption:hover {
    padding-left: 10px;
  }
  figure:hover {
    -webkit-filter: grayscale(0);
    filter: grayscale(0);
  }

  /***************************************************
    Responsive Framework
    https://codepen.io/HikwaMehluli/full/qeNOVv
***************************************************/
  .the-grid-section {
    max-width: 1500px;
    margin: 0 auto;
    width: 100%;
  }
  .the-grid-section .the-grid {
    margin-bottom: 40px;
    -webkit-transition: all 0.5s;
    transition: all 0.5s;
  }
  .the-grid-section .the-grid .the-grid-content p {
    display: -webkit-box;
    -webkit-line-clamp: 5;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }
  /* the flexbox magic */
  @media screen and (min-width: 768px) {
    .the-grid-section {
      display: -webkit-box;
      display: flex;
      flex-wrap: wrap;
      -webkit-box-pack: justify;
      justify-content: space-between;
    }

    .the-grid {
      display: -webkit-box;
      display: flex;
      -webkit-box-flex: 0;
      flex: 0 1 calc(50% - 0.5em);
    }
  }
  @media screen and (min-width: 1000px) {
    .the-grid {
      -webkit-box-flex: 0;
      flex: 0 1 calc(45% - 1em);
    }
  }
  @media screen and (min-width: 1500px) {
    .the-grid {
      -webkit-box-flex: 0;
      flex: 0 1 calc(40% - 1em);
    }
  }

/* Toggle switch styling */
.dark_mode_container {
  display: -webkit-box;
  display: flex;
  position: relative;
  -webkit-box-align: center;
          align-items: center;
}
.dark_mode_container .dark_mode_switch {
  display: inline-block;
  height: 20px;
  width: 60px;
  max-width: 60px;
}
.dark_mode_container .dark_mode_switch input {
  display: none;
}
.dark_mode_container .dark_mode_switch input:checked + .slider {
  background-color: var(--green-color);
}
.dark_mode_container .dark_mode_switch input:checked + .slider:before {
  -webkit-transform: translateX(25px);
          transform: translateX(25px);
}

.slider {
  background-color: #ccc;
  bottom: 0;
  cursor: pointer;
  position: absolute;
  right: 0;
  top: 0;
  -webkit-transition: var(--transition-animation);
  transition: var(--transition-animation);
  width: 44px;
}
.slider:before {
  background-color: var(--white-color);
  bottom: 5px;
  content: "";
  height: 10px;
  left: 5px;
  position: absolute;
  -webkit-transition: var(--transition-animation);
  transition: var(--transition-animation);
  width: 10px;
}
.slider.round {
  border-radius: 34px;
}
.slider.round:before {
  border-radius: 50%;
}
</style>

<svelte:head>
  <title>Sapper project template</title>
</svelte:head>

<header>
  <h1 class="news_paper_title">
    <a href="/">Gabriela Antunes</a>
  </h1>

<!--   <div class="dark_mode_container">
		<label class="dark_mode_switch" for="checkbox">
			<input type="checkbox" id="checkbox" bind:checked={darkmode}/>
			<div class="slider round"></div>
		</label>
	</div> -->

  <div class="news_paper_location">
    Portfólio Com Minhas Publicações -
    <span id="time">{weekday} - {day} de {month} {year}</span>
  </div>
</header>

<section class="the-grid-section">
  {#each posts as post}
    <article class="the-grid">
      <div class="the-grid-content">
        <div class="headline">
          <a href={`/posts/${post.permalink}`}>
            <h2 class="title">{post.title}</h2>
            <h3 class="writer">
              Data: {post.date.getDay()}-{post.date.getMonth()}-{post.date.getFullYear()}
            </h3>
            <figure>
              <img src={post.hero} alt="Image {post.title}" />
              <figcaption>
                <a href={post.hero}>Image Source: {post.source}</a>
              </figcaption>
            </figure>
          </a>
        </div>
        <p>{post.summary}</p>
        <div class="button">
          <a href={`/posts/${post.permalink}`}>Leia Mais</a>
        </div>
      </div>
    </article>
  {/each}
  <span />
</section>
