<template>
  <v-app>
    <v-navigation-drawer width="240px" permanent fixed>
      <v-list-item>
        <v-list-item-avatar>
          <v-img src="https://randomuser.me/api/portraits/men/85.jpg"></v-img>
        </v-list-item-avatar>
        <v-list-item-content>
          <v-list-item-title class="title">
            Julian Hiess
          </v-list-item-title>
          <v-list-item-subtitle>
            Junior Webdeveloper
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
          :to="`#${item.title.toLowerCase().replace(' & ', '-')}`"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <slot/>
    </v-main>  
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      items: [
          { title: 'About', icon: 'mdi-account-box-outline' },
          { title: 'Projects', icon: 'mdi-apps' },
          { title: 'Education & Experience', icon: 'mdi-school-outline' },
          { title: 'Contact', icon: 'mdi-message-text-outline' },
        ],
        right: null,
    }
  }
}
</script>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style>
html {
  scroll-behavior: smooth;
}
.v-application--wrap {
  flex-direction: row;
}

.v-main {
  margin-left: 240px;
  flex: 1 0;
}
</style>
