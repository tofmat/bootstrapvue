<template>
  <b-col md="3">
          <b-card
          :title="name" 
          img-src="https://picsum.photos/600/300/?image=25"
          img-alt="Job"
          img-top
          tag='article'
          style="max-width:20rem"
          class="mb-2"
          footer="This is a footer"
          >
            <b-card-text>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quo cupiditate eius soluta placeat, assumenda consequuntur nisi perferendis beatae, doloremque debitis nulla libero iste sit officiis. Nostrum voluptas deserunt at sed.
            </b-card-text>
            <b-button variant="primary">Apply</b-button>
           </b-card>
        </b-col>
</template>

<script>
export default {
    props: ["name"]
}
</script>

<style>

</style>