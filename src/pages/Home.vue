<script setup lang="ts">
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import BarangJualan from '../components/BarangJualan.vue';
import Maps from '../components/Maps.vue';
import { faWhatsapp } from '@fortawesome/free-brands-svg-icons';
import { faPhone } from '@fortawesome/free-solid-svg-icons';
import { ref } from 'vue';
import { useNow, useDateFormat,  } from '@vueuse/core';


const date = useDateFormat(useNow(), "DD - MM - YYYY", {locales: 'id-ID'})
const day = useDateFormat(useNow(), "dddd", {locales: 'id-ID'})
</script>

<!-- TODO dinamis tanggal besok dan tulisan libur-->
<!-- TODO fungsional footer bagian wa -->


<template>
    <div id="app" class="w-full h-dvh">
        <header class="w-full h-fit flex items-center justify-between p-5 bg-white z-50 sm:shadow-md sticky top-0">
            <h1 class="font-bold">Men Sari</h1>
            <div>
                <ul class="flex items-center text-neutral-500 gap-4 sm:gap-10">
                    <li class="text-xs hover:underline hover:text-neutral-800"><a href="#barang">Barang</a></li>
                    <li class="text-xs hover:underline hover:text-neutral-800"><a href="#kontak">Kontak</a></li>
                </ul>
            </div>
        </header>
        <section class="p-5 h-4/5 flex flex-col gap-10 justify-center sm:justify-evenly">
            <!-- <img src="../assets/pp.svg" class="absolute inset-0" /> -->
            <div>
                <h1 class="font-semibold text-4xl sm:text-6xl sm:font-bold">Om Swastyastu</h1>
                <h2 class="font-semibold text-sm sm:text-2xl sm:mt-2 sm:ml-2">Selamat Datang, Silahkan Melihat-Lihat</h2>
            </div>
            <div class="w-full flex flex-col sm:flex-row sm:justify-between h-fit px-8 py-3 pb-9 rounded-lg bg-gradient-to-br from-orange-500 sm:from-transparent to-orange-800 sm:to-transparent relative shadow-lg">
                <div class="flex justify-between sm:flex-col sm:w-2/4 border-b pb-2 border-b-white/20 font-semibold text-white sm:text-neutral-800">
                    <p class="sm:font-bold sm:text-xl">{{day}}</p>
                    <p class="sm:mt-2">{{date}}</p>
                </div>
                <div class="w-full flex justify-center sm:justify-end gap-3 text-6xl font-bold">
                    <span id="libur"
                        class="text-white sm:text-neutral-800 bg-clip-text">L</span>
                    <span id="libur"
                        class="text-white sm:text-neutral-800 bg-clip-text">I</span>
                    <span id="libur"
                        class="text-white sm:text-neutral-800 bg-clip-text">B</span>
                    <span id="libur"
                        class="text-white sm:text-neutral-800 bg-clip-text">U</span>
                    <span id="libur"
                        class="text-white sm:text-neutral-800 bg-clip-text">R</span>
                </div>
            </div>
        </section>
        <section class="h-fit w-full p-5">
            <h1 id="barang" class="text-3xl font-bold text-neutral-600">Barang Jualan</h1>
            <div class="mt-4 grid grid-cols-1 grid-rows-4 sm:grid-cols-2 sm:grid-rows-2 md:grid-cols-3 md:grid-rows-2 gap-5">
                <BarangJualan 
                    type="1"
                    title="Bubur Ayam"
                    description="Bubur ayam adalah salah satu jenis makanan dari Indonesia. Bubur nasi adalah beras yang dimasak dengan air yang banyak sehingga memiliki tekstur yang lembut dan berair. "/>
                <BarangJualan 
                    type="2"
                    title="Tum Ayam"
                    description="Tum ayam merupakan sajian khas Bali yang terdiri dari campuran daging cincang dan bumbu."/>
                <BarangJualan 
                    type="3"
                    title="Tum Babi"
                    description="Tum babi dibuat dari daging dan kulit babi yang dicincang lalu diberi bumbu base genep, tepung, dan darah."/>
                <BarangJualan 
                    type="4"
                    title="Tum Tuna"
                    description="Tum ayam merupakan sajian khas Bali yang terdiri dari campuran daging cincang dan bumbu."/>
            </div>
        </section>
        <footer class="h-fit p-3 pt-8 pb-10 grid grid-cols-1 sm:grid-cols-2 gap-5 bg-neutral-800 text-neutral-300 overflow-hidden">
            <div>
                <h1 class="text-xl font-semibold mb-2">Men Sari</h1>
                <p class="text-sm">Pengusaha Bubur</p>
            </div>
            <div>
                <h1 class="text-xl font-semibold mb-2">Hubungi</h1>
                <div id="kontak">
                    <ul class="text-sm flex flex-col gap-2">
                        <li>
                           <FontAwesomeIcon :icon="faPhone"/>
                           <p>+62 2833 122 1213</p> 
                        </li>
                        <li>
                            <FontAwesomeIcon :icon="faWhatsapp"/>
                            <a href="/">Men Sari</a>
                        </li>
                    </ul>
                </div>
            </div>
            <div>
                <h1 class="text-xl font-semibold mb-2">Lokasi</h1>
                <p class="mb-2 text-sm">C39X+2FG, Bengkel, Kediri, Tabanan Regency, Bali 82115</p>
                <Maps/>
            </div>
        </footer>
    </div>
</template>
<style scoped>

    ul li {
        display: flex;
        align-items: center;
        gap: 10px;
    }

    html{
        scroll-behavior: smooth;
    }

</style>