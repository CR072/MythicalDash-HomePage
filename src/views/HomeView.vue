<template>
  <div class="min-h-screen bg-[#151329] text-gray-300">
    <!-- Navigation -->
    <nav class="bg-[#1E1B2E] bg-opacity-80 backdrop-filter backdrop-blur-lg fixed w-full z-10">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex items-center justify-between h-16">
          <div class="flex items-center">
            <a href="#" class="flex-shrink-0">
              <ServerIcon class="h-8 w-8 text-purple-400" />
            </a>
            <div class="hidden md:block">
              <div class="ml-10 flex items-baseline space-x-4">
                <a
                  href="/"
                  class="px-3 py-2 rounded-md text-sm font-medium text-white bg-purple-900 bg-opacity-50"
                  >Home</a
                >
                <a
                  target="_blank"
                  href="https://discord.mythical.systems"
                  class="px-3 py-2 rounded-md text-sm font-medium hover:bg-purple-900 hover:bg-opacity-30 transition-colors"
                  >Discord</a
                >
                <a
                  href="https://github.com/MythicalLTD/MythicalDash"
                  target="_blank"
                  class="px-3 py-2 rounded-md text-sm font-medium hover:bg-purple-900 hover:bg-opacity-30 transition-colors"
                  >Github</a
                >
                <a
                  href="https://www.mythical.systems/docs/mythicalclient-v4/welcome"
                  target="_blank"
                  class="px-3 py-2 rounded-md text-sm font-medium hover:bg-purple-900 hover:bg-opacity-30 transition-colors"
                  >Docs</a
                >
              </div>
            </div>
          </div>
          <div class="hidden md:block">
            <div class="ml-4 flex items-center md:ml-6">
              <a
                href="https://www.mythical.systems/docs/mythicalclient-v4/welcome"
                target="_blank"
                class="bg-purple-600 hover:bg-purple-700 text-white px-4 py-2 rounded-md text-sm font-medium transition-colors"
                >Get Started</a
              >
            </div>
          </div>
          <div class="-mr-2 flex md:hidden">
            <button
              type="button"
              class="bg-purple-900 bg-opacity-50 inline-flex items-center justify-center p-2 rounded-md text-purple-400 hover:text-white hover:bg-purple-800 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-purple-800 focus:ring-white"
            >
              <span class="sr-only">Open main menu</span>
              <MenuIcon class="h-6 w-6" aria-hidden="true" />
            </button>
          </div>
        </div>
      </div>
    </nav>

    <!-- Hero Section (enhanced with image) -->
    <header class="pt-24 pb-16 px-4 sm:px-6 lg:px-8 bg-gradient-to-b from-[#1E1B2E] to-[#151329]">
      <div class="max-w-7xl mx-auto flex flex-col lg:flex-row items-center">
        <div class="lg:w-1/2 mb-8 lg:mb-0">
          <h1 class="text-4xl sm:text-5xl font-bold text-white mb-4 animate-fade-in-up">
            Welcome to MythicalClient
          </h1>
          <p class="text-xl sm:text-2xl text-gray-300 mb-8 animate-fade-in-up animation-delay-200">
            Empower your hosting business with our cutting-edge
            <span class="typing-animation" id="hosting_type"></span> solution
          </p>
          <a
            href="https://www.mythical.systems/docs/mythicalclient-v4/welcome"
            target="_blank"
            class="inline-flex items-center px-6 py-3 border border-transparent text-base font-medium rounded-md text-white bg-purple-600 hover:bg-purple-700 transition-colors animate-fade-in-up animation-delay-400"
          >
            Get Started
            <ArrowRightIcon class="ml-2 -mr-1 h-5 w-5" aria-hidden="true" />
          </a>
        </div>
        <div class="lg:w-1/2 animate-float">
          <img
            src="https://i.mythical.systems/storage/uploads/1738160250.png?height=400&width=600"
            alt="MythicalClient Dashboard Preview"
            class="rounded-lg shadow-2xl"
          />
        </div>
      </div>
    </header>

    <!-- Countdown Timer -->
    <section class="py-12 px-4 sm:px-6 lg:px-8">
      <div class="max-w-7xl mx-auto text-center">
        <h2 class="text-3xl font-bold text-white mb-4 animate-fade-in-up">Launching Soon</h2>
        <p class="text-xl text-gray-300 mb-8 animate-fade-in-up animation-delay-200">
          Get ready for the next generation of hosting management
        </p>
        <div class="flex justify-center space-x-4 animate-fade-in-up animation-delay-400">
          <div
            v-for="(value, unit) in countdown"
            :key="unit"
            class="bg-purple-900 bg-opacity-50 rounded-lg p-4 w-24"
          >
            <div class="text-4xl font-bold text-white">{{ value }}</div>
            <div class="text-sm text-gray-400">{{ unit }}</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Feature Highlights (enhanced animations) -->
    <section class="py-16 px-4 sm:px-6 lg:px-8">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-3xl font-bold text-white mb-8 text-center animate-fade-in-up">
          Powerful Features
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div
            v-for="(feature, index) in features"
            :key="feature.title"
            class="bg-[#1E1B2E] bg-opacity-60 backdrop-filter backdrop-blur-lg rounded-lg p-6 hover:bg-opacity-80 transition-all duration-300 animate-fade-in-up hover:scale-105"
            :style="{ animationDelay: `${index * 200}ms` }"
          >
            <component :is="feature.icon" class="h-10 w-10 text-purple-400 mb-4" />
            <h3 class="text-xl font-semibold text-white mb-2">{{ feature.title }}</h3>
            <p class="text-gray-400">{{ feature.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Product Preview -->
    <section class="py-16 px-4 sm:px-6 lg:px-8 bg-[#1E1B2E] bg-opacity-30">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-3xl font-bold text-white mb-8 text-center animate-fade-in-up">
          See MythicalClient in Action
        </h2>
        <p class="text-center text-gray-400 mb-8 animate-fade-in-up animation-delay-200">
          Take a look at some of the key features of our clients futures
        </p>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <div
            v-for="(preview, index) in productPreviews"
            :key="preview.title"
            class="bg-[#252236] rounded-lg p-6 animate-fade-in-up hover:shadow-lg transition-all duration-300"
            :style="{ animationDelay: `${index * 200}ms` }"
          >
            <img
              :src="preview.image"
              :alt="preview.title"
              class="w-full h-auto rounded-lg mb-4 animate-float"
            />
            <h3 class="text-xl font-semibold text-white mb-2">{{ preview.title }}</h3>
            <p class="text-gray-400">{{ preview.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Comparison Table -->
    <section class="py-16 px-4 sm:px-6 lg:px-8">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-3xl font-bold text-white mb-8 text-center animate-fade-in-up">
          How We Compare
        </h2>
        <p class="text-center text-gray-400 mb-8 animate-fade-in-up animation-delay-200">
          See how MythicalClient stacks up against the competition.
        </p>
        <div class="overflow-x-auto animate-fade-in-up animation-delay-200">
          <table class="w-full text-left border-collapse">
            <thead>
              <tr class="bg-purple-900 bg-opacity-50">
                <th class="p-3 border border-gray-700">Feature</th>
                <th class="p-3 border border-gray-700">MythicalClient</th>
                <th class="p-3 border border-gray-700">WHMCS</th>
                <th class="p-3 border border-gray-700">Paymenter</th>
                <th class="p-3 border border-gray-700">HolaClient</th>
              </tr>
            </thead>
            <tbody>
              <tr
                v-for="(feature, index) in comparisonFeatures"
                :key="feature.name"
                :class="index % 2 === 0 ? 'bg-[#1E1B2E]' : 'bg-[#252236]'"
                class="animate-fade-in-up hover:bg-purple-900 hover:bg-opacity-30 transition-colors"
              >
                <td class="p-3 border border-gray-700">{{ feature.name }}</td>
                <td
                  class="p-3 border border-gray-700"
                  v-for="product in ['mythicalClient', 'whmcs', 'paymenter', 'holaclient']"
                  :key="product"
                >
                  <CheckIcon
                    v-if="feature[product as keyof typeof feature]"
                    class="h-5 w-5 text-green-400"
                  />
                  <XIcon v-else class="h-5 w-5 text-red-400" />
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </section>

    <!-- Pricing Plans (enhanced animations) -->
    <section class="py-16 px-4 sm:px-6 lg:px-8 bg-[#1E1B2E] bg-opacity-30">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-3xl font-bold text-white mb-8 text-center animate-fade-in-up">
          Flexible Pricing Plans
        </h2>
        <p class="text-center text-gray-400 mb-8 animate-fade-in-up animation-delay-200">
          Choose the plan that best suits your needs.
        </p>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div
            v-for="(plan, index) in pricingPlans"
            :key="plan.title"
            class="bg-[#252236] rounded-lg p-6 flex flex-col animate-fade-in-up hover:shadow-lg transition-all duration-300"
            :class="{ 'border-2 border-purple-500': plan.popular }"
            :style="{ animationDelay: `${index * 200}ms` }"
          >
            <h3 class="text-2xl font-bold text-white mb-4">{{ plan.title }}</h3>
            <p class="text-4xl font-bold text-white mb-6">
              {{ plan.price }}€<span class="text-xl font-normal text-gray-400">/mo</span>
            </p>
            <ul class="mb-8 flex-grow">
              <li v-for="feature in plan.features" :key="feature" class="flex items-center mb-2">
                <CheckIcon class="h-5 w-5 text-green-400 mr-2" />
                <span>{{ feature }}</span>
              </li>
            </ul>
            <a
              :href="plan.link"
              class="bg-purple-600 text-white px-4 py-2 rounded-md text-center hover:bg-purple-700 transition-colors transform hover:scale-105"
              >{{ plan.button }}</a
            >
          </div>
        </div>
      </div>
    </section>

    <!-- Testimonials (enhanced animations) -->
    <section class="py-16 px-4 sm:px-6 lg:px-8">
      <div class="max-w-7xl mx-auto">
        <h2 class="text-3xl font-bold text-white mb-8 text-center animate-fade-in-up">
          What Our Clients Say
        </h2>
        <p class="text-center text-gray-400 mb-8 animate-fade-in-up animation-delay-200">
          Hear from some of our satisfied clients.
        </p>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div
            v-for="(testimonial, index) in testimonials"
            :key="testimonial.name"
            class="bg-[#1E1B2E] bg-opacity-60 backdrop-filter backdrop-blur-lg rounded-lg p-6 animate-fade-in-up hover:shadow-lg transition-all duration-300"
            :style="{ animationDelay: `${index * 200}ms` }"
          >
            <p class="text-gray-300 mb-4">"{{ testimonial.quote }}"</p>
            <div class="flex items-center">
              <img
                :src="testimonial.avatar"
                :alt="testimonial.name"
                class="h-10 w-10 rounded-full mr-3"
              />
              <div>
                <p class="text-white font-semibold">{{ testimonial.name }}</p>
                <p class="text-gray-400 text-sm">{{ testimonial.company }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Call to Action (enhanced animations) -->
    <section class="py-16 px-4 sm:px-6 lg:px-8 bg-gradient-to-b from-[#1E1B2E] to-[#151329]">
      <div class="max-w-3xl mx-auto text-center">
        <h2 class="text-3xl font-bold text-white mb-4 animate-fade-in-up">Ready to Get Started?</h2>
        <p class="text-xl text-gray-300 mb-8 animate-fade-in-up animation-delay-200">
          Join thousands of satisfied clients and take your hosting business to the next level.
        </p>
        <a
          href="https://www.mythical.systems/docs/mythicalclient-v4/welcome/"
          class="inline-flex items-center px-6 py-3 border border-transparent text-base font-medium rounded-md text-purple-900 bg-purple-100 hover:bg-purple-200 transition-colors animate-fade-in-up animation-delay-400 transform hover:scale-105"
        >
          Start Your Adventure!
          <ArrowRightIcon class="ml-2 -mr-1 h-5 w-5" aria-hidden="true" />
        </a>
      </div>
    </section>

    <!-- Footer -->
    <footer
      class="bg-[#1E1B2E] bg-opacity-80 backdrop-filter backdrop-blur-lg py-12 px-4 sm:px-6 lg:px-8"
    >
      <p class="text-center text-gray-400">
        Copyright &copy; 2020 - {{ new Date().getFullYear() }}
        <a
          href="https://mythical.systems"
          class="text-purple-400 hover:text-purple-600 transition-colors"
          >MythicalSystems</a
        >. All rights reserved.
      </p>
    </footer>
  </div>
</template>

<script setup lang="ts">
import {
  ServerIcon,
  MenuIcon,
  ArrowRightIcon,
  CheckIcon,
  XIcon,
  ShieldIcon,
  CreditCardIcon,
  UsersIcon,
} from 'lucide-vue-next'

document.title = 'MythicalClient - The Ultimate Hosting Solution'

import { ref, onMounted } from 'vue'

const hostingType = ref('')
const types = ['VPS Hosting', 'WebHosting', 'Bare Metal', 'Game Hosting']
let typeIndex = 0
let charIndex = 0

function typeNext() {
  if (charIndex < types[typeIndex].length) {
    hostingType.value += types[typeIndex].charAt(charIndex)
    charIndex++
    setTimeout(typeNext, 100)
  } else {
    setTimeout(() => {
      hostingType.value = ''
      charIndex = 0
      typeIndex = (typeIndex + 1) % types.length
      typeNext()
    }, 2000)
  }
}

onMounted(() => {
  typeNext()
  calculateTimeLeft()
  timer = setInterval(calculateTimeLeft, 1000)
})

const features = [
  {
    icon: ShieldIcon,
    title: 'Advanced Security',
    description: "Protect your clients' data with our state-of-the-art security measures.",
  },
  {
    icon: CreditCardIcon,
    title: 'Automated Billing',
    description: 'Streamline your revenue with our powerful automated billing system.',
  },
  {
    icon: UsersIcon,
    title: 'Client Management',
    description: 'Efficiently manage your clients with our intuitive management tools.',
  },
]

const productPreviews = [
  {
    title: 'Intuitive Dashboard',
    description: 'Get a quick overview of your business with our user-friendly dashboard.',
    image: 'https://i.mythical.systems/storage/uploads/1738160250.png?height=300&width=500',
  },
  {
    title: 'Powerful Admin Panel',
    description: 'Manage all aspects of your hosting business from one central location.',
    image: 'https://mythical.pics/i?i=1738160336?height=300&width=500',
  },
]

const comparisonFeatures = [
  {
    name: 'Automated Provisioning',
    mythicalClient: true,
    whmcs: true,
    paymenter: true,
    holaclient: true,
  },
  { name: 'Open Source', mythicalClient: true, whmcs: false, paymenter: true, holaclient: false },
  {
    name: 'Automated Backups',
    mythicalClient: true,
    whmcs: true,
    paymenter: false,
    holaclient: true,
  },
  {
    name: 'Open SDK (Plugins SDK)',
    mythicalClient: true,
    whmcs: true,
    paymenter: true,
    holaclient: true,
  },
  { name: 'Live App', mythicalClient: true, whmcs: false, paymenter: true, holaclient: true },
  {
    name: 'Customizable Themes',
    mythicalClient: true,
    whmcs: true,
    paymenter: false,
    holaclient: false,
  }
]

const pricingPlans = [
  {
    title: 'Starter',
    price: 0,
    features: ['Full Access', 'Community Support', '1 Nodes'],
    popular: true,
    link: 'https://www.mythical.systems/docs/mythicalclient-v4/welcome/',
    button: 'Get Started',
  },
  {
    title: 'Professional',
    price: 15,
    features: [
      'Full Access ',
      'Priority Support',
      '15 Nodes',
      'Additional plugins',
      'Discount on plugins',
      'Update priority',
    ],
    popular: false,
    link: '#',
    button: 'Coming Soon',
  },
  {
    title: 'Enterprise',
    price: 50,
    features: [
      'Unlimited Everything',
      '24/7 Premium Support',
      'Unlimited Nodes',
      'Additional plugins',
      'Discount on plugins',
      'Update priority',
      'Custom branding',
    ],
    popular: false,
    link: '#',
    button: 'Coming Soon',
  },
]

const testimonials = [
  {
    quote:
      "Pretty good, easy to make themes and edit it's interface. I've been using it for half a month now, seems pretty good ❤️ ",
    name: 'Rodio',
    company: 'Free2Host.',
    avatar: 'https://github.com/mythicalltd.png?height=40&width=40',
  },
  {
    quote:
      'I love it is better then the most client areas out there. Never had a problem with it 5/5',
    name: 'Usslmulk',
    company: 'Unknown',
    avatar: 'https://github.com/mythicalltd.png?height=40&width=40',
  },
  {
    quote: 'It does what it should do the owner is helpful and really nice.',
    name: 'LordWolfy',
    company: 'Unknown',
    avatar: 'https://github.com/mythicalltd.png?height=40&width=40',
  },
  {
    quote:
      'I really like this Dashboard/client better then other if your looking one use this has so much features and is easy to use.',
    name: 'piecerxd',
    company: 'Unknown',
    avatar: 'https://github.com/mythicalltd.png?height=40&width=40',
  },
  {
    quote: 'Easy to Install and understandable Docs, nice look and feel.',
    name: 'Pringles',
    company: 'Unkown',
    avatar: 'https://github.com/mythicalltd.png?height=40&width=40',
  },
  {
    quote:
      "Good UI and animations and ease of navigation, And the queue system is good if your node allocation is full, and dont show error reported by panel like in other client's",
    name: 'coolhighzz',
    company: 'Unknown',
    avatar: 'https://github.com/mythicalltd.png?height=40&width=40',
  },
]

// Countdown Timer Logic
const countdown = ref({
  days: 0,
  hours: 0,
  minutes: 0,
  seconds: 0,
})

const calculateTimeLeft = () => {
  const difference = +new Date('2025-03-15') - +new Date()
  let timeLeft = { days: 0, hours: 0, minutes: 0, seconds: 0 }

  if (difference > 0) {
    timeLeft = {
      days: Math.floor(difference / (1000 * 60 * 60 * 24)),
      hours: Math.floor((difference / (1000 * 60 * 60)) % 24),
      minutes: Math.floor((difference / 1000 / 60) % 60),
      seconds: Math.floor((difference / 1000) % 60),
    }
  }

  countdown.value = timeLeft
}

let timer: number
</script>

<style>
@import 'tailwindcss/base';
@import 'tailwindcss/components';
@import 'tailwindcss/utilities';

/* Custom animations */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes float {
  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(-10px);
  }
}

.animate-fade-in-up {
  animation: fadeInUp 0.6s ease-out forwards;
}

.animate-float {
  animation: float 3s ease-in-out infinite;
}

.animation-delay-200 {
  animation-delay: 200ms;
}

.animation-delay-400 {
  animation-delay: 400ms;
}

/* Custom scrollbar */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: #151329;
}

::-webkit-scrollbar-thumb {
  background: #2d2844;
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: #3a3557;
}
</style>
