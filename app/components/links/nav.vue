<script setup>
const activeSection = ref('home')
const isMenuOpen = ref(false)

const handleScroll = () => {
    const sections = ['home', 'about', 'services', 'values', 'contact']

    for (const section of sections) {
        const element = document.getElementById(section)
        if (element) {
            const rect = element.getBoundingClientRect()
            if (rect.top <= 100 && rect.bottom >= 100) {
                activeSection.value = section
                break
            }
        }
    }
}

const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value
}

const navigateAndClose = (section) => {
    isMenuOpen.value = false
    document.getElementById(section)?.scrollIntoView({ behavior: 'smooth' })
}

onMounted(() => {
    window.addEventListener('scroll', handleScroll)
    handleScroll()
})

onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
    <div
        :class="['fixed w-[100%] z-1 transition-all duration-300 ease-in-out', activeSection !== 'home' ? 'lg:px-[12em] lg:top-[2em] top-[1.5em] px-[1em]' : 'lg:px-[6em] lg:top-[4em] top-[2em] px-[2em] ']">
        <div class="flex justify-between text-white">
            <NuxtLink to="#home"
                class="rounded-[1em] bg-[#001f4e] p-[0.5em] flex items-center transition-all duration-500 ease-in-out group">
                <img src="~/assets/images/icon.jpeg" alt="" width="80" height="80" class="rounded-[0.5em] shrink-0" />
                <p class=""
                    :class="['text-[12pt] companyname text-white whitespace-nowrap overflow-hidden transition-all duration-500 ease-in-out',
                        activeSection !== 'home' ? 'opacity-0 max-w-0 max-h-0 group-hover:opacity-100 group-hover:max-w-[400px] group-hover:max-h-[100px] group-hover:px-[1em]' : 'opacity-100 max-w-[400px] max-h-[100px] px-[1em]']">
                    Murad United General <br class="" /> <span class="hidden md:block">Contracting & Trading Establishment</span>
                </p>
            </NuxtLink>
            <div class="hidden md:flex items-center bg-[#001f4e] rounded-[1em] gap-[1em] px-[2em] text-[13pt]">
                <NuxtLink to="#home"
                    :class="['hover:text-[#c38d07]', activeSection === 'home' && 'text-[#c59107] font-bold']">
                    Home
                </NuxtLink>
                <NuxtLink to="#about"
                    :class="['hover:text-[#c38d07]', activeSection === 'about' && 'text-[#c59107] font-bold']">
                    About
                </NuxtLink>
                <NuxtLink to="#services" @click="navigateAndClose('services')"
                    :class="['hover:text-[#c38d07]', activeSection === 'services' && 'text-[#c59107] font-bold']">
                    Services
                </NuxtLink>
                <NuxtLink to="#values" @click="navigateAndClose('services')"
                    :class="['hover:text-[#c38d07]', activeSection === 'services' && 'text-[#c59107] font-bold']">
                    Values
                </NuxtLink>
                <NuxtLink to="#contact" @click="navigateAndClose('services')"
                    :class="['hover:text-[#c38d07]', activeSection === 'services' && 'text-[#c59107] font-bold']">
                    Contact
                </NuxtLink>
            </div>
            <button @click="toggleMenu"
                :class="['md:hidden flex items-center bg-[#001f4e] rounded-[1em] gap-[1em] px-[2em] text-[13pt]', activeSection === 'home' && 'hidden']"
                aria-label="Toggle menu" :aria-expanded="isMenuOpen">
                <p class="capitalize font-semibold">{{ activeSection }}</p>
                <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960" width="24px" fill="#fff"
                    :class="['transition-transform duration-300', isMenuOpen && 'rotate-180']">
                    <path d="M480-344 240-584l56-56 184 184 184-184 56 56-240 240Z" />
                </svg>
            </button>
            <Transition enter-active-class="transition-all duration-300 ease-out"
                enter-from-class="opacity-0 -translate-y-2" enter-to-class="opacity-100 translate-y-0"
                leave-active-class="transition-all duration-200 ease-in" leave-from-class="opacity-100 translate-y-0"
                leave-to-class="opacity-0 -translate-y-2">
                <div v-if="isMenuOpen" class="absolute top-full left-0 right-0 px-[2em] mt-2 md:hidden">
                    <div
                        class="bg-black/30 backdrop-blur-lg border border-[#C7C4B7] rounded-2xl overflow-hidden shadow-xl">
                        <NuxtLink to="#home" @click="navigateAndClose('home')" :class="[
                            'block px-6 py-4 text-white hover:bg-white/10 transition-colors border-b border-[#C7C4B7]/20',
                            activeSection === 'home' && 'bg-[#c59107]/20 text-[#c38d07] font-bold'
                        ]">
                            Home
                        </NuxtLink>
                        <NuxtLink to="#about" @click="navigateAndClose('about')" :class="[
                            'block px-6 py-4 text-white hover:bg-white/10 transition-colors border-b border-[#C7C4B7]/20',
                            activeSection === 'about' && 'bg-[#c59107]/20 text-[#c38d07] font-bold'
                        ]">
                            About
                        </NuxtLink>
                        <NuxtLink to="#services" @click="navigateAndClose('services')" :class="[
                            'block px-6 py-4 text-white hover:bg-white/10 transition-colors border-b border-[#C7C4B7]/20',
                            activeSection === 'services' && 'bg-[#c59107]/20 text-[#c38d07] font-bold'
                        ]">
                            Services
                        </NuxtLink>
                        <NuxtLink to="#values" @click="navigateAndClose('values')" :class="[
                            'block px-6 py-4 text-white hover:bg-white/10 transition-colors border-b border-[#C7C4B7]/20',
                            activeSection === 'values' && 'bg-[#c59107]/20 text-[#c38d07] font-bold'
                        ]">
                            Values
                        </NuxtLink>
                        <NuxtLink to="#contact" @click="navigateAndClose('contact')" :class="[
                            'block px-6 py-4 text-white hover:bg-white/10 transition-colors',
                            activeSection === 'contact' && 'bg-[#c59107]/20 text-[#c38d07] font-bold'
                        ]">
                            Contact
                        </NuxtLink>
                    </div>
                </div>
            </Transition>
        </div>


    </div>
</template>