<template>
<v-container grid-list-lg>
    <v-layout>
        <v-row align="center" justify="center">
            <v-flex xs6 md4>
                <v-card shaped>
                    <h4 class="text-center">Rudy's Tank</h4>
                    <v-row justify="center">
                        <v-progress-circular :rotate="-90" :size="100" :width="15" :value="real_RudysTankLvl" :color="color_rudys_meter">
                            {{real_RudysTankLvl}}%
                        </v-progress-circular>
                    </v-row>
                </v-card>
            </v-flex>
            <v-flex xs6 md4>
                <v-card shaped>
                    <h4 class="text-center">Raquel's Tank</h4>
                    <v-row align="center" justify="center">
                        <v-progress-circular :rotate="-90" :size="100" :width="15" :value="real_RaquelsTankLvl" :color="color_raquels_meter">
                            {{real_RaquelsTankLvl}}%
                        </v-progress-circular>
                    </v-row>
                </v-card>
            </v-flex>
        </v-row>
    </v-layout>
    <v-divider></v-divider>
    <v-layout fluid>
        <v-flex xs12 md12>
            <v-card raised>
                <h4 class="text-center">Last 24h</h4>
                <div>
                    <line-chart></line-chart>
                </div>
            </v-card>
        </v-flex>
    </v-layout>
</v-container>
</template>

<script>
//colores verde "#00E676", naranja "#F9A825", rojo "#C62828"

// @ is an alias to /src
import LineChart from '@/components/Chart.vue';
import {
    mapState
} from 'vuex';

export default {
    name: 'dashboard',
    components: {
        LineChart
    },
    computed: {
        ...mapState(['real_RudysTankLvl', 'real_RaquelsTankLvl']),
        color_rudys_meter() {
            if (this.real_RudysTankLvl <= 30) {
                return "#C62828";
            }
            if (this.real_RudysTankLvl > 30 && this.real_RudysTankLvl < 60) {
                return "#F9A825";
            }
            return "#00E676";
        },
        color_raquels_meter() {
            if (this.real_RaquelsTankLvl <= 30) {
                return "#C62828";
            }
            if (this.real_RaquelsTankLvl > 30 && this.real_RaquelsTankLvl < 60) {
                return "#F9A825";
            }
            return "#00E676";
        }
    }
}
</script>
