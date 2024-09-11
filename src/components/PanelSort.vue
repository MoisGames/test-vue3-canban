<template >
    <v-toolbar flat ref="cardItemRef">
        <v-toolbar-title class="text-black" >
          Сортировать рейтинг по:
        </v-toolbar-title>
        
        <v-tooltip text="Сортировка по убыванию">
                    <template v-slot:activator="{ props }">
                        <v-btn
                            v-bind="props"
                            icon="mdi-sort"
                            density="compact"
                            variant="tonal"
                            class="sort-btn"
                            color="blue"
                            @click="sortRatingDown" 
                            />
                    </template>
        </v-tooltip>
        
        <v-tooltip text="Сортировка по возрастанию">
                    <template v-slot:activator="{ props }">
                        <v-btn
                            v-bind="props"
                            icon="mdi-sort"
                            density="compact"
                            variant="tonal"
                            class="sort-btn"
                            color="blue"
                            @click="sortRatingUp" 
                            />
                    </template>
        </v-tooltip>
        
        <v-tooltip text="Без сортировки">
                    <template v-slot:activator="{ props }">
                        <v-btn
                            v-bind="props"
                            icon="mdi-sort"
                            density="compact"
                            variant="tonal"
                            class="sort-btn"
                            color="blue"
                            @click="sortRatingRand" 
                            />
                    </template>
        </v-tooltip>
      </v-toolbar>
</template>

<script setup>
import { inject, ref} from 'vue';


const firstList = inject('firstList');
const secondList = inject('secondList');
const lastList = inject('lastList');

const props = defineProps({
    options: {},
  });

let cards = ref([])

cards = firstList.value

function sortRatingDown() {
    firstList.value.sort((a,b) => b.rating.rate - a.rating.rate);
    secondList.value.sort((a,b) => b.rating.rate - a.rating.rate);
    lastList.value.sort((a,b) => b.rating.rate - a.rating.rate);
}
function sortRatingUp() {
    firstList.value.sort((a,b) => a.rating.rate - b.rating.rate);
    secondList.value.sort((a,b) => a.rating.rate - b.rating.rate);
    lastList.value.sort((a,b) => a.rating.rate - b.rating.rate);
}
function sortRatingRand() {
    firstList.value.rand();
    secondList.value.rand();
    lastList.value.rand();
}
console.log(firstList.value, "firstList из PanelSort v.2");


// const sortListRatingDown = inject('sortListRatingDown')
// const sortListRatingUp = inject('sortListRatingUp')
// const sortListRatingDefault = inject('sortListRatingDefault')

// function test() {
//     sortListRatingDown()
// }
  
</script>

<style lang="scss" scoped>
@forward 'vuetify/settings';

.v-toolbar {
    border-radius: 10px;
}
.v-toolbar-title {
    font-size: 18px;
}
.v-btn {
    margin: 10px;
}
</style>