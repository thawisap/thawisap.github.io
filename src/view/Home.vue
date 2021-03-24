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
                    <v-chip v-for="(ref, i) in experience.ref" :key="i" :href="ref.link" :color="experience.color" class="ma-2" dark>
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
            <app-contact :contact="contact" ></app-contact>
          </v-flex>
        </template>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
import AppBanner from "@/components/AppBanner.vue";
import AppSkillCard from "../components/AppSkillCard.vue";
import AppContact from '../components/AppContact.vue';

export default {
  components: { AppBanner, AppSkillCard, AppContact },
  data: () => ({
    aboutMe:
      "I love coding and develop web and apps. I enjoy learning and Try new technology for develope software in my free time. I just curious to see how things work. I quick learnning when i love it. Love to encourage my friend that they can do it too !",
    bachelor:
      "Bachelor of Science Program in Information and Communication Technology, Major Computer Science, Sukhothai Thammathirat Open University — 2013-2016",
    experiences: [
      {
        color: "red",
        year: "2019 - PRESET",
        business: "SCG Digital Office",
        role: "Technology Developer",
        ref: [
          {
            name: "SCG Digital Office",
            link: "https://www.scg.com/innovation/digital-office-scg/",
          },
        ],
      },
      {
        color: "green",
        year: "2018 - 2019",
        business: "Deepscope & Soilfish",
        role: "Senior Fullstack Software Engineer",
        ref: [
          { name: "Deepscope", link: "https://deepscope.com/" },
          { name: "Soilfish", link: "https://soilfish.co/" },
        ],
      },
      {
        color: "cyan",
        year: "2017 - 2018",
        business: "Tixget / Dtac Accelerate",
        role: "Software Developer",
        ref: [{ name: "tixget", link: "#" }],
      },
      {
        color: "orange",
        year: "2016 - 2017",
        business: "Orange Technology Solution",
        role: "Web Programmer",
        ref: [{ name: "Orange", link: "https://www.orange-thailand.com/" }],
      },
    ],
    languageSkills: [
      { name: "Javacsript", logo: "javascript.png" },
      { name: "Typescript", logo: "typescript.png" },
      { name: "Node Js", logo: "nodejs.png" },
      { name: "PHP", logo: "php.png" },
      { name: "Python", logo: "python.png" },
      { name: "Go", logo: "go.png" },
      { name: "Dart", logo: "dart.png" },
      { name: "Html5", logo: "html.png" },
      { name: "Css3", logo: "css.png" },
      { name: "Sass", logo: "sass.png" },
      { name: "Less", logo: "less.png" },
      { name: "Json", logo: "json.png" },
      { name: "Yaml", logo: "yml.png" },
      { name: "Xml", logo: "xml.png" },
    ],
    frameworks: [
      { name: "NestJs", logo: "nest.png", description: "JS / TS" },
      { name: "ExpressJs", logo: "express.png", description: "JS / TS" },
      { name: "KoaJs", logo: "koa.png", description: "JS / TS" },
      { name: "Vue", logo: "vue.png", description: "JS / TS" },
      { name: "React", logo: "react.png", description: "JS / TS" },
      { name: "NextJs", logo: "nextjs.png", description: "JS / TS" },
      { name: "NuxtJs", logo: "nuxtjs.png", description: "JS / TS" },
      { name: "Angular", logo: "angular.png", description: "JS / TS" },
      { name: "Fastify", logo: "fastify.png", description: "JS / TS" },
      { name: "Flutter", logo: "flutter.png", description: "Dart" },
      { name: "Laravel", logo: "laravel.png", description: "PHP" },
      { name: "Codeigniter", logo: "codeigniter.png", description: "PHP" },
      { name: "PHP Slim", logo: "phpslim.png", description: "PHP" },
      { name: "Django", logo: "django.png", description: "Python" },
      { name: "Flask", logo: "flask.png", description: "Python" },
      { name: "Fastapi", logo: "fast-api.png", description: "Python" },
      { name: "Echo", logo: "echo.png", description: "Go" },
      { name: "Gin", logo: "gin.jpeg", description: "Go" },
    ],
    devOpsSkills: [
      { name: "Docker", logo: "docker.png" },
      { name: "Kubernetes", logo: "kubernetes.png" },
      { name: "Jenkins", logo: "jenkins.png" },
      { name: "Terraform", logo: "terraform.png" },
      { name: "Git", logo: "git.png" },
      { name: "Github", logo: "github.png" },
      { name: "Gitlab", logo: "gitlab.png" },
      { name: "AWS", logo: "aws.png" },
      { name: "GCP", logo: "gcp.png" },
      { name: "Argo CI/CD", logo: "argo.png" },
      { name: "Pulumi", logo: "pulumi.png" },
      { name: "Digital Ocean", logo: "digital-ocean.png" },
      { name: "Heroku", logo: "heroku.png" },
      { name: "Netlify", logo: "netlify.png" },
      { name: "Vercel", logo: "vercel.png" },
    ],
    databaseSkills: [
      { name: "MySQL", logo: "mysql.png" },
      { name: "Postgresql", logo: "postgresql.png" },
      { name: "MongoDB", logo: "mongodb.png" },
      { name: "Firebase", logo: "firebase.png" },
      { name: "MSSQL", logo: "mssql.png" },
      { name: "Sqlite", logo: "sqlite.png" },
    ],
    contacts: [
        {
          name: "Email",
          value: "preecharat.lookod@gmail.com",
          link: "mailto:reecharat.lookod@gmail.com",
          icon: "mdi-email"
        },
        {
          name: "LinkedIn",
          value: "Precharat Chuenta",
          link: "https://www.linkedin.com/in/preecharat-chuenta/",
          icon: "mdi-linkedin"
        },
        {
          name: "Github",
          value: "iamlookod",
          link: "https://github.com/iamlookod/",
          icon: "mdi-github"
        },
        {
          name: "Facebook",
          value: "Precharat Chuenta",
          link: "https://www.facebook.com/OddPrecharat",
          icon: "mdi-facebook"
        },
        {
          name: "Tel",
          value: "Precharat Chuenta",
          link: "tel:66803355181",
          icon: "mdi-phone"
        },
      ]
  }),
};
</script>
