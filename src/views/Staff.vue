<template>
  <v-container>
    <v-row>
      <v-col>
        <PhotoCard
          :image_src="rex_ying_image_src"
          name="Rex Ying"
          role="Instructor"
        ></PhotoCard>
      </v-col>
    </v-row>
    <v-row>
      <v-col v-for="p in staff" :key="p.name">
        <PhotoCard v-bind="p" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import PhotoCard from "@/components/PhotoCard.vue";

export default defineComponent({
  components: { PhotoCard },
  data: () => ({
    rex_ying_image_src: new URL(
      "../assets/photos/ying_rex.jpg",
      import.meta.url
    ).href,
    staff: [
      // {
      //     name: "Rex Ying",
      //     image_src: "https://cs.stanford.edu/people/rexy/images/photo_Rex.jpg",
      //     role: "Instructor",
      // },
      // {
      //   name: "Jialin Chen",
      //   image_src: new URL("../assets/photos/chen_jialin.jpg", import.meta.url)
      //     .href,
      //   role: "Head TA",
      // },
      // {
      //   name: "Agastya Rana",
      //   image_src: new URL("../assets/photos/rana_agastya.jpg", import.meta.url)
      //     .href,
      //   role: "TA",
      // },
      // {
      //   name: "Yuhang Chen",
      //   image_src: new URL("../assets/photos/chen_yuhang.jpg", import.meta.url)
      //     .href,
      //   role: "TA",
      // },
      // {
      //   name: "Matt Soleimani",
      //   image_src: new URL("../assets/photos/soleimani_matt.png", import.meta.url)
      //     .href,
      //   role: "TA",
      // },
      // {
      //   name: "Meili Gupta",
      //   image_src: new URL("../assets/photos/gupta_meili.png", import.meta.url)
      //     .href,
      //   role: "ULA",
      // },
      // {
      //   name: "Weikang Qiu",
      //   image_src: new URL("../assets/photos/qiu_weikang.png", import.meta.url)
      //     .href,
      //   role: "Grader",
      // },
      {
        name: "Ngoc Bui",
        image_src: new URL("../assets/photos/ngoc_bui.jpg", import.meta.url)
          .href,
        role: "Teaching Assistant",
      },
      {
        name: "Rishabh Anand",
        image_src: new URL("../assets/photos/rishabh_anand.jpg", import.meta.url)
          .href,
        role: "Teaching Assistant",
        website: "https://rish-16.github.io/"
      },
      {
        name: "Leyao Wang",
        image_src: new URL("../assets/photos/leyao_wang.jpg", import.meta.url)
          .href,
        role: "Teaching Assistant",
        website: "https://lwang-laura.github.io/leyaowang.github.io/"
      },
      {
        name: "Harshit Verma",
        image_src: new URL("../assets/photos/harshit_verma.jpg", import.meta.url)
          .href,
        role: "Teaching Assistant",
      },
      {
        name: "Jeb Cui",
        image_src: new URL("../assets/photos/jeb_cui.png", import.meta.url)
          .href,
        role: "Undergraduate Learning Assistant",
        website: "https://jebcui.com/"
      },
      {
        name: "Felix Zou",
        image_src: new URL("../assets/photos/felix_zou.png", import.meta.url)
          .href,
        role: "Undergraduate Learning Assistant",
      },
    ],
  }),
});
</script>
