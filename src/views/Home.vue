<template>
	<div>
		<Navbar v-if="isMobile === false"/>
		<MobileNav2 v-if="isMobile === true"/>
		<Header/>
		<Introduction/>
		<State/>
		<DesktopMode/>
		<Footer/>
	</div>
</template>


<script>
import Navbar from "@/components/Navbar.vue";
import MobileNav from "@/components/MobileNav.vue";
import MobileNav2 from "@/components/MobileNav2.vue";
import Header from "@/components/Header.vue";
import Introduction from "@/components/Introduction.vue";
import State from "@/components/State.vue";
import DesktopMode from "@/components/Desktop-mode.vue";
import Footer from "@/components/Footer.vue";

	export default {
		data() {
			return {
				isMobile : false,
        		showMobileMenu: false
    
			}
		},
		components: {
			MobileNav,
			MobileNav2,
			Navbar,
			Header,
			Introduction,
			State,
			DesktopMode,
			Footer
		},
		created() {
			window.addEventListener('resize', this.onWindowResize);
			this.onWindowResize();
		},
		methods: {
			onWindowResize(){
				if(window.innerWidth < 900){
					this.isMobile = true;
				}else {
					this.isMobile = false;
				}
			}
		}
	}
</script>


<style lang="scss">
  	@import '../scss/main.scss';
</style>
