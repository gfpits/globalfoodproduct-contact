<script setup>
/*
  ⭐ โครงข้อมูลแบบ Team Group
  เพิ่มทีมเพิ่มคนได้ง่าย
*/
const teams = [
  {
    team: 'Food Service',
    members: [
      {
        title: 'Thaifex',
        name: 'คุณ ภาวิดา สุขดี (แอร์)',
        phone: '0805689999',
        avatar: 'https://i.pravatar.cc/100?img=5'
      },
      {
        title: 'เชลล์ชวนชิม',
        name: 'คุณ สุทธิ ทุกข์ดี (อาร์ม)',
        phone: '0805688888',
        avatar: 'https://i.pravatar.cc/100?img=8'
      },
      {
        title: 'เปิปพิสดาร',
        name: 'คุณ ธีรพงศ์ บรรจง (ตรงตรง)',
        phone: '0805687777',
        avatar: 'https://i.pravatar.cc/100?img=11'
      }
    ]
  },
  {
    team: 'Restaurant',
    members: [
      {
        title: 'Thaifex',
        name: 'คุณ อภิญญา สุขดี (อู๋)',
        phone: '0805681111',
        avatar: 'https://i.pravatar.cc/100?img=20'
      }
    ]
  },

  {
    team: 'Retail',
    members: [
      {
        title: 'Lotus',
        name: 'คุณ จิรายุส มุกทอง (ส้มร้อน)',
        phone: '0805681111',
        avatar: 'https://i.pravatar.cc/100?img=9'
      },

      {
        title: 'Central',
        name: 'คุณ นิรันดร์ พงศ์ศิริ (นัท)',
        phone: '0805682222',
        avatar: 'https://i.pravatar.cc/100?img=16'
      }
    ]
  }
]

const email = 'info@globalfoodproduct.com'

const brands = [
  { name: 'Acqua Panna', logo: '/brands/acquapanna.jpg' },
  { name: 'Balducci', logo: '/brands/balducci.jpg' },
  { name: 'Beerenberg', logo: '/brands/beerenberg.jpg' },
  { name: 'Bega', logo: '/brands/Bega.png' },
  { name: 'BenJerry', logo: '/brands/benjerry.jpg' },
  { name: 'Bulla', logo: '/brands/bulla.jpg' },
  { name: 'Chachos', logo: '/brands/chachos.jpg' },
  { name: 'Cheezels', logo: '/brands/cheezels.jpg' },
  { name: 'Cocobella', logo: '/brands/cocobella.jpg' },
  { name: 'Dr.Oetker', logo: '/brands/droetker.jpg' },
  { name: 'FarmersUnion', logo: '/brands/farmersunion.jpg' },
  { name: 'Fiamma', logo: '/brands/fiamma.jpg' },
  { name: 'Hellmanns', logo: '/brands/hellmanns.jpg' },
  { name: 'Hengstenberg', logo: '/brands/hengstenberg.jpg' },
  { name: 'JackLinks', logo: '/brands/jacklinks.jpg' },
  { name: 'Lavazza', logo: '/brands/lavazza.jpg' },
  { name: 'Mission', logo: '/brands/mission.png' },
  { name: 'NaturalChip', logo: '/brands/naturalchip.jpg' },
  { name: 'Pauls', logo: '/brands/pauls.jpg' },
  { name: 'Peroni', logo: '/brands/peroni.png' },
  { name: 'RANA', logo: '/brands/rana.jpg' },
  { name: 'Sanremo', logo: '/brands/sanremo.jpg' },
  { name: 'Spam', logo: '/brands/spam.jpg' }
]
</script>

<template>
  <div class="min-h-screen bg-white text-gray-900">
    <section
      class="
      min-h-[50vh] md:min-h-[60vh]
      flex flex-col justify-center items-center
      text-center
      px-6 md:px-10
      bg-gradient-to-b from-gray-50 to-white
      "
    >
      <!-- Logo -->
      <img
        src="/images/logo.png"
        class="w-40 sm:w-32 md:w-40 mb-4 md:mb-6 opacity-100"
      >

      <!-- Title -->
      <h1
        class="
        text-2xl sm:text-3xl md:text-4xl lg:text-5xl
        font-semibold tracking-tight
        bg-gradient-to-r from-gray-900 to-gray-500
        bg-clip-text text-transparent
        "
      >
        Global Food Product
      </h1>

      <!-- Subtitle -->
      <p class="text-gray-500 mt-3 text-sm md:text-base max-w-sm leading-relaxed">
        Contact our team directly.
        <br class="hidden sm:block">
        Scroll down to view all team information.
      </p>

      <!-- Scroll Hint -->
      <div class="mt-6 md:mt-10 animate-bounce text-gray-400 text-xs md:text-sm">
        ↓ Scroll
      </div>
    </section>

    <!-- 🏷️ Brand Strip -->
    <section class="py-12 border-y border-gray-100 mb-12 overflow-hidden">
      <p class="text-sm text-center text-gray-400 mb-6 tracking-widest">
        OUR BRAND SELECTION
      </p>

      <div class="relative w-full overflow-hidden">
        <!-- Track -->
        <div class="brand-track flex items-center gap-14">
          <!-- 🔁 ทำซ้ำ 2 รอบ เพื่อให้เลื่อนไม่มีสะดุด -->
          <template v-for="i in 4">
            <div
              v-for="b in brands"
              :key="b.name + i"
              class="flex-shrink-0 opacity-80 hover:opacity-100 transition"
            >
              <!-- grayscale -->
              <img
                :src="b.logo"
                class="h-25 object-contain hover:grayscale-0 transition duration-300"
              />
            </div>
          </template>
        </div>
      </div>
    </section>

    <!-- 📄 CONTENT -->
    <UContainer class="max-w-xl mx-auto pb-20">
      <!-- 🔁 Loop Teams -->
      <section
        v-for="team in teams"
        :key="team.team"
        class="mb-12"
      >
        <h2 class="text-xl font-semibold mb-4">
          {{ team.team }}
        </h2>

        <div class="space-y-3">
          <!-- 👤 MEMBER CARD -->
          <div
            v-for="m in team.members"
            :key="m.phone"
            class="flex items-center gap-4 border-b border-gray-200 pb-4"
          >
            <!-- Avatar -->
            <img
              :src="m.avatar || 'https://i.pravatar.cc/100?img=12'"
              class="w-12 h-12 rounded-full object-cover"
            />
            <!-- Info -->
            <div class="flex-1">
              <p class="font-medium">
                {{ m.title }}
              </p>
              <p class="text-sm text-gray-600">
                {{ m.name }}
              </p>
              <p class="text-xs text-gray-400 mt-1">
                {{ m.phone }}
              </p>
            </div>
            <!-- Action -->
            <UButton
              size="sm"
              icon="i-heroicons-phone"
              variant="ghost"
              :to="`tel:${m.phone}`"
            >
              Tel
            </UButton>
          </div>
        </div>
      </section>

      <!-- EMAIL -->
      <section class="mt-10">
        <h2 class="text-lg font-semibold mb-2">
          Email
        </h2>

        <UButton
          block
          variant="soft"
          icon="i-heroicons-envelope"
          :to="`mailto:${email}`"
        >
          {{ email }}
        </UButton>
      </section>

      <!-- 🛒 Online Shop -->
      <section class="py-12 border-t border-gray-100">
        <div class="max-w-3xl mx-auto px-6 text-center">
          <!-- Title -->
          <h2 class="text-lg md:text-xl font-semibold tracking-wide">
            ONLINE SHOP
          </h2>

          <p class="text-sm text-gray-400 mt-2 mb-8">
            Shop our products online
          </p>

          <!-- Horizontal Logo Row -->
          <div
            class="
            grid
            grid-cols-3
            sm:grid-cols-3
            md:grid-cols-3
            gap-8 md:gap-12
            items-center
            justify-items-center
            "
          >
            <!-- TOPS -->
            <a
              href="https://www.tops.co.th/en/shop-by-brands/global-food-products"
              target="_blank"
              class="flex-shrink-0 opacity-80 hover:opacity-100 transition"
            >
              <!-- <img
                src="/images/tops.png"
                class="h-10 md:h-12 object-contain"
              /> -->
              <img src="/images/tops.png" alt="Tops" loading="lazy" />
            </a>

            <!-- SHOPEE -->
            <a
              href="https://shopee.co.th/global_food_products"
              target="_blank"
              class="flex-shrink-0 opacity-80 hover:opacity-100 transition"
            >
              <!-- <img
                src="/images/shopee.png"
                class="h-10 md:h-12 object-contain"
              /> -->
              <img src="/images/shopee.png" alt="Shopee" loading="lazy" />
            </a>

            <!-- LAZADA -->
            <a
              href="https://www.lazada.co.th/shop/global-food-products/"
              target="_blank"
              class="flex-shrink-0 opacity-80 hover:opacity-100 transition"
            >
              <!-- <img
                src="/images/lazada.png"
                class="h-10 md:h-12 object-contain"
              /> -->
              <img src="/images/lazada.png" alt="Lazada" loading="lazy" />
            </a>
          </div>
        </div>
      </section>
    </UContainer>
  </div>
</template>

<style scoped lang="css">
.brand-track {
  width: max-content;
  animation: scrollBrand 60s linear infinite;
}

@keyframes scrollBrand {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-65%);
  }
}
</style>
