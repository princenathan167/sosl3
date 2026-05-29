<script setup>
import contactImg from '../assets/bg.jpg'
</script>

<template>
	<main class="page">
		<div class="rounded-[2rem] bg-white border border-emerald-100 shadow-2xl p-8 grid gap-10 lg:grid-cols-[1fr_1.1fr] items-center">
			<div>
				<h1 class="text-4xl font-bold text-green-700 mb-4">Contact Us</h1>
				<p class="text-lg text-gray-800 mb-6">
					For inquiries, bookings, or custom itineraries, email us at info@rwanda-explorer.example or use the contact details below.
				</p>
				<div class="space-y-4">
					<div class="rounded-3xl bg-emerald-50 p-6 shadow-sm border border-emerald-100">
						<span class="text-sm uppercase tracking-[0.35em] text-emerald-700">Email</span>
						<p class="text-gray-700 mt-2">info@rwanda-explorer.example</p>
					</div>
					<div class="rounded-3xl bg-emerald-50 p-6 shadow-sm border border-emerald-100">
						<span class="text-sm uppercase tracking-[0.35em] text-emerald-700">Response time</span>
						<p class="text-gray-700 mt-2">We usually respond within 24 hours and can help you plan the perfect Rwanda journey.</p>
					</div>
				</div>
			</div>
			<div class="rounded-[2rem] overflow-hidden shadow-xl border border-emerald-100">
				<img :src="contactImg" alt="Contact Rwanda Explorer" class="w-full h-96 object-cover" />
			</div>
		</div>
	</main>
</template>