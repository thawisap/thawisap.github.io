<template>
  <div class="home">
    <app-banner></app-banner>
    <v-container>
      <v-layout wrap>
        <v-flex xs12>
          <div class="display-1 font-weight-bold" id="about">About me</div>
        </v-flex>
        <v-flex xs12 mt-5>
          <div class="body-1">{{ aboutMe }}</div>
        </v-flex>
      </v-layout>

      <v-layout wrap my-16>
        <v-flex xs12 id="experience">
          <div class="display-1 font-weight-bold">Experience</div>
        </v-flex>
        <v-flex xs12 mt-5>
          <div class="body-1">
            <v-timeline align-top>
              <v-timeline-item
                v-for="(experience, i) in experiences"
                :key="i"
                :color="experience.color"
                small
                :class="`${i % 2 !== 1 ? 'text-left' : 'text-right'}`"
              >
                <template>
                  <span
                    :class="`headline font-weight-bold ${experience.color}--text`"
                    >{{ experience.year }}, {{ experience.business }}</span
                  >
                </template>
                <div class="pt-4">
                  <h2
                    :class="`headline font-weight-light mb-4 ${experience.color}--text`"
                  >
                    {{ experience.role }}
                  </h2>
                </div>
                <div>
                  <v-chip
                    v-for="(ref, i) in experience.ref"
                    :key="i"
                    :href="ref.link"
                    :color="experience.color"
                    class="ma-2"
                    dark
                  >
                    <v-icon>mdi-link</v-icon> {{ ref.name }}
                  </v-chip>
                </div>
              </v-timeline-item>
            </v-timeline>
          </div>
        </v-flex>
      </v-layout>

      <v-layout wrap my-16>
        <v-flex xs12 id="education">
          <div class="display-1 font-weight-bold">Education</div>
        </v-flex>
        <v-flex xs12 mt-5>
          <div class="text-h6">{{ bachelor }}</div>
        </v-flex>
      </v-layout>

      <v-layout wrap my-16>
        <v-flex xs12 id="skill">
          <div class="display-1 font-weight-bold">Language Skills</div>
        </v-flex>
        <v-flex xs12 class="mt-5">
          <v-layout wrap>
            <template v-for="(languageSkill, i) in languageSkills">
              <v-flex :key="i" xs12 sm6 md4>
                <app-skill-card :data="languageSkill" />
              </v-flex>
            </template>
          </v-layout>
        </v-flex>
      </v-layout>

      <v-layout wrap my-16>
        <v-flex xs12>
          <div class="display-1 font-weight-bold">Framework</div>
        </v-flex>
        <v-flex xs12 class="mt-5">
          <v-layout wrap>
            <template v-for="(framework, i) in frameworks">
              <v-flex :key="i" xs12 sm6 md4>
                <app-skill-card :data="framework" />
              </v-flex>
            </template>
          </v-layout>
        </v-flex>
      </v-layout>

      <v-layout wrap my-16>
        <v-flex xs12>
          <div class="display-1 font-weight-bold">DevOps</div>
        </v-flex>
        <v-flex xs12 class="mt-5">
          <v-layout wrap>
            <template v-for="(devOpsSkill, i) in devOpsSkills">
              <v-flex :key="i" xs12 sm6 md4>
                <app-skill-card :data="devOpsSkill" />
              </v-flex>
            </template>
          </v-layout>
        </v-flex>
      </v-layout>

      <v-layout wrap my-16>
        <v-flex xs12 id="database">
          <div class="display-1 font-weight-bold">Database</div>
        </v-flex>
        <v-flex xs12 class="mt-5">
          <v-layout wrap>
            <template v-for="(databaseSkill, i) in databaseSkills">
              <v-flex :key="i" xs12 sm6 md4>
                <app-skill-card :data="databaseSkill" />
              </v-flex>
            </template>
          </v-layout>
        </v-flex>
      </v-layout>

      <v-layout wrap my-16>
        <v-flex xs12 mb-5>
          <div class="display-1 font-weight-bold" id="contact">Contact me</div>
        </v-flex>
        <template v-for="(contact, i) in contacts">
          <v-flex sm6 md4 xs12 :key="i">
            <app-contact :contact="contact"></app-contact>
          </v-flex>
        </template>
      </v-layout>
    </v-container>
  </div>

  <!-- I love codding and develop web and apps. I lilk to learn new tecnology and research new technical for develop yourself    -->

  <!-- ฉันชื่นชอบในการเขียนโปรแกรม และ ชอบเรียนรู้เทคโนโลยีใหม่ๆ ,ชอบหาเทคนิคใหม่ๆในการพัฒนาตัวเอง ,ฉันชอบในการทำงานเป็นทีม ,ฉันสามารถเรียนรู้ได้เร็ว  -->
</template>

<script>
import AppBanner from "@/components/AppBanner.vue";
import AppSkillCard from "../components/AppSkillCard.vue";
import AppContact from "../components/AppContact.vue";

export default {
  components: { AppBanner, AppSkillCard, AppContact },
  data: () => ({
    aboutMe:
      "I love codding and develop web and apps. I lilk to learn new tecnology and research new technical for develop yourself.",
    bachelor:
      "Bachelor of Computer Science ,Khon Kaen University — 2013-2016",
    experiences: [
      {
        color: "yellow",
        year: "2018 - PRESET",
        business: "Ookbee Co., Ltd.",
        role: "Web Developer",
        ref: [
          {
            name: "Ookbee Co., Ltd.",
            link: "https://www.ookbee.com/",
          },
        ],
      },

      {
        color: "orange",
        year: "2016 - 2017",
        business: "Orange Technology Solution",
        role: "Web Developer",
        ref: [{ name: "Orange", link: "https://www.orange-thailand.com/" }],
      },
    ],
    languageSkills: [
      { name: "Javacsript", logo: "javascript.png" },
      { name: "Typescript", logo: "typescript.png" },
      { name: "Node Js", logo: "nodejs.png" },
      { name: "PHP", logo: "php.png" },
      { name: "Python", logo: "python.png" }, 
      { name: "Dart", logo: "dart.png" },
      { name: "Html5", logo: "html.png" },
      { name: "Css3", logo: "css.png" },
      { name: "Sass", logo: "sass.png" },
      { name: "Less", logo: "less.png" }, 
    ],
    frameworks: [
      { name: "NestJs", logo: "nest.png", description: "JS / TS" },
      { name: "ExpressJs", logo: "express.png", description: "JS / TS" },
      { name: "KoaJs", logo: "koa.png", description: "JS / TS" },
      { name: "Vue", logo: "vue.png", description: "JS / TS" },
      { name: "React", logo: "react.png", description: "JS / TS" },
      { name: "NextJs", logo: "nextjs.png", description: "JS / TS" },
      { name: "NuxtJs", logo: "nuxtjs.png", description: "JS / TS" },
      { name: "Flutter", logo: "flutter.png", description: "Dart" },
      { name: "Laravel", logo: "laravel.png", description: "PHP" }, 
      { name: "Flask", logo: "flask.png", description: "Python" },
    ],
    devOpsSkills: [
      { name: "Docker", logo: "docker.png" },
      { name: "Git", logo: "git.png" },
      { name: "Github", logo: "github.png" },
      { name: "Gitlab", logo: "gitlab.png" },
    ],
    databaseSkills: [
      { name: "MySQL", logo: "mysql.png" },
      { name: "Postgresql", logo: "postgresql.png" },
      { name: "MongoDB", logo: "mongodb.png" },
      { name: "Firebase", logo: "firebase.png" }, 
      { name: "Sqlite", logo: "sqlite.png" },
    ],
    contacts: [
      {
        name: "Email",
        value: "thawisap.numnoii@gmail.com",
        link: "mailto:thawisap.numnoii@gmail.com",
        icon: "mdi-email",
      },
      {
        name: "Github",
        value: "thawisap",
        link: "https://github.com/Thawisap",
        icon: "mdi-github",
      },
      {
        name: "Facebook",
        value: "Thawisap prathammate",
        link: "https://www.facebook.com/thawisap.prathammate/",
        icon: "mdi-facebook",
      },
      {
        name: "Tel",
        value: "Thawisap prathammate",
        link: "tel:66829913791",
        icon: "mdi-phone",
      },
    ],
  }),
};
</script>
