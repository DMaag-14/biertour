<template>
  <div class="background">
    <div class="container">
      <div class="impressum">
          <h3 class="impressum__title">Impressum</h3>
          <section class="quellen">
              <h4>Quellen</h4>
              <p>Die Texte stammen von <a href="https://www.bern.com/de/bier/bier-bars" class="inline-link" target="_blank">https://www.bern.com/de/bier/bier-bars</a> und den jeweiligen Seiten der Lokale:</p>
              <ul>
                  <li><a href="https://www.autrappiste.ch" class="quellen__links" target="_blank">Au Trappiste</a></li>
                  <li><a href="https://www.dietaube.ch" class="quellen__links" target="_blank">Die Taube</a></li>
                  <li><a href="http://www.ontapbern.ch" class="quellen__links" target="_blank">OnTap Bern</a></li>
                  <li><a href="https://www.kronebern.ch/bar/" class="quellen__links" target="_blank">Krone Bar</a></li>
                  <li><a href="https://www.cafemarta.ch" class="quellen__links" target="_blank">Café-Bar Marta</a></li>
                  <li><a href="https://www.oldcity.ch" class="quellen__links" target="_blank">The Old City Irish Pub</a></li>
              </ul>
              <p>Die Bilder stammen von <a href="https://baerner-meitschi.ch" class="inline-link" target="_blank">https://baerner-meitschi.ch</a>, <a href="https://unsplash.com" class="inline-link" target="_blank">https://unsplash.com</a>, <a href="https://www.google.com" class="inline-link" target="_blank">https://www.google.com</a>, <a href="https://www.bern.com/de/berner-biervielfalt" class="inline-link" target="_blank">https://www.bern.com/de/berner-biervielfalt</a> oder von Jeannine Kämpfer, Joel Lüthi und Dominik Maag. </p>
          </section>
          <section class="autoren">
              <h4>Autoren</h4>
              <p><strong>Dominik Maag</strong>, Konzept, Back-End Entwickler</p>
              <p><strong>Joel Lüthi</strong>, Konzept, Webdesign und Front-End Entwickler</p>
              <p><strong>Jeannine Kämpfer</strong>, Konzept, Webdesign, Front-End Entwicklerin</p>
              <p>© 2020, HSLUjooo</p>
          </section>

      </div>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style>
.background {
    background-color: var(--black-background);
    height: 100vh;
}

.impressum {
    color: var(--white);
    padding-top: 4rem;
    max-width: 50%;
}

.impressum h3 {
    margin-bottom: 1rem;
}

.impressum h4 {
    margin: 0;
}

.impressum a {
    text-decoration: none;
    color: var(--yellow-tint-60);
}

.quellen, .autoren {
    padding: 1rem 0rem;
}

.quellen ul{
    padding-left: .5rem;
}

.quellen ul li {
    list-style-type: none;
}

.quellen ul li::before {
    content: "—";
    margin-right: .5rem;
}

.autoren p {
    margin: .5rem 0rem;
}

.autoren p:last-of-type {
    margin-top: 2rem;
}

</style>