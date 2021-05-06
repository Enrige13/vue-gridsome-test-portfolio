<template>
    <section id="projects" class="project-section">
        <v-container>
            <v-row>
                <v-col>
                    <h1>Projects</h1>
                </v-col>
            </v-row>
            <v-row class="justify-space-around mb-8 mt-4">
                <v-card
                    v-for="project in projects"
                    :key="project.name"
                    class=""
                    max-width="400"
                >
                    <v-img
                    class="white--text align-end"
                    height="200px"
                    :src="project.image"
                    >
                    <v-card-title>
                        {{ project.name }}
                    </v-card-title>
                    </v-img>

                    <v-card-text class="text--primary">
                        {{ truncate(project.description) }}
                    </v-card-text>
                    <v-card-text class="text--primary">
                        {{ project.techs }}
                    </v-card-text>

                    <v-card-actions>
                    <v-btn
                        color="orange"
                        text
                        :href="project.github"
                    >
                        Github Repo
                    </v-btn>

                    </v-card-actions>
                </v-card>
            </v-row>
        </v-container>
    </section>
</template>

<script>
export default {
    data() {
        return {
            projects: [
                {
                    name: 'Adopt Pets',
                    github: 'https://github.com/Enrige13/adopt-pets',
                    description: 'Lorem ipsum',
                    image: 'https://cdn.vuetifyjs.com/images/cards/docks.jpg',
                    techs: 'Vue 2' + ' ' + 'JavaScript'
                },
                {
                    name: 'PW Generator',
                    github: 'https://github.com/Enrige13/pw-generator',
                    description: 'Lorem ipsum',
                    image: 'https://cdn.vuetifyjs.com/images/cards/docks.jpg',
                    techs: 'HTML5' + ' ' + 'JavaScript'
                }
            ]
        }
    },
    methods: {
        truncate(str) {
            if (str.length > 80) {
                return str.slice(0, 79) + '...'
            }
            return str
        }
    }
}
</script>

<style scoped>
.project-section {
    background-color: #FFD563;
}
.v-image {
    filter: grayscale(100%);
    border-bottom: 1px solid;
}
</style>
