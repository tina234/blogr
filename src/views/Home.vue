<template>
	<div>
		<Header/>
		<Introduction/>
		<State/>
		<DesktopMode/>
		<Footer/>
	</div>
</template>


<script>
import Header from "@/components/Header.vue";
import Introduction from "@/components/Introduction.vue";
import State from "@/components/State.vue";
import DesktopMode from "@/components/Desktop-mode.vue";
import Footer from "@/components/Footer.vue";

	export default {
		components: {
			Header,
			Introduction,
			State,
			DesktopMode,
			Footer
		}
	}
</script>


<style lang="scss">

</style>
