<template>
  <!-- Default list Item-->
  <div class="d-flex justify-content-center">
    <div class="text h4 mt-4">
    This is the call to the component v-list-item without any slots and without any props.<br />
    So, the default values will appear as:
    <ul>
      <li>Avatar</li>
      <li>Title</li>
      <li>Description</li>
      <li>Sub Description</li>
      <li>Action</li>
    </ul>
  </div>
</div>
  <v-list-item />
  <br />
  <hr />

  <!--List Item With Full props and slots-->
  <div class="d-flex justify-content-center">
  <div class="text h4">
    This is the call to the component v-list-item with slots and props.<br />
    The values will appear as avatar, title, description, sub description, and action.<br />
    If any data is not provided, it will not appear.<br />
    <br />
    The props are:
    <ul>
      <li>color (left border color)</li>
      <li>border (true or false, if you want to show the left border)</li>
      <li>disabled (boolean)</li>
    </ul>
    The slots are:
    <ul>
      <li>#title</li>
      <li>#logo (send image or avatar)</li>
      <li>#desc</li>
      <li>#subDesc</li>
      <li>#action</li>
    </ul>
  </div>
</div>

  <v-list-item :color="'blue'" :border="true" :disabled="false">
    <template #title>Mohammad Aljamal</template>
    <template #logo
      ><img
        src="https://s3.eu-central-1.amazonaws.com/elciqlo-production-public/users/483189/pictures/84D-F441ACF4D06F.jpg"
        alt="Logo"
        class="avatar"
    /></template>
    <template #desc>Front-End Developer</template>
    <template #subDesc>2001/02/11</template>
    <template #action>This is Action Area</template>
  </v-list-item>
  <br />
  <hr />

  <!--List Item With non-Full props and slots-->
  <div class="d-flex justify-content-center h4">
    Multi Examples for using the list item : <br/>
  </div>
  <div class="d-flex justify-content-center h4">
    1 -sent just title slot <br/>
  </div>
  <v-list-item> <template #title>Mohammad Aljamal</template> </v-list-item><br />
  <div class="d-flex justify-content-center h4">
    2 -sent title and action slot <br/>
  </div>
  <v-list-item>
    <template #title>Mohammad Aljamal</template>
    <template #action
      ><span class="badge bg-primary rounded-pill">2001/02/11</span></template
    > </v-list-item
  ><br />
  <div class="d-flex justify-content-center h4">
    3 -sent title and logo slots with props(border : true - color : red)<br/>
  </div>
  <v-list-item :border="true" :color="'red'">
    <template #title>Mohammad Aljamal</template>
    <template #logo
      ><img
        src="https://s3.eu-central-1.amazonaws.com/elciqlo-production-public/users/483189/pictures/84D-F441ACF4D06F.jpg"
        alt="Logo"
        class="avatar"
    /></template> </v-list-item
  ><br />
  <div class="d-flex justify-content-center h4">
    4 -sent title, logo, action slots with props(border : true - color : blue)<br/>
  </div>
  <v-list-item :color="'blue'" :border="true">
    <template #title>Mohammad Aljamal</template>
    <template #logo
      ><img
        src="https://s3.eu-central-1.amazonaws.com/elciqlo-production-public/users/483189/pictures/84D-F441ACF4D06F.jpg"
        alt="Logo"
        class="avatar"
    /></template>
    <template #action
      ><span class="badge bg-primary rounded-pill">Front-End</span></template
    > </v-list-item
  ><br />
  <div class="d-flex justify-content-center h4">
    5 -sent title, logo, action, description slots with props(border : true - color : blue)<br/>
  </div>
  <v-list-item :color="'blue'" :border="true">
    <template #title>Mohammad Aljamal</template>
    <template #logo
      ><img
        src="https://s3.eu-central-1.amazonaws.com/elciqlo-production-public/users/483189/pictures/84D-F441ACF4D06F.jpg"
        alt="Logo"
        class="avatar"
    /></template>
    <template #desc>Front-End Developer</template>
    <template #action
      ><span class="badge bg-primary rounded-pill">Front-End</span></template
    > </v-list-item
  ><br />
  <div class="d-flex justify-content-center h4">
    6 -sent title, logo, action, description slots with props(border : true - color : yellow - disabled : true)<br/>
  </div>
  <v-list-item :color="'yellow'" :border="true" :disabled="true">
    <template #title>Mohammad Aljamal</template>
    <template #logo
      ><img
        src="https://s3.eu-central-1.amazonaws.com/elciqlo-production-public/users/483189/pictures/84D-F441ACF4D06F.jpg"
        alt="Logo"
        class="avatar"
    /></template>
    <template #desc>Front-End Developer</template>
    <template #action
      ><span class="badge bg-primary rounded-pill">Front-End</span></template
    > </v-list-item
  ><br />
  <div class="d-flex justify-content-center h4">
    7 -sent title, logo, action, description, sub description slots with props(border : true - color : green - disabled : true)<br/>
  </div>
  <v-list-item :color="'green'" :border="true">
    <template #title>Mohammad Aljamal</template>
    <template #logo
      ><img
        src="https://s3.eu-central-1.amazonaws.com/elciqlo-production-public/users/483189/pictures/84D-F441ACF4D06F.jpg"
        alt="Logo"
        class="avatar"
    /></template>
    <template #desc>Front-End Developer</template>
    <template #subDesc>Cubes Platform .Inc</template>
    <template #action
      ><span class="badge bg-warning rounded-pill">1 month</span></template
    > </v-list-item
  ><br />

  <hr />
  <div class="d-flex justify-content-center h4">
    <div class="text h4">
    If you want to display the list in a list group, just call the <strong>v-list-group</strong> component.<br />
    Send the props that define the list of items you want to show:<br />
    <strong>:list='your lists data name'</strong> and the list data should contain:
    <ul>
        <li>Header</li>
        <li>Items:
            <ul>
                <li>Logo</li>
                <li>Title</li>
                <li>Description</li>
                <li>Action</li>
                <li>Sub Description</li>
                <li>Border (boolean)</li>
                <li>Color (red,green,blue,yellow and so on)</li>
                <li>Disabled (boolean)</li>
            </ul>
        </li>
    </ul>
    </div>
</div>


  <!-- List Group -->
  <template v-for="list in lists" :key="list.header">
    <v-list-group :list="list"></v-list-group>
  </template>
</template>

<script setup lang="ts">
import { ref } from "vue";
import VListGroup from "@/components/listGroup.vue";
import VListItem from "@/components/listItem.vue";
const lists = ref([
  {
    header: "Barcelona Players",
    items: [
      {
        logo: "https://fcb-abj-pre.s3.amazonaws.com/img/jugadors/MESSI.jpg",
        title: "Lionel Messi",
        desc: "Considered the greatest player of all time with 8 Ballon d'Or wins.",
        action: "1",
        subDesc: "Famous for his dribbling, playmaking, and finishing abilities.",
        border: true,
        color: "red",
        disabled: false,
      },
      {
        logo: "https://fcb-abj-pre.s3.amazonaws.com/img/jugadors/INIESTA%202017-18.jpg",
        title: "Andrés Iniesta",
        desc: "Midfield maestro known for his vision, control, and passing.",
        action: "1",
        subDesc: "Key figure in Barcelona's golden era and Spain's World Cup win.",
        border: true,
        color: "yellow",
        disabled: false,
      },
      {
        logo: "https://fcb-abj-pre.s3.amazonaws.com/img/jugadors/763_ronaldinho.jpg",
        title: "Ronaldinho",
        desc:
          "Known for his flair, tricks, and joyful playstyle that dazzled fans worldwide.",
        action: "3",
        subDesc:
          "Helped Barcelona return to winning ways, lifting multiple La Liga and Champions League titles.",
        border: true,
        color: "blue",
        disabled: true,
      },
      {
        logo:
          "https://cdn.bleacherreport.net/images_root/slides/photos/000/629/010/108096092_original.jpg?1295306079",
        title: "Xavi Hernández",
        desc:
          "A legendary playmaker, known for his passing accuracy and tactical intelligence.",
        action: "1",
        subDesc:
          "Central to Barcelona's tiki-taka style of play and their numerous successes.",
        border: false,
        color: "green",
        disabled: false,
      },
    ],
  },
  {
    header: "Real Madrid Players",
    items: [
      {
        logo:
          "https://upload.wikimedia.org/wikipedia/commons/8/8c/Cristiano_Ronaldo_2018.jpg",
        title: "Cristiano Ronaldo",
        desc: "One of the most famous footballers in history, with 5 Ballon d'Or titles.",
        action: "3",
        subDesc: "Known for his goal-scoring prowess and incredible athleticism.",
        border: true,
        color: "red",
        disabled: false,
      },
      {
        logo:
          "http://soccer-europe.com/images/Zinedine_Zidane_copyright_sportige_com.jpg",
        title: "Zinedine Zidane",
        desc: "A football legend, known for his elegance, vision, and technical skill.",
        action: "2",
        subDesc:
          "Led Real Madrid to multiple Champions League titles, both as a player and coach.",
        border: true,
        color: "yellow",
        disabled: false,
      },
      {
        logo:
          "https://upload.wikimedia.org/wikipedia/commons/thumb/e/e2/Raul_Gonzalez_10mar2007.jpg/375px-Raul_Gonzalez_10mar2007.jpg",
        title: "Raúl González",
        desc:
          "An iconic forward, known for his loyalty and goal-scoring consistency at Real Madrid.",
        action: "2",
        subDesc:
          "One of the club's all-time top scorers, with numerous La Liga and Champions League titles.",
        border: true,
        color: "blue",
        disabled: true,
      },
      {
        logo:
          "https://publish-p47754-e237306.adobeaemcloud.com/adobe/dynamicmedia/deliver/dm-aid--077a0344-869c-4e0c-ae38-163cd1c92fc7/_330347659219.app.webp?preferwebp=true&width=312",
        title: "Iker Casillas",
        desc:
          "Legendary goalkeeper, captain, and key figure for both Real Madrid and Spain.",
        action: "2",
        subDesc: "Known for his quick reflexes, leadership, and shot-stopping ability.",
        border: false,
        color: "green",
        disabled: false,
      },
    ],
  },
]);
</script>
<style scoped></style>
