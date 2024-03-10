<template>
  <div class="">

    <app-header></app-header>

<!--    <div class="app-container">-->
<!--      <div style="width: 100%; height: 1300px;background: burlywood;margin-top: 400px">s</div>-->
<!--    </div>-->

    <div class="app-container" style="margin-top: 70px">
      <about-us></about-us>

      <categories @change="changeCategory"></categories>
      <div class="app-flex-grid">
        <div v-for="val in result" class="app-flex-grid-item">
          <product-item :item="val" :key="val.id"></product-item>
        </div>
      </div>

      <app-footer></app-footer>



    </div>


<!--    <script type="text/javascript" charset="utf-8" async src="https://api-maps.yandex.ru/services/constructor/1.0/js/?um=constructor%3Aa99a36ff077be4121d489bfcc6ab84a387965a8e8dd101d33d9db00eec5bd2e5&amp;width=921&amp;height=400&amp;lang=ru_RU&amp;scroll=true"></script>-->


  </div>
</template>

<script lang="ts">
import {ref} from "#imports";

export default {
  setup () {

    let items = ref<Array<any>>([]);
    const category = ref<any>(null)

    fetch('/products.json')
        .then((response) => {

          console.log(response)
          return response.json()
        })
        .then((data) => {

          items.value = data
          console.log(data)

          return 34567
        })
        .then((data) => {
          console.log(data)
        })
        .catch()
        .finally()

    let result = computed(() => {
      let result = items.value.filter(function (value, index, array) {
        if (!category.value) {
          return true
        }

        return value.category.id === category.value.id
      })

      return result;
    })

    const changeCategory = (cat: any) => {
      category.value = cat
    }

    return {
      items,
      result,
      changeCategory,
    }
  }
}

</script>

<style >
html, body {
  margin: 0;
  padding: 0;
}
* {
  box-sizing: border-box;
}
.app-container {
  padding: 0 15px;
}
.app-flex-grid {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-flow: row wrap;

}
.app-flex-grid-item {
  width: 100%;
  max-width: 25%;
}
@media only screen and (max-width: 1000px) {
  .app-flex-grid-item {
    max-width: 33.333333%;
  }
}
@media only screen and (max-width: 680px) {
  .app-flex-grid-item {
    max-width: 50%;
  }
}
@media only screen and (max-width: 480px) {
  .app-flex-grid-item {
    max-width: 100%;
  }
}

</style>