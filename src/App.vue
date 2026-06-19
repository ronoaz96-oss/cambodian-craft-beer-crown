<template>
  <div class="min-h-screen bg-gray-50">

    <!-- Hidden checkbox -->
    <input type="checkbox" id="menu-toggle" class="hidden peer" />

    <!-- Header -->
    <header class="fixed top-0 left-0 right-0 z-50 bg-white ">
      <div class="flex items-center justify-between px-4 h-14">

        <!-- Logo -->
        <a href="/" class="flex items-center gap-2">
          
          <span class="text-gray-900 font-semibold text-lg tracking-tight">Logo</span>
        </a>

        <!-- Burger -->
        <label
          for="menu-toggle"
          class="burger p-2 rounded-lg text-gray-600 hover:bg-gray-100 active:bg-gray-200 transition-colors cursor-pointer"
          aria-label="Toggle menu"
        >
          <span></span>
          <span></span>
          <span></span>
        </label>
      </div>
    </header>

    <!-- Overlay -->
    <label
      for="menu-toggle"
      class="fixed inset-0 z-40 bg-black/30 opacity-0 pointer-events-none transition-opacity duration-300
             peer-checked:opacity-100 peer-checked:pointer-events-auto"
    />

    <!-- Slide-in from right nav -->
    <nav
      class="fixed top-0 right-0 bottom-0 z-50 w-72 bg-white shadow-xl
             translate-x-full transition-transform duration-300 ease-in-out
             peer-checked:translate-x-0"
    >
      <!-- Nav header -->
      <div class="flex items-center justify-between px-5 h-14 border-b border-gray-100">
        <span class="font-semibold text-gray-900">Menu</span>
        <label for="menu-toggle" class="p-1 rounded-lg text-gray-500 hover:bg-gray-100 cursor-pointer">
          <svg class="w-5 h-5" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </label>
      </div>

      <!-- Nav links -->
      <ul class="flex flex-col divide-y divide-gray-50 mt-2">
        <li>
          <label for="menu-toggle">
            <a href="/" class="flex items-center gap-3 px-6 py-4 text-gray-700 hover:bg-indigo-50 hover:text-indigo-600 transition-colors">
              <span class="text-lg text-black">
                <svg class="w-5 h-5" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                  <path d="M3 12l9-9 9 9" />
                  <path d="M5 10v10a1 1 0 0 0 1 1h4v-6h4v6h4a1 1 0 0 0 1-1V10" />
                </svg>
              </span>
              <span class="font-medium">Home</span>
            </a>
          </label>
        </li>
        <li>
          <label for="menu-toggle">
            <a href="/about" class="flex items-center gap-3 px-6 py-4 text-gray-700 hover:bg-indigo-50 hover:text-indigo-600 transition-colors">
              <span class="text-lg">👤</span>
              <span class="font-medium">About</span>
            </a>
          </label>
        </li>
        <li>
          <label for="menu-toggle">
            <a href="/services" class="flex items-center gap-3 px-6 py-4 text-gray-700 hover:bg-indigo-50 hover:text-indigo-600 transition-colors">
              <span class="text-lg">⚙️</span>
              <span class="font-medium">Services</span>
            </a>
          </label>
        </li>
        <li>
          <label for="menu-toggle">
            <a href="/contact" class="flex items-center gap-3 px-6 py-4 text-gray-700 hover:bg-indigo-50 hover:text-indigo-600 transition-colors">
              <span class="text-lg">✉️</span>
              <span class="font-medium">Contact</span>
            </a>
          </label>
        </li>
      </ul>
    </nav>

    <!-- Page content -->
    <main class="pt-14 px-4 py-6">
      <p class="text-gray-400 text-sm text-center mt-10">Page content here</p>
    </main>

  </div>
</template>

<script setup>
// No JavaScript needed!
</script>

<style scoped>
/* Burger icon */
.burger {
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 5px;
  width: 40px;
  height: 40px;
}
.burger span {
  display: block;
  height: 2px;
  width: 20px;
  background: currentColor;
  border-radius: 2px;
  transition: transform 0.3s ease, opacity 0.2s ease;
  transform-origin: center;
}

/* Animate to X when checked */
#menu-toggle:checked ~ header .burger span:nth-child(1) {
  transform: translateY(7px) rotate(45deg);
}
#menu-toggle:checked ~ header .burger span:nth-child(2) {
  opacity: 0;
  transform: scaleX(0);
}
#menu-toggle:checked ~ header .burger span:nth-child(3) {
  transform: translateY(-7px) rotate(-45deg);
}
</style>