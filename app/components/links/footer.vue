<script setup>
const now = new Date();
const currentYear = now.getFullYear();
</script>

<template>
    <div class="xl:px-[15em] lg:px-[5em] px-[1em] md:py-[5em] py-[2em] pb-[2em] bg-[#C7C4B7]/50">
        <div class="flex flex-col md:flex-row gap-[1em] items-center md:justify-between md:items-start">
            <NuxtLink to="#home"
                class="flex flex-col w-1/3 items-center justify-center text-[#001f4e] hover:text-[#c59107] font-semibold">
                <img src="~/assets/images/icon-nobg.avif" alt="" width="200" class="transition-all duration-300">
                <div class='transition-opacity duration-300 px-[0.5em] opacity-100 text-center'>
                    <p class="text-[20pt] whitespace-nowrap">Murad United</p>
                    <p class="text-[15pt] whitespace-nowrap">General Contracting <br class="md:hidden"> & Trading Establishment</p>
                </div>
            </NuxtLink>
            <div class="w-1/3">
                <h5 class="font-[sansita] text-[#c59107] text-[20pt] text-center">Navigation</h5>
                <div class="flex flex-col gap-[0.5em] my-[1em] text-center text-[15pt]">
                    <NuxtLink class="hover:text-[#c59107]" exact to="#home">
                        Home</NuxtLink>
                    <NuxtLink class="hover:text-[#c59107]" exact to="#about">
                        About</NuxtLink>
                    <NuxtLink class="hover:text-[#c59107]" exact to="#services">
                        Services</NuxtLink>
                    <NuxtLink class="hover:text-[#c59107]" exact to="#values">
                        Values</NuxtLink>
                    <NuxtLink class="hover:text-[#c59107]" exact to="#contact">
                        Contact</NuxtLink>
                </div>
            </div>
            <div class="md:w-1/3">
                <h5 class="font-[sansita] text-[#c59107] text-[20pt] text-center md:text-start">About Us</h5>
                <div class="flex flex-col gap-[0.5em] items-center md:items-start text-[15pt]">
                    <p>We deliver certified, skilled construction personnel to support global projects, backed by 20+
                        years of experience with major clients like Saudi Aramco, Sabic, Maaden, SCECO, and Marafiq.</p>
                </div>
            </div>
        </div>

        <div class="mt-[2em]">
            <hr />
            <div class="flex mt-[1em] justify-between">
                <p>Copyright ©{{ currentYear }}. All Rights Reserved By <a href="/"
                        class="text-[#c59107] hover:text-[#001f4e] font-semibold">Murad United</a></p>
                <p>Designed & Developed By <a href="/" class="text-[#c59107] hover:text-[#001f4e] font-semibold">Adsaura
                        Production</a></p>
            </div>
        </div>
    </div>
</template>