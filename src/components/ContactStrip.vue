<template>
    <div class="bg-primarycolor py-2 px-4 sm:px-6 lg:px-8">
      <div class="max-w-7xl mx-auto flex justify-between items-center">
        <!-- Contact Info -->
        <div class="text-white font-medium">
          Get In Touch: +254 733 290 655
        </div>
        
        <!-- Social Icons -->
        <div class="flex items-center space-x-4">
          <span class="text-white hidden sm:inline">Follow Us:</span>
          <div class="flex space-x-3">
            <a href="#" class="text-[#1877F2] bg-white p-1 rounded-full hover:opacity-80 transition-opacity">
              <FacebookIcon class="h-4 w-4" />
            </a>
            <a href="#" class="text-[#1DA1F2] bg-white p-1 rounded-full hover:opacity-80 transition-opacity">
              <TwitterIcon class="h-4 w-4" />
            </a>
            <a href="#" class="text-[#0A66C2] bg-white p-1 rounded-full hover:opacity-80 transition-opacity">
              <LinkedinIcon class="h-4 w-4" />
            </a>
            <a href="#" class="text-[#E4405F] bg-white p-1 rounded-full hover:opacity-80 transition-opacity">
              <InstagramIcon class="h-4 w-4" />
            </a>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { FacebookIcon, TwitterIcon, LinkedinIcon, InstagramIcon } from 'lucide-vue-next';
  </script>