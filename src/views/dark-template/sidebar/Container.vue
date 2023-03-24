<!-- eslint-disable no-trailing-spaces -->
<template>
  <v-card
    color="grey darken-3"
    dark
  >
    <v-card-text>
      <avatar />
      <div class="text-sm-center mb-4 mt-3">
        <h1>
          Michael Roy <span class="light-blue--text text--lighten-3">Otilla</span>
        </h1>
        <span>
          An Invovative web developer
        </span>
      </div>

      <sidebar-section :options="sections.info" />
      <sidebar-section :options="sections.socials" />
      <sidebar-section :options="sections.hobbies">
        <template v-slot:item="{item}">
          <v-chip>
            <v-avatar>
              <v-icon>
                {{ item.icon }}
              </v-icon>
            </v-avatar>
            {{ item.text }}
          </v-chip>
        </template>
      </sidebar-section>
      <sidebar-section :options="sections.languages">
        <template v-slot:items="{items}">
          <v-container pa-0>
            <v-layout
              wrap
              class="text-xs-center"
            >
              <template
                v-for="(item, i) in items"
              >
                <v-flex
                  :key="i"
                  md3
                  sm4
                  xs6
                >
                  <v-progress-circular
                    rotate="360"
                    size="65"
                    width="2"
                    :value="item.value"
                    color="white"
                    class="ma-2"
                  >
                    {{ item.text }}
                  </v-progress-circular>
                </v-flex>
              </template>
            </v-layout>
          </v-container>
        </template>
      </sidebar-section>
    </v-card-text>
  </v-card>
</template>

<script>
import Avatar from '@/views/dark-template/sidebar/Avatar'
import SidebarSection from '@/views/dark-template/sidebar/Section'
export default {
  name      : 'Sidebar',
  components: { SidebarSection, Avatar },
  data () {
    return {
      sections: {
        info: {
          title: 'INFO',
          items: [
            {
              name: 'Email',
              icon: 'mdi-email',
              text: 'otillamrm@gmail.com',
            },
            {
              name: 'Mobile Number',
              icon: 'mdi-phone',
              text: 'otillamrm@gmail.com',
            },
            {
              name: 'Birth Date',
              icon: 'mdi-cake-variant',
              text: 'Jan 24, 1999',
            },
            {
              name: 'Home',
              icon: 'mdi-map-marker',
              text: 'Phillipines, Cavite City',
            },
          ],
        },
        socials: {
          title: 'SOCIALS',
          items: [
            {
              icon: 'mdi-github-circle',
              text: 'github.com/MichaelOtilla',
              link: 'https://github.com/MichaelOtilla',
            },
            {
              icon: 'mdi-linkedin-box',
              text: 'linkedin.com/in/michael-roy-otilla',
              link: 'https://www.linkedin.com/in/michael-roy-otilla-6935b71bb/',
            },
            {
              icon: 'mdi-facebook',
              text: 'facebook.com/michael.allito',
              link: 'https://www.facebook.com/michael.allito',
            },
          ],
        },
        hobbies: {
          title: 'Hobbies/Interests',
          items: [

            // {
            //   icon: 'mdi-bullseye',
            //   text: 'Getting out of Safe Zone',
            // },
            // {
            //   icon: 'mdi-biohazard',
            //   text: 'Challenges',
            // },
            // {
            //   icon: 'mdi-bike',
            //   text: 'Cycling',
            // },
            // {
            //   icon: 'mdi-',
            //   text: 'Leadership',
            // },
            {
              icon: 'mdi-weather-sunset-up',
              text: 'Solar panels',
            },
            {
              icon: 'mdi-auto-fix',
              text: 'Debugging',
            },
            {
              icon: 'mdi-teach',
              text: 'Teaching',
            },
            {
              icon: 'mdi-robot',
              text: 'Robotics',
            },
            {
              icon: 'mdi-flash',
              text: 'Electronics',
            },
            {
              icon: 'mdi-book-open-page-variant',
              text: 'Novels',
            },
            {
              icon: 'mdi-sword',
              text: 'Fantasy',
            },
            {
              icon: 'mdi-android-debug-bridge',
              text: 'Debugging Bugs!',
            },
          ],
        },
        languages: {
          title: 'LANGUAGES',
          items: [
            {
              text : 'Filipino',
              value: 100,
            },
            {
              text : 'English',
              value: 70,
            },
          ],
        },
        others:{
          title:"OTHER SKILLS",
          items: [
            {
              text : 'Computer Repair',
              value: 100,
            },
            {
              text : 'Networking',
              value: 70,
            },
            {
              text : 'Electronics',
              value: 70,
            },
          ],
        }
      },
    }
  },
}
</script>

<style scoped>
.sidebar{
    background: #2e2e2e;
}
</style>
