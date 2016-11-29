<template>
  <div class="ratings">
    <div class="rating" v-for="n in max">
      <i class="fa fa-star" v-on:mouseover="star_over(n)" v-on:mouseout="star_out" v-on:click.stop.prevent="star_selected(n)" :class="{'active' : (overwritten_value >= n)}"></i>
    </div>
    <div class="search-input" v-if="!disabled">
      <select v-bind:name="s_name">
        <option v-for="n in max" v-bind:selected="overwritten_value==n" v-bind:value="n" v-text="n">1</option>
      </select>
    </div>
  </div>
</template>
<script>
    export default {
      data:function () {
        return {
          is_selected:true,
          overwritten_value:this.value
        }
      },
      props: {
        max: Number,
        value: Number,
        disabled: Boolean,
        s_name: String,
        icon: {
          type:String,
          default: "fa fa-star"
        }
      },
      ready:function() {
        console.log('Component ready.')
      },
      watch: {
        overwritten_value:function(){
          this.selected_value = false;
        }
      },
      methods: {
        star_over: function(index){
          if (this.disabled!=true) {
            this.temp_value = this.overwritten_value;
            this.overwritten_value = index;
          }
        },
        star_out: function(){
          if (this.disabled!=true && this.selected_value!=true) {
            this.overwritten_value = this.temp_value;
          }
        },
        star_selected: function(value){
          if (this.disabled!=true) {
            this.selected_value = true;
            this.overwritten_value = value;
          }
        }
      }
    }
</script>

