<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
	  <router-link to="/goods">Goods</router-link> |
	  <router-link to="/show">Show</router-link> |
	  <router-link to="/user">用户</router-link> |
	  <router-link to="/daily">日报</router-link> |
	   <router-link to="/keep">keep</router-link> |
	  <!-- <router-link to="/User1">user1</router-link> | -->
	 <!-- <router-link :to="u">user1</router-link> -->
	 <router-link to="/User1/10">user1</router-link> |
	 <router-link to="/User1/222">user2</router-link> |
	 <router-link :to="u2">user3</router-link> |
	 <button @click="$router.push('/User1/55').catch(err=>{})">user5</button> |
	 <button @click="$router.replace('/User1/66').catch(err=>{})">user6</button> |
	 <button @click="$router.push({name:'user1',params:{page:77}})">user7</button> |
	 <button @click="btn1">user8</button>
	 <router-link to="/message">message</router-link>
	 
    </div>
	<transition name="fade">
		<router-view/>
	</transition>
	<mu-container>
	  <mu-bottom-nav>
	    <mu-bottom-nav-item title="Recents" icon="restore"></mu-bottom-nav-item>
	    <mu-bottom-nav-item title="Favorites" icon="favorite"></mu-bottom-nav-item>
	    <mu-bottom-nav-item title="Nearby" icon="location_on"></mu-bottom-nav-item>
	  </mu-bottom-nav>
	</mu-container>
  </div>
</template>
<script>
	export default{
		data(){
			return{
				btn:"info",
				u:"/User1",
				u2:"/User1/33"
			}
		},
		methods:{
			btn1(){
				this.$router.push('/User1/88');//点击按钮组件跳转
			}
		},
	}
</script>
<style lang="scss">
	.fade-enter-active, .fade-leave-active {
	  transition: opacity .5s;
	}
	.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
	  opacity: 0;
	}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

</style>
