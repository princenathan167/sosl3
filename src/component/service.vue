<script setup>
// Changed from ../../ to ../
import serviceImg from '../assets/service.jpg'
</script>

<template>
	<main class="page">
		<div class="rounded-[2rem] bg-white border border-emerald-100 shadow-2xl p-8 grid gap-10 lg:grid-cols-[1.4fr_1fr] items-center">
			<section class="space-y-6">
				<p class="text-sm uppercase tracking-[0.35em] text-emerald-700">Our services</p>
				<h1 class="text-4xl font-bold text-slate-900">Travel support you can count on.</h1>
				<p class="text-lg text-slate-700 leading-relaxed">
					We prioritize sustainable partners and authentic experiences—reach out to tailor services to your travel style and dates.
				</p>
				<div class="grid gap-4">
					<div class="rounded-3xl bg-emerald-50 p-6 shadow-sm border border-emerald-100">
						<h2 class="text-xl font-semibold text-green-700 mb-2">Guided tours</h2>
						<p class="text-gray-600">Local experts lead hikes, wildlife visits, and cultural walks with personal care.</p>
					</div>
					<div class="rounded-3xl bg-emerald-50 p-6 shadow-sm border border-emerald-100">
						<h2 class="text-xl font-semibold text-green-700 mb-2">Wildlife excursions</h2>
						<p class="text-gray-600">Arrange memorable experiences like gorilla trekking, bird watching, and safari days.</p>
					</div>
					<div class="rounded-3xl bg-emerald-50 p-6 shadow-sm border border-emerald-100">
						<h2 class="text-xl font-semibold text-green-700 mb-2">Cultural experiences</h2>
						<p class="text-gray-600">Connect with communities, traditions, and authentic local stories.</p>
					</div>
				</div>
			</section>
			<div class="rounded-[2rem] overflow-hidden shadow-xl border border-emerald-100">
				<img :src="serviceImg" alt="Travel services" class="w-full h-96 object-cover" />
			</div>
		</div>
	</main>
</template>
