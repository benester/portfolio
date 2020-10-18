<script>
  import { modelStore } from "../store.js";

  let isMobile;
  if (isMobile === undefined)
    modelStore.subscribe(model => {
      isMobile = model.getIsMobile();
    });
</script>

<style>
  footer {
    position: absolute;
    bottom: 0;
    width: 100%;
    background-color: rgb(60, 19, 96);
    right: 0;
    color: white;
    z-index: 101;
  }
  a {
    text-decoration: none;
  }
  h3 {
    color: rgb(194, 163, 209);
  }
  #Wrapper {
    width: 100%;
    display: flex;
    padding-top: 10px;
    flex-direction: row;
    justify-content: center;
  }
  #column1,
  #column2,
  #column3, .mobilCol {
    display: flex;
    flex-direction: column;
  }
  .mobilCol{
      align-items: center;
  }

  #column1 {
    margin-right: 5%;
  }
  #column2 {
    margin-right: 5%;
  }
  #column3 {
    margin-left: 10%;
  }
  #copyRight {
    width: 100%;
    text-align: center;
    color: rgb(194, 163, 209);
  }
  figure,
  img {
    left: 0;
    margin: 0;
  }
  figure {
    margin: 0px 5px;
  }
  #imgSpace {
    margin-left: 8px;
  }
  p {
    margin: 5px;
  }
  #mobileWrap {
    width: 100%;
    padding-top: 10px;
  }
</style>

{#if !isMobile}
  <footer>
    <div id="Wrapper">
      <div id="column1">
        <h3>
          <b>Produkt</b>
        </h3>
        <a href=".">Platformen</a>
        <!--- TODO ADD LINKS-->
        <a href=".">Boka demo</a>
        <a href=".">Ladda upp</a>
        <a href="terms">Användarvilkor</a>
        <a href="privacy">Integritetspolicy</a>
        <a href="cookies">Cookie policy</a>
      </div>
      <div id="column2">
        <h3>
          <b>Sekando</b>
        </h3>
        <a href="omoss">Om oss</a>
        <!--- TODO ADD LINKS-->
        <a href="career">Jobba här</a>
        <a href=".">FAQ</a>
      </div>
      <div id="column3">
        <h3>
          <b>Kontakta oss</b>
        </h3>
        <p>
          +46 761 66 82 52
          <br />
          <a href="mailto:info@sekando.se">info@sekando.se</a>
        </p>
        <figure>
          <img src="sekandologolitenvit.webp" alt="Sekando logotyp" />
        </figure>
        <figure>
          <a href="https://www.linkedin.com/company/sekando-ab/">
            <img src="linkedin.webp" alt="LinkedIn logotyp" />
          </a>
          <a href="https://www.instagram.com/sekando.se">
            <img id="imgSpace" src="instagram.webp" alt="Instagram logotyp" />
          </a>
        </figure>
        <p>Org: 559250-3741</p>
      </div>
    </div>
    <div id="copyRight">
      <p>© 2020 by Sekando AB</p>
    </div>
  </footer>
{:else}
  <!-------------------     For mobile phones        ------------>
  <footer>
    <div id="mobileWrap">
      <div class="mobilCol">
        <h3>
          <b>Produkt</b>
        </h3>
        <a href=".">Platformen</a>
        <!--- TODO ADD LINKS-->
        <a href=".">Boka demo</a>
        <a href=".">Ladda upp</a>
        <a href="terms">Användarvilkor</a>
        <a href="privacy">Integritetspolicy</a>
        <a href="cookies">Cookie policy</a>
        <br />
      </div>
      <div class="mobilCol">
        <h3>
          <b>Sekando</b>
        </h3>
        <a href="omoss">Om oss</a>
        <!--- TODO ADD LINKS-->
        <a href="career">Jobba här</a>
        <a href=".">FAQ</a>
        <br />
      </div>
      <div class="mobilCol">
        <h3>
          <b>Kontakta oss</b>
        </h3>
        <p>
          +46 761 66 82 52
          <br />
          <a href="mailto:info@sekando.se">info@sekando.se</a>
        </p>
        <figure>
          <img src="sekandologolitenvit.webp" alt="Sekando logotyp" />
        </figure>
        <figure>
          <a href="https://www.linkedin.com/company/sekando-ab/">
            <img src="linkedin.webp" alt="LinkedIn logotyp" />
          </a>
          <a href="https://www.instagram.com/sekando.se">
            <img id="imgSpace" src="instagram.webp" alt="Instagram logotyp" />
          </a>
        </figure>
        <p>Org: 559250-3741</p>
      </div>
    </div>
    <div id="copyRight">
      <p>© 2020 by Sekando AB</p>
    </div>
  </footer>
{/if}