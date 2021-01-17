<template>
  <v-app>
    <v-app-bar
        app
        absolute
        color="#6A76AB"
        dark
        shrink-on-scroll
        prominent
        src="https://cdn.pixabay.com/photo/2018/08/14/09/59/mountains-3605113_960_720.jpg"
        fade-img-on-scroll
        scroll-target="#scrolling-techniques-3"
    >
      <template v-slot:img="{ props }">
        <v-img
            v-bind="props"
            gradient="to top right, rgba(100,115,201,.7), rgba(25,32,72,.7)"
        ></v-img>
      </template>
      <v-app-bar-title>Portfolio</v-app-bar-title>
    </v-app-bar>

    <v-main class="bg">
      <v-container>
        <v-row justify="center">
          <v-col cols="6">
            <h1 class="mt-4">基本情報</h1>
            <v-card class="mt-4">
              <v-card-title>Profile</v-card-title>
              <v-list two-line>
                <v-list-item
                    v-for="item in profile"
                    :key="item.title"
                >
                  <v-list-item-icon>
                    <v-icon :color="item.color">
                      {{ item.icon }}
                    </v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>{{ item.title }}</v-list-item-title>
                    <v-list-item-subtitle v-if="item.subtitle">{{ item.subtitle }}</v-list-item-subtitle>
                    <v-list-item-subtitle v-if="item.link"><a :href="item.link">{{ item.linktitle }}</a>
                    </v-list-item-subtitle>
                  </v-list-item-content>
                </v-list-item>
              </v-list>
            </v-card>
          </v-col>

          <v-col cols="12" class="mt-4">
            <h1>プログラミング</h1>
            <p>星マークの付いているものは、実務経験(インターン)あり</p>
            <v-row class="mt-4">
              <layout-card card-title="言語" :items="languages"></layout-card>
              <layout-card card-title="フレームワーク" :items="frameworks"></layout-card>
              <layout-card card-title="データベース" :items="databases"></layout-card>
              <layout-card card-title="サーバー・インフラ" :items="servers"></layout-card>
            </v-row>
          </v-col>

          <v-col cols="12" class="mt-4 mb-16">
            <h1>作品</h1>
            <p>これらの作品は一部です。機械学習を使用しているリポジトリ等は<a href="https://github.com/I-Root-Route?tab=repositories">GitHub</a>で確認できます</p>
            <v-row>
              <layout-work-card Title="Travel Web App" cardImage='https://life-void.com/wp-content/uploads/travel.png'
                                linkto="https://brave-plant-06292c600.azurestaticapps.net/">
                <v-card-text class="text--primary">
                  一人旅の経験から、旅の記録を行えるWebアプリがあると便利だと思い、作りました。出費や滞在日数等を記録できます。また、以下の情報でログインが可能です。<br>
                  <p class="text-center"> ユーザー名: testuser <br> パスワード: test <br></p>
                  ログインできない場合は時間を置いて再度試してみてください。<br>
                  <ul>
                    <li>フロントエンド: Vue, Vuetify</li>
                    <li>バックエンド: Python(Flask)</li>
                    <li>データベース: ElasticSearch</li>
                    <li>サーバー・インフラ
                      <ul>
                        <li>Azure App Service</li>
                        <li>Azure Static Web App</li>
                      </ul>
                    </li>
                    <li>GitHub
                      <ul>
                        <li><a href="https://github.com/I-Root-Route/travel-web-app">フロントエンド</a></li>
                        <li><a href="https://github.com/I-Root-Route/travel-web-app-backend">バックエンド</a></li>
                      </ul>
                    </li>
                  </ul>
                </v-card-text>
              </layout-work-card>

              <layout-work-card Title="本ポートフォリオ"
                                cardImage="https://life-void.com/wp-content/uploads/スクリーンショット-2021-01-17-15.26.36.png"
                                linkto="/"
              >
                <v-card-text class="text--primary">
                  <ul>
                    <li>フロントエンド: Vue.js, Vuetify</li>
                    <li>サーバー・インフラ: Azure Static Web App</li>
                    <li><a href="https://github.com/I-Root-Route/vue-portfolio">GitHub</a></li>
                  </ul>
                </v-card-text>

              </layout-work-card>


              <layout-work-card
                Title="FlowProd"
                cardImage="https://life-void.com/wp-content/uploads/スクリーンショット-2021-01-17-15.37.16.png"
                linkto="https://flowprod.herokuapp.com"
              >
                <v-card-text class="text--primary">
                  音楽制作の経験から、音楽制作における調べ物の時間を短縮するために作りました。検索窓にはアーティスト名を入れてください。<br>
                  ※初回起動時は時間がかかる場合があります。
                  <ul>
                    <li>フロントエンド: HTML/CSS</li>
                    <li>バックエンド: Python(Flask)</li>
                    <li>データベース: SQLite</li>
                    <li>その他: YouTubeAPI, SpotifyAPI</li>
                    <li>インフラ・サーバー: Heroku</li>
                    <li><a href="https://github.com/I-Root-Route/flowprod">GitHub</a></li>
                  </ul>
                </v-card-text>
              </layout-work-card>
            </v-row>

          </v-col>


          <v-col cols="12">
            <h1>音楽制作</h1>
            <p>今までリリース・プロモートされた曲のうち4曲を載せておきます。</p>
            <v-row class="mt-4">
              <v-col cols="6">
                <iframe width="100%" height="315" src="https://www.youtube.com/embed/Fq8yNcv-E-E" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
              </v-col>
              <v-col cols="6">
                <iframe width="100%" height="315" src="https://www.youtube.com/embed/9RoHg4qpRqE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
              </v-col>

              <v-col cols="6">
                <iframe width="100%" height="315" src="https://www.youtube.com/embed/C00uJ-kDs7A" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
              </v-col>

              <v-col cols="6">
                <iframe width="100%" height="315" src="https://www.youtube.com/embed/gyiGTkadZHA" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
              </v-col>

            </v-row>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>


<style>
.bg {
  background-color: ghostwhite;
}
</style>

<script>
import LayoutCard from "@/components/LayoutCard";
import LayoutWorkCard from "@/components/LayoutWorkCard";

export default {
  components: {
    LayoutCard,
    LayoutWorkCard
  },
  data: () => ({
    profile: [
      {
        icon: "mdi-school",
        title: "東京理科大学",
        subtitle: "理工学部情報科学科",
        color: "black"
      },
      {
        icon: "mdi-git",
        title: "I-Root-Route",
        link: "https://github.com/I-Root-Route?tab=repositories",
        linktitle: "GitHubのリポジトリに移動",
        color: "orange"
      },
      {
        icon: "mdi-spotify",
        title: "Root Introvert",
        link: "https://open.spotify.com/artist/2BFl1d7x1czOzdjt63O8Qe?si=1ySd5hTrT5qV798PMZ9Jvg",
        linktitle: "Spotifyに移動",
        color: "green"
      }
    ],
    languages: [
      {
        icon: "mdi-language-python",
        title: "Python",
        color: "light-blue",
        star: "mdi-star"
      },
      {
        icon: "mdi-language-php",
        title: "PHP",
        color: "purple",
        star: "mdi-star"
      },
      {
        icon: "mdi-language-go",
        title: "Go",
        color: "blue"
      },
      {
        icon: "mdi-laptop",
        title: "Dart",
        color: "light-green"
      }
    ],
    frameworks: [
      {
        icon: "mdi-language-python",
        title: "Flask",
        color: "light-green",
        star: "mdi-star"
      },
      {
        icon: "mdi-language-php",
        title: "Laravel",
        color: "orange",
        star: "mdi-star"
      },
      {
        icon: "mdi-language-javascript",
        title: "Vue.js, Vuetify",
        color: "green",
        star: "mdi-star"
      },
      {
        icon: "mdi-laptop",
        title: "Flutter",
        color: "light-blue"
      }
    ],
    databases: [
      {
        icon: "mdi-database",
        title: "MySQL",
        color: "black",
        star: "mdi-star"
      },
      {
        icon: "mdi-hexagon-multiple",
        title: "ElasticSearch",
        color: "green",
        star: "mdi-star"
      }
    ],
    servers: [
      {
        icon: "mdi-server",
        title: "Azure",
        color: "blue",
        star: "mdi-star"
      }
    ],
    works: [
      {
        color: '#1F7087',
        src: '../public/img/travel.png',
        title: 'Supermodel',
        artist: 'Foster the People',
      }
    ]
  })
}
</script>