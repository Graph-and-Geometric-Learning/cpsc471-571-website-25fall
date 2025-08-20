<template>
    <v-app-bar color="#4169e1">
        <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
        <v-toolbar-title>CPSC 471/571: Trustworthy Deep Learning</v-toolbar-title>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer">
        <v-list density="default" nav>
            <v-list-item v-for="page in pages" :prepend-icon="page.prepend_icon" :title="page.title" :value="page.value"
                :to="page.value" color="primary">
            </v-list-item>
            <v-list-item prepend-icon="mdi-star" title="Canvas" value="canvas"
                href="https://yale.instructure.com/courses/108561" color="primary"></v-list-item>
        </v-list>
    </v-navigation-drawer>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
    name: "Navigation",
    data: () => ({
        drawer: true,
        pages: [
            { prepend_icon: "mdi-graphql", title: "Logistics", value: "logistics" },
            { prepend_icon: "mdi-account-multiple", title: "Staff", value: "staff" },
            // { prepend_icon: "mdi-folder", title: "Content", value:"content" },
            { prepend_icon: "mdi-calendar", title: "Syllabus", value: "syllabus" },
            { prepend_icon: "mdi-text-box-remove-outline", title: "Policies", value: "policies" },
            { prepend_icon: "mdi-office-building", title: "Office Hours", value: "officehours" },
            { prepend_icon: "mdi-help", title: "FAQ", value: "faq" },
            // { prepend_icon: "mdi-star", title: "Canvas", value: "canvas" },
        ],
    }),
})
</script>
