<template>
<v-container grid-list-lg>
    <v-layout>
        <v-row align="center" justify="center">
            <v-flex xs10 md5>
                <v-card shrink>
                    <v-card-title>Network Credentials</v-card-title>
                    <v-card-text>
                        <v-form v-model="valid">
                            <v-row>
                                <v-col>
                                    <v-text-field v-model="ssid" :rules="namerules" label="WiFi SSID"></v-text-field>
                                    <v-text-field v-model="password" :rules="namerules" label="Password"></v-text-field>
                                    <v-text-field v-model="staticIP" :rules="namerules" label="Static IP"></v-text-field>
                                    <v-text-field v-model="gateway" :rules="namerules" label="Gateway"></v-text-field>
                                    <v-text-field v-model="subnet" :rules="namerules" label="Subnet"></v-text-field>
                                </v-col>
                            </v-row>
                        </v-form>
                    </v-card-text>
                </v-card>
            </v-flex>
            <v-flex xs10 md5>
                <v-card shrink>
                    <v-card-title>Tanks Parameters</v-card-title>
                    <v-card-text>
                        <v-form v-model="valid">
                            <v-row>
                                <v-col>
                                    <v-text-field v-model="rudys_min_distance" :rules="namerules" label="Min Distance(cm) in Rudy's Tank"></v-text-field>
                                    <v-text-field v-model="rudys_max_distance" :rules="namerules" label="Max Distance(cm) in Rudy's Tank"></v-text-field>
                                    <v-text-field v-model="raquels_min_distance" :rules="namerules" label="Min Distance(cm) in Raquel's Tank"></v-text-field>
                                    <v-text-field v-model="raquels_max_distance" :rules="namerules" label="Max Distance(cm) in Raquel's Tank"></v-text-field>
                                </v-col>
                            </v-row>
                        </v-form>
                    </v-card-text>
                </v-card>
            </v-flex>
        </v-row>
    </v-layout>

</v-container>
</template>
