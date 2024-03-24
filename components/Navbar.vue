<template>
	<div class="flex justify-center items-center px-20 py-5">
		<a
			class="flex title-font font-medium items-center text-gray-900 mb-4 md:mb-0"
		>
			<span class="ml-3 text-xl">Tailblocks</span>
		</a>
		<nav
			class="md:ml-auto flex flex-wrap items-center text-base justify-center"
		>
			<NuxtLink class="mr-5 hover:text-gray-900" to="/">First Link</NuxtLink>
			<NuxtLink class="mr-5 hover:text-gray-900" to="/">First Link</NuxtLink>
			<NuxtLink class="mr-5 hover:text-gray-900" to="/">First Link</NuxtLink>
			<div class="relative group mr-5" @mouseover="dropdownOpen = true">
				<span class="cursor-pointer">Menu</span>
				<div
					class="absolute left-0 mt-2 w-48 rounded-md shadow-lg bg-white z-10"
					v-show="dropdownOpen"
					@mouseleave="dropdownOpen = false"
				>
					<ul class="py-1 rounded-md bg-white shadow-xs">
						<li v-for="(item, index) in items" :key="index">
							<NuxtLink
								:to="item.to"
								class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100"
								@click="dropdownOpen = false"
								>{{ item.label }}</NuxtLink
							>
						</li>
					</ul>
				</div>
			</div>
			<NuxtLink class="mr-5 hover:text-gray-900" to="/">First Link</NuxtLink>
		</nav>
	</div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const dropdownOpen = ref(false);
const items = [
	{
		label: 'Home',
		to: '/',
	},
	{
		label: 'About',
		to: '/about',
	},
	// Add more items as needed
];
</script>
