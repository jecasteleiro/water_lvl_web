<script>
import {
    Line
} from 'vue-chartjs';
import {
    mapState
} from 'vuex'

export default {
    extends: Line,
    data() {
        return {
            chartData: {
                labels: ['24h', '23h', '22h', '21h', '20h', '19h', '18h', '17h', '16h', '15h', '14h',
                    '13h', '12h', '11h', '10h', '9h', '8h', '7h', '6h', '5h', '4h', '3h', '2h', '1h'
                ],
                datasets: [{
                        label: "Rudy's Tank",
                        backgroundColor: "#0277BD",
                        data: [40, 20, 23, 45, 33, 2, 1, 2, 3, 44, 3, 3, 2, 21, 23, 12, 23, 79, 65, 66, 7, 8, 65, 45],
                        fill: false,
                        borderColor: "#0277BD",
                        borderWidth: 2
                    },
                    {
                        label: "Raquel's Tank",
                        backgroundColor: '#F06292',
                        data: [12, 23, 45, 65, 67, 89, 43, 54, 10, 9, 6, 7, 43, 24, 67, 22, 32, 21, 67, 8, 99, 5, 77, 32],
                        fill: false,
                        borderColor: '#F06292',
                        borderWidth: 2
                    }
                ]
            },
            options: {
                scales: {
                    yAxes: [{
                        ticks: {
                            beginAtZero: true
                        },
                        gridLines: {
                            display: true
                        }
                    }],
                    xAxes: [{
                        gridLines: {
                            display: false
                        }
                    }]
                },
                legend: {
                    display: true
                },
                responsive: true,
                maintainAspectRatio: false
            }
        }
    },
    computed: {
        ...mapState
    },
    mounted() {
        this.renderChart(this.chartData, this.options)
    }
}
</script>

<style>
.small {
    max-width: 300px;
    max-height: 200px;
}
</style>
