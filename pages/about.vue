<template>
  <v-layout column justify-center align-center>
    <v-flex class="text-center" style="width: 650px">
      <v-sheet class="my-10">
        <p class="display-3 text--primary">About MFI Calculator</p>
        <v-img
          class="my-5"
          lazy-src="https://picsum.photos/id/11/100/60"
          src="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQuYTd6uR42vKMStMcNargUxe5tlg-ukiainbUrsdWdAzDtX3gs"
        >
          <template v-slot:placeholder>
            <v-row class="fill-height ma-0" align="center" justify="center">
              <v-progress-circular
                indeterminate
                color="grey lighten-5"
              ></v-progress-circular>
            </v-row> </template
        ></v-img>
        <p class="body-1 text--primary">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Corrupti
          libero est ratione expedita ducimus nisi inventore, ad ipsam repellat
          illum dolorem odit, qui nihil asperiores? Blanditiis odio aspernatur
          laudantium vel!
        </p>
        <p class="body-1 text--primary">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Corrupti
          libero est ratione expedita ducimus nisi inventore, ad ipsam repellat
          illum dolorem odit, qui nihil asperiores? Blanditiis odio aspernatur
          laudantium vel!
        </p>
        <p class="body-1 text--primary">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Corrupti
          libero est ratione expedita ducimus nisi inventore, ad ipsam repellat
          illum dolorem odit, qui nihil asperiores? Blanditiis odio aspernatur
          laudantium vel!
        </p>
      </v-sheet>
    </v-flex>
  </v-layout>
</template>

<style scoped>
.v-image {
  max-height: 600px;
  max-width: 600px;
  margin: auto;
  border-radius: 10%;
}
</style>
