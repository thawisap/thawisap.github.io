<template>
  <div class="home">
    <app-banner></app-banner>
    <v-container>
      <v-layout wrap >
        <v-flex xs12 id="about">
          <div class="display-1 font-weight-bold" id="about">About me</div>
        </v-flex>
        <v-flex xs12 mt-5>
          <div class="body-1">{{ aboutMe }}</div>
        </v-flex>
      </v-layout>
      
      <v-layout wrap my-16>
        <v-flex xs12 id="skill">
          <div class="display-1 font-weight-bold" id="portfolio">Language Skills</div>
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
        <v-flex xs12 id="skill">
          <div class="display-1 font-weight-bold" id="portfolio">Framework</div>
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
        <v-flex xs12 id="skill">
          <div class="display-1 font-weight-bold" id="portfolio">DevOps</div>
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
        <v-flex xs12 id="skill">
          <div class="display-1 font-weight-bold" id="portfolio">Database</div>
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

    </v-container>
  </div>
</template>

<script>
import AppBanner from "@/components/AppBanner.vue";
import AppSkillCard from '../components/AppSkillCard.vue';

export default {
  components: { AppBanner, AppSkillCard },
  data: () => ({
    aboutMe:
      "I love coding and develop web and apps. I enjoy learning and Try new technology for develope software in my free time. I just curious to see how things work. I quick learnning when i love it. Love to encourage my friend that they can do it too !",
    languageSkills: [
      { name: 'Javacsript', logo: 'javascript.png' },
      { name: 'Typescript', logo: 'typescript.png' },
      { name: 'Node Js', logo: 'nodejs.png' },
      { name: 'PHP', logo: 'php.png' },
      { name: 'Python', logo: 'python.png' },
      { name: 'Go', logo: 'go.png' },
      { name: 'Dart', logo: 'dart.png' },
      { name: 'Html5', logo: 'html.png' },
      { name: 'Css3', logo: 'css.png' },
      { name: 'Sass', logo: 'sass.png' },
      { name: 'Less', logo: 'less.png' },
      { name: 'Json', logo: 'json.png' },
      { name: 'Yaml', logo: 'yml.png' },
      { name: 'Xml', logo: 'xml.png' },
    ],
    frameworks: [
      { name: 'NestJs', logo: 'nest.png', description: 'JS / TS' },
      { name: 'ExpressJs', logo: 'express.png', description: 'JS / TS' },
      { name: 'KoaJs', logo: 'koa.png', description: 'JS / TS' },
      { name: 'Vue', logo: 'vue.png', description: 'JS / TS' },
      { name: 'React', logo: 'react.png', description: 'JS / TS' },
      { name: 'NextJs', logo: 'nextjs.png', description: 'JS / TS' },
      { name: 'NuxtJs', logo: 'nuxtjs.png', description: 'JS / TS' },
      { name: 'Angular', logo: 'angular.png', description: 'JS / TS' },
      { name: 'Fastify', logo: 'fastify.png', description: 'JS / TS' },
      { name: 'Flutter', logo: 'flutter.png', description: 'Dart' },
      { name: 'Laravel', logo: 'laravel.png', description: 'PHP' },
      { name: 'Codeigniter', logo: 'codeigniter.png', description: 'PHP' },
      { name: 'PHP Slim', logo: 'phpslim.png', description: 'PHP' },
      { name: 'Django', logo: 'django.png', description: 'Python' },
      { name: 'Flask', logo: 'flask.png', description: 'Python' },
      { name: 'Fastapi', logo: 'fast-api.png', description: 'Python' },
      { name: 'Echo', logo: 'echo.png', description: 'Go' },
      { name: 'Gin', logo: 'gin.jpeg', description: 'Go' },
    ],
    devOpsSkills: [
      { name: 'Docker', logo: 'docker.png' },
      { name: 'Kubernetes', logo: 'kubernetes.png' },
      { name: 'Jenkins', logo: 'jenkins.png' },
      { name: 'Terraform', logo: 'terraform.png' },
      { name: 'Git', logo: 'git.png' },
      { name: 'Github', logo: 'github.png' },
      { name: 'Gitlab', logo: 'gitlab.png' },
      { name: 'AWS', logo: 'aws.png' },
      { name: 'GCP', logo: 'gcp.png' },
      { name: 'Argo CI/CD', logo: 'argo.png' },
      { name: 'Pulumi', logo: 'pulumi.png' },
      { name: 'Digital Ocean', logo: 'digital-ocean.png' },
      { name: 'Heroku', logo: 'heroku.png' },
      { name: 'Netlify', logo: 'netlify.png' },
      { name: 'Vercel', logo: 'vercel.png' },
    ],
    databaseSkills: [
      { name: 'MySQL', logo: 'mysql.png' },
      { name: 'Postgresql', logo: 'postgresql.png' },
      { name: 'MongoDB', logo: 'mongodb.png' },
      { name: 'Firebase', logo: 'firebase.png' },
      { name: 'MSSQL', logo: 'mssql.png' },
      { name: 'Sqlite', logo: 'sqlite.png' },
    ],
  }),
};
</script>
