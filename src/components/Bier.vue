<template>
    <div class="bier">
      <div class="bier__name">
        <h4>{{bierTitel}}</h4>
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
    bierBrauerei: String
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
    align-items: flex-end;
    background: var(--black-default);
    padding: 1rem 2rem;
  }

  .bier__name h4 {
    color: var(--white);
    text-align: right;
  }

  .bier__info {
    display: flex;
    flex-direction: column;
    padding: 1rem 2rem;
    background: var(--yellow-tint-60);
  }





</style>