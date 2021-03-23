<template>
	<div>
		<Header/>
		<Introduction/>
		<State/>
		<DesktopMode/>
	</div>
</template>


<script>
import Header from "@/components/Header.vue";
import Introduction from "@/components/Introduction.vue";
import State from "@/components/State.vue";
import DesktopMode from "@/components/Desktop-mode.vue";

	export default {
		components: {
			Header,
			Introduction,
			State,
			DesktopMode,
		}
	}
</script>


<style lang="scss">

</style>
