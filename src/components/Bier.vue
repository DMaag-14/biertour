<template>
    <div class="bier">
      <div class="bier__name">
        <h4>{{bierTitel}}</h4>
        <span class="detail">
          <div class="square"></div>
          <span class="number">{{bierNummer}}</span>
        </span>
      </div>
      <div class="bier__info">
        <div class="bier__info__item">
          <span>Brauerei</span><span class="bier__info__item__right">{{bierBrauerei}}</span>
        </div>
        <div class="bier__info__item">
          <span>Alk.</span><span class="bier__info__item__right">{{bierAlkohol}}</span>
        </div>
        <div class="bier__info__item">
          <span>Herkunft</span><span class="bier__info__item__right">{{bierHerkunft}}</span>
        </div>
        <div class="bier__info__item">
          <span>Art</span><span class="bier__info__item__right">{{bierArt}}</span>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: "Bier",
  props: {
    bierTitel: String,
    bierAlkohol: String,
    bierHerkunft: String,
    bierArt: String,
    bierBrauerei: String,
    bierNummer: String
  }
};

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<!-- <style scoped lang="scss"> !-->
<style scoped >
  .bier {
    display: flex;
    flex-direction: column;
  }

  .bier__name {
    display: flex;
    justify-content: flex-end;
    background: var(--black-default);
    padding: 1rem 2rem;
    border-right: 4px solid var(--yellow-default);
    position: relative;
  }

  .bier__name .detail {
    position: absolute;
    top: -30%;
    left: 5%;
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 1fr;
    grid-template-areas: "overlap";
  }

  .bier__name .number {
    font-family: 'DM Serif Display', serif;
    font-size: 1.618rem;
    color: var(--black-default);
    grid-area: overlap;
    justify-self: center;
    align-self: center;
    z-index: 10;
  }

   .bier__name .square {
    height: 40px;
    width: 40px;
    background: var(--yellow-default);
    transform: rotate(45deg);
    grid-area: overlap;
    justify-self: center;
    align-self: center;
  }

  .bier__name h4 {
    color: var(--white);
    text-align: right;
    margin: 0;
  }

  .bier__info {
    display: flex;
    flex-direction: column;
    padding: 1rem 2rem;
    background: var(--yellow-tint-60);
  }

  .bier__info__item {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    color: var(--black-default);
    margin-bottom: .5rem;
  }

  .bier__info__item:last-of-type {
    margin-bottom: 0rem;
  }

  .bier__info__item span:first-child {
    margin-right: 1rem;
  }

  .bier__info__item__right {
    text-align: right;
  }
</style>