<template>
<div id="app">
  <v-app id="inspire">
    <!-- <v-navigation-drawer
      fixed
      :clipped="$vuetify.breakpoint.mdAndUp"
      app
      v-model="drawer"
    >
      <v-list dense>
        <template v-for="item in items">
          <v-layout
            row
            v-if="item.heading"
            align-center
            :key="item.heading"
          >
            <v-flex xs6>
              <v-subheader v-if="item.heading">
                {{ item.heading }}
              </v-subheader>
            </v-flex>
            <v-flex xs6 class="text-xs-center">
              <a href="#!" class="body-2 black--text">EDIT</a>
            </v-flex>
          </v-layout>
          <v-list-group
            v-else-if="item.children"
            v-model="item.model"
            :key="item.text"
            :prepend-icon="item.model ? item.icon : item['icon-alt']"
            append-icon=""
          >
            <v-list-tile slot="activator">
              <v-list-tile-content>
                <v-list-tile-title>
                  {{ item.text }}
                </v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
            <v-list-tile
              v-for="(child, i) in item.children"
              :key="i"
              @click=""
            >
              <v-list-tile-action v-if="child.icon">
                <v-icon>{{ child.icon }}</v-icon>
              </v-list-tile-action>
              <v-list-tile-content>
                <v-list-tile-title>
                  {{ child.text }}
                </v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
          </v-list-group>
          <v-list-tile v-else @click="" :key="item.text">
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>
                {{ item.text }}
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </template>
      </v-list>
    </v-navigation-drawer> -->
    <v-toolbar
      color="withe"
      flat
      height="100%"
      app
      :clipped-left="$vuetify.breakpoint.mdAndUp"
      fixed
    >
      <v-toolbar-title style="width: 300px" class="ml-0 pl-3">
        <!-- <v-toolbar-side-icon  @click.stop="drawer = !drawer"></v-toolbar-side-icon> -->
        <v-btn
        flat
        exact
        :to="{name: 'home'}"
        >
        <span
        class="hidden-sm-and-down">Lion cho</span>
        </v-btn>
      </v-toolbar-title>

      <v-spacer></v-spacer>
            <v-btn
              flat icon
              large
              href=https://github.com/CHOHYOJUN
              target="_blank"
              >
              <v-icon color="indigo">fab fa-github</v-icon>
            </v-btn>
      <v-toolbar-items>
        <v-btn
        flat
        :to="{name: 'about'}"
        >about</v-btn>
        <v-btn
        flat
        exact
        :to="{name: 'portfolio'}"
        >project</v-btn>
        <!-- <v-btn flat>Link Two</v-btn> -->
      </v-toolbar-items>
    </v-toolbar>

    <v-content>
      <v-container
      align-baseline
      >
            <router-view/>
      </v-container>

    </v-content>
      <v-footer class="pa-3">
    <v-icon>email</v-icon>
    <span>
    lionjerher84@gmail.com
    </span>
    <v-spacer></v-spacer>
    <div>&copy; {{ new Date().getFullYear() }}</div>
  </v-footer>
  </v-app>
</div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      dialog: false,
      // drawer: false,
      // items: [
      //   { icon: 'contacts', text: 'Contacts' },
      //   { icon: 'history', text: 'Frequently contacted' },
      //   { icon: 'content_copy', text: 'Duplicates' },
      //   { icon: 'settings', text: 'Settings' },
      //   { icon: 'chat_bubble', text: 'Send feedback' },
      //   { icon: 'help', text: 'Help' },
      //   { icon: 'phonelink', text: 'App downloads' },
      // ],
    }
   }
}
</script>
