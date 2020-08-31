<template>
<v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app clipped>
        <v-list>
            <v-list-item router-link to="/">
                <v-list-item-action>
                    <v-icon>mdi-view-dashboard</v-icon>
                </v-list-item-action>
                <v-list-item-content>
                    <v-list-item-title>Dashboard</v-list-item-title>
                </v-list-item-content>
            </v-list-item>
            <v-list-item router-link to="/settings">
                <v-list-item-action>
                    <v-icon>mdi-cog</v-icon>
                </v-list-item-action>
                <v-list-item-content>
                    <v-list-item-title>Settings</v-list-item-title>
                </v-list-item-content>
            </v-list-item>
        </v-list>
    </v-navigation-drawer>

    <v-app-bar app clipped-left dense>
        <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
        <v-toolbar-title>Water Level Web</v-toolbar-title>
    </v-app-bar>

    <v-main>
        <v-flex>
            <v-container class="fill-height" fluid>
                <v-row align="center" justify="center">
                    <v-col>
                        <router-view />
                    </v-col>
                </v-row>
            </v-container>
        </v-flex>
    </v-main>

    <v-footer app height=30>
        <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
</v-app>
</template>

<script>
export default {
    props: {
        source: String,
    },
    data: () => ({
        drawer: null,
    }),
    created() {
        this.$vuetify.theme.dark = true
    },
}
</script>
