<template>
  <header class="bg-white shadow-md">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center py-4">
        <!-- Logo -->
        <div class="flex-shrink-0">
          <a href="/" class="text-2xl font-bold text-gray-800 hover:text-indigo-600 transition duration-300 flex">
            <img :src="logo" alt="treyonks technology limited logo" class="h-10">
            <span class="text-2xl font-bold text-gray-800 hover:text-indigo-600 transition duration-300">Revlis Engineering Limited</span>
          </a>
        </div>

        <!-- Navigation for larger screens -->
        <nav class="hidden md:flex space-x-8">
          <a v-for="item in navItems" :key="item.name" :href="item.href"
             class="text-gray-600 hover:text-indigo-600 px-3 py-2 rounded-md text-sm font-medium transition duration-300 ease-in-out"
             :class="{ 'bg-indigo-100 text-indigo-700': item.current }"
          >
            {{ item.name }}
          </a>
        </nav>

        <!-- Search Icon -->
        <div class="hidden md:block">
          <button @click="openSearch" class="text-gray-600 hover:text-primary p-2 rounded-full transition duration-300 ease-in-out transform hover:scale-105 focus:outline-none focus:ring-2 focus:ring-primary focus:ring-opacity-50">
            <SearchIcon class="h-6 w-6" />
          </button>
        </div>

        <!-- Mobile menu button -->
        <div class="md:hidden">
          <button @click="toggleMobileMenu" class="text-gray-600 hover:text-indigo-600 focus:outline-none">
            <MenuIcon v-if="!isMobileMenuOpen" class="h-6 w-6" />
            <XIcon v-else class="h-6 w-6" />
          </button>
        </div>
      </div>

      <!-- Mobile menu -->
      <transition
        enter-active-class="transition duration-300 ease-out"
        enter-from-class="transform scale-95 opacity-0"
        enter-to-class="transform scale-100 opacity-100"
        leave-active-class="transition duration-200 ease-in"
        leave-from-class="transform scale-100 opacity-100"
        leave-to-class="transform scale-95 opacity-0"
      >
        <div v-if="isMobileMenuOpen" class="md:hidden">
          <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
            <a v-for="item in navItems" :key="item.name" :href="item.href"
               class="text-gray-600 hover:text-primary block px-3 py-2 rounded-md text-base font-medium"
               :class="{ 'bg-primary/10 text-primary': item.current }"
            >
              {{ item.name }}
            </a>
          </div>
        </div>
      </transition>
    </div>
  </header>
  <ContactStrip/>
</template>

<script setup>
import { ref } from 'vue';
import { MenuIcon, XIcon, SearchIcon } from 'lucide-vue-next';
import ContactStrip from './ContactStrip.vue';
import logo from "@/assets/logo.svg";
import { useRouter } from 'vue-router';

const router = useRouter();

const navItems = [
  { name: 'Home', href: '/', current: false },
  { name: 'About Us', href: '/about', current: false },
  { name: 'Services', href: '/services', current: false },
  { name: 'Contact Us', href: '/contact', current: false },
];

const isMobileMenuOpen = ref(false);

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};

const openSearch = () => {
  console.log('Search clicked');
};
</script>

<style scoped>
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(-10px); }
  to { opacity: 1; transform: translateY(0); }
}

header {
  animation: fadeIn 0.5s ease-out;
}

nav a, button {
  transition: all 0.3s ease;
}

nav a:hover, button:hover {
  transform: translateY(-2px);
}
</style>