<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :clipped="clipped"
      fixed
      temporary
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="`drawer_nav_item_${i}`"
          :to="item.to"
          :href="item.href"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" app>
      <v-app-bar-nav-icon
        @click.stop="drawer = !drawer"
        class="hidden-sm-and-up"
      />
      <v-toolbar-title v-text="title" />

      <v-spacer />

      <v-toolbar-items class="hidden-xs-only">
        <v-divider vertical></v-divider>
        <template v-for="(item, i) in items">
          <v-btn
            text
            v-bind:key="`toolbar_item_${i}_btn`"
            :to="items[i].to"
            :href="items[i].href"
          >
            {{ items[i].title }}
          </v-btn>
          <v-divider vertical :key="`toolbar_item_${i}_divider`"></v-divider>
        </template>
      </v-toolbar-items>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }} huhubun</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: true,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-home-outline',
          title: '首页',
          to: '/'
        },
        {
          icon: 'mdi-information-outline',
          title: '关于呼呼小笼包',
          href: 'https://nzc.me'
        }
      ],
      title: '呼呼小笼包的主页'
    }
  }
}
</script>
