<template>
  <div>
    <HomeHeroSection />
    <HomeStatSection />
    <div class="max-w-7xl mx-auto mt-14 px-4 sm:px-6 lg:px-8 lg:mt-24">
      <div class="space-y-8 sm:space-y-12">
        <div class="space-y-5 sm:mx-auto sm:max-w-xl sm:space-y-4 lg:max-w-5xl text-center">
          <h2 class="text-3xl font-extrabold tracking-tight sm:text-4xl">
            Pourquoi cette initiative ?
          </h2>
          <p class="text-xl text-gray-500">
            <ul class="text-xl text-gray-500">
              <li>
               Pour que les cyclistes du pays de Morlaix puissent se déplacer en sécurité sur leurs trajets quotidiens.
              </li>
              <li>
                Pour que les aménagements à venir sur les lignes définies ici prennent en compte le cahier des charges édité par Morlaix Communauté en 2024 pour les aménagements cyclables.
              </li>
              <li>
                Pour que les habitant.e.s du pays de Morlaix qui le souhaitent puissent se déplacer sans voiture et le coût qui lui est associé.
              </li>
              <li>
                Pour donner des idées aux élu.e.s en cours et futurs. 
              </li>
            </ul>
          </p>
        </div>
      </div>
      <ProgressBar :voies="voies" class="mt-8 md:mt-10" />
      <Stats :voies="voies" class="mt-8" />
      <StatsQuality v-if="displayQuality() && displayQualityOnHomePage()" :voies="voies" class="mt-8" />
      <Typology :voies="voies" class="mt-8 max-w-2xl mx-auto" />
    </div>
    <div class="max-w-7xl mx-auto mt-14 px-4 sm:px-6 lg:px-8 lg:mt-24">
      <div class="space-y-8 sm:space-y-12">
        <div class="space-y-5 sm:mx-auto sm:max-w-xl sm:space-y-4 lg:max-w-5xl text-center">
          <h2 class="text-3xl font-extrabold tracking-tight sm:text-4xl">
            Découvrez les lignes
          </h2>
          <p class="text-xl text-gray-500">
            Choisissez une {{ getRevName('singular') }} pour connaitre le détail de l'itinéraire.
          </p>
        </div>
        <HomeLinesSection class="mt-5" />
      </div>
    </div>
    <div class="py-16">
      <LvvCta />
    </div>
  </div>
</template>

<script setup>
const { getRevName, displayQuality, displayQualityOnHomePage } = useConfig();

const { data: voies } = await useAsyncData(() => {
  return queryContent('voies-cyclables').where({ _type: 'json' }).find();
});
</script>
