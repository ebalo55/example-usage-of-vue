<template>
	<div class="relative w-full h-full">
		<nav class="fixed w-full grid grid-cols-4 md:grid-cols-12 p-2 bg-gray-100 shadow-lg">
			<a class="flex items-center justify-center md:col-start-3" href="/">
				<img src="@/assets/logo.svg" class="object-contain max-h-20">
			</a>
			<a class="items-center justify-center hidden md:flex transition-all duration-300 hover:bg-gray-200"
			   :class="assignColumnStart(elem)"
			   :href="elem.href"
			   v-for="(elem, id) of navigation"
			   :key="id">
				{{ elem.text }}
			</a>
			<div class="flex items-center justify-center md:hidden cursor-pointer col-start-4"
				@click="mobile_menu = true">
				<img src="@/assets/menu.svg" class="h-8">
			</div>
		</nav>
		<div class="p-4 w-full min-h-screen fixed z-50 right-0 top-0 transform-gpu transition-all duration-500 bg-gray-100"
			:class="mobileTranslation">
			<div class="flex">
				<a class="flex items-center justify-center p-2" href="/">
					<img src="@/assets/logo.svg" class="object-contain h-12">
				</a>
				<div class="flex items-center justify-center ml-auto p-3 cursor-pointer" @click="mobile_menu = false">
					<img src="@/assets/close.svg" class="h-5">
				</div>
			</div>
			<div class="mt-6 flex flex-col">
				<a class="w-full p-3 border-b transition-all duration-300 hover:bg-gray-200"
				   :class="assignColumnStart(elem)"
				   :href="elem.href"
				   v-for="(elem, id) of navigation"
				   :key="id">
					{{ elem.text }}
				</a>
			</div>
		</div>
		<main class="pt-24">
			<pre>
				<template v-for="(elem, id) of Array.from({length: 255}, (v,k) => k)" :key="id">
					{{ elem }}: {{ id }}
				</template>
			</pre>
		</main>
	</div>
</template>

<script>

export default {
	name: 'App',
	components: {},
	data: () => ({
		navigation: [
			{
				colStart: 5,
				text: "nav1",
				href: "#nav1"
			},
			{
				text: "nav2",
				href: "#nav2"
			},
			{
				text: "nav3",
				href: "#nav3"
			},
			{
				text: "nav4",
				href: "#nav4"
			},
			{
				text: "nav5",
				href: "#nav5"
			},
		],
		mobile_menu: false
	}),
	methods: {
		assignColumnStart(element) {
			switch (element.colStart) {
				case 1:
					return "col-start-1"
				case 2:
					return "col-start-2"
				case 3:
					return "col-start-3"
				case 4:
					return "col-start-4"
				case 5:
					return "col-start-5"
				case 6:
					return "col-start-6"
				case 7:
					return "col-start-7"
				case 8:
					return "col-start-8"
				case 9:
					return "col-start-9"
				case 10:
					return "col-start-10"
				case 11:
					return "col-start-11"
				case 12:
					return "col-start-12"
			}
		}
	},
	computed: {
		mobileTranslation() {
			return this.mobile_menu ? "translate-x-0 opacity-100" : "translate-x-full opacity-0"
		}
	},
}
</script>

<style>

</style>
