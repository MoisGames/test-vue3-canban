<template>
    <v-toolbar flat>
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
                            @click="sortList" 
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
                            @click="sortList" 
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
                            @click="sortList" 
                            />
                    </template>
        </v-tooltip>
      </v-toolbar>
</template>

<script>
//     export default {
//   components: {
//     PanelSort
//   }
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