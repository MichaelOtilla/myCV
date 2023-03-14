<template>
  <v-card
    color="grey lighten-4"
    light
  >
    <v-card-text id="to-timeline">
      <content-section
        title="Who am I?"
      >
        I'm a developer born in the Phillipines and currently working at  <a href="http://www.hrd-s.com/">HRD Singapore PTE LTD</a>.<br>
        Proficient in programming and web development, I possess a diverse range of skills and knowledge in various aspects of Information Technology.
      </content-section>
      <content-section
        v-if="prouds"
        title="What am I proud of?"
      >
        <v-layout
          v-for="(proud, i) in prouds"
          :key="i"
        >
          <v-flex
            md1
            xs3
          >
            <v-icon right>
              {{ proud.icon }}
            </v-icon>
          </v-flex>
          <v-flex
            md11
            xs9
          >
            <p>
              <strong>{{ proud.text }}</strong><br>
              {{ proud.source }}
            </p>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="educations"
        title="Education"
      >
        <v-layout
          v-for="(education, i) in educations"
          :key="i"
        >
          <v-flex md4>
            {{ education.from }} - {{ education.to }}
          </v-flex>
          <v-flex md8>
            <strong v-if="education.title">{{ education.title }}</strong>
            <div v-if="education.location">
              <i>{{ education.location }}</i>
            </div>
            <div v-if="education.description">
              {{ education.description }}
            </div>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="skills"
        title="Skills"
      >
        <template slot="actions">
          (% are relative not absolute)
        </template>
        <v-layout wrap>
          <template
            v-for="(skill, i) in skills"
          >
            <v-flex
              v-if="skill.divider"
              :key="i"
              md12
              xs12
              mb-4
            />
            <v-flex
              v-else
              :key="i"
              md6
              xs12
            >
              <div
                class="mr-2 ml-2"
              >
                <div class="align-center">
                  <v-icon
                    small
                  >
                    {{ skill.icon }}
                  </v-icon>
                  {{ skill.title }}
                </div>
                <v-progress-linear
                  class="progress"
                  color="secondary"
                  height="3"
                  :value="skill.value"
                />
              </div>
            </v-flex>
          </template>
        </v-layout>
      </content-section>
    </v-card-text>
  </v-card>
</template>

<script>
import ContentSection from '@/views/dark-template/content/Section'
export default {
  name      : 'MainContent',
  components: { ContentSection },
  data      : () => ({
    prouds: [
      {
        icon  : 'mdi-teach',
        text  : 'I trained newly recruited and reassigned employees in FullStack Development.',
        source: 'Covering VueJS for front-end and NodeJS for back-end development. For Database, I covered SQL (MySQL, MsSql), and NoSQL(CouchDB)',
      },
      {
        icon  : 'mdi-timer-sand',
        text  : "Developed a web application that enhanced production process efficiency by reducing processing time.",
        source: 'The web application I developed includes data extraction, customized system features tailored to meet user requirements, and integration with other systems for automated processing.',
      },
      {
        icon  : 'mdi-brain',
        text  : 'Provide solutions to my fellow programming colleagues in a consulting capacity.',
        source: '',
      },
      // {
      //   icon  : 'mdi-account-multiple',
      //   text  : 'Tried to cover small part of 7 people expenses.',
      //   source: '(My awesome colleagues)',
      // },
    ],
    educations: [
      {
        from       : '2015',
        to         : '2019',
        title      : 'Bachelor\'s degree, Computer Engineering',
        location   : 'San Sebastian College Recoletos de Cavite',

      },
    ],
    skills: [
      {
        title: 'PHP',
        icon : 'mdi-language-php',
        value: 70,
      },
      {
        title: 'Laravel Framework',
        icon : 'mdi-laravel',
        value: 60,
      },
      {
        title: 'JavaScript',
        icon : 'mdi-language-javascript',
        value: 95,
      },
      {
        title: 'Node.js',
        icon : 'mdi-nodejs',
        value: 80,
      },
      {
        title: 'Vue.js Framework',
        icon : 'mdi-vuejs',
        value: 90,
      },
      {
        title: 'React.js Framework',
        icon : 'mdi-react',
        value: 60,
      },

      {
        title: 'SQL Server',
        icon : 'mdi-database',
        value: 70,
      },
      {
        title: 'CouchDB(NoSQL)',
        icon : 'mdi-sofa',
        value: 90,
      },
      {
        title: 'Continuous Integration / Continuous Delivery',
        icon : 'mdi-truck-fast',
        value: 50,
      },
      {
        title: 'Git',
        icon : 'mdi-git',
        value: 67,
      },
      {
        title: 'Hardware Programming',
        icon : 'mdi-chip',
        value: 15,
      },
      {
        title: 'C/C++',
        icon : 'mdi-language-cpp',
        value: 25,
      },
      {
        title: 'Teaching skills',
        icon : 'mdi-book-open-page-variant',
        value: 70,
      },
      {
        title: 'Web Design',
        icon : 'mdi-star',
        value: 10,
      },
    ],
  }),
}
</script>

<style scoped>
.title {
  border-bottom: 2px #bfbfbf solid;
  line-height: 1.5 !important;
}
.progress {
  margin-top: 0.1rem;
}
</style>
