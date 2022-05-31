<!-- <head>
<link
      rel="stylesheet"
      href="https://use.fontawesome.com/releases/v5.13.0/css/all.css"
      integrity="sha384-Bfad6CLCknfcloXFOyFnlgtENryhrpZCe29RTifKEixXQZ38WheV+i/6YWSzkz3V"
      crossorigin="anonymous"
    />
    </head> -->


<template>
  <div class="card">
    <div class="card-header p-0">
      <div class="tab__header">
        <a
          href="#"
          :class="['justify-between flex', active ? '' : '']"
          @click.prevent="active = !active"
        >
          <strong class="font-size-18 weight-800">{{ title }}</strong>
          <span
            v-show="!active"
            class="down-Arrow text-disabled font-size-24 "
          ><i class="fa fa-angle-down weight-400" /> </span>
          <span
            v-show="active"
            class="up-Arrow text-disabled font-size-24"
          ><i class="fa fa-angle-up weight-400" /></span>
        </a>
      </div>
    </div>
    <div>
      <div
        v-show="active"
        class="tab__content p-2"
      >
        <slot />
      </div>
    </div>
  </div>
</template>
<style scoped lang="scss">
@import "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.13.0/css/all.min.css";
    .card {
      padding:0 !important;
    }
    .font-size-24 {
    font-size: 24px;
}
    .tab__header {
        background: #fbfbfb;
    }

    .tab__header a {
        // color: $text !important;
        text-decoration: none;
        display: flex !important;
        line-height: 38px;

    }
    .tab__header a:hover,
    .tab__header a:focus {
        background-color: #deedf9;
    }

    .tab__header a strong {
        padding: 15px !important;

    }

    .tab__header .justify-between {
        justify-content: space-between !important;
    }

    .tab__header a:hover {

        text-decoration: none;
    }

    .tab__header .down-Arrow,
    .up-Arrow {
        border-left: 1px solid #ccc !important;
        padding: 15px 20px 15px 20px;
    }
    

    
</style>
<script>
export default {
	props:
        { title:
                {type:String, default:''
                },
        ariaExpanded:
                { type:Boolean, default:false
                },
        tab : {  type:String, default:'tab'}
        },
	data() {
		return { active:false,

		};
	},
	watch :{
	    active(val){
			localStorage.setItem(this.tab, val);
		}
	},
	mounted() {
	    let currentActive = localStorage.getItem(this.tab);
		this.active = currentActive ? (currentActive !== 'false') : this.ariaExpanded ;

	},
};
</script>
