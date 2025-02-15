<template>
  <div class="bg-white pt-12 sm:pt-16">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="max-w-4xl mx-auto text-center">
        <h2 class="text-3xl font-extrabold text-gray-900 sm:text-4xl">
          Les {{ getRevName() }}, c'est quoi ?
        </h2>
        <p class="mt-3 text-xl text-gray-500 sm:mt-4">
          C'est le nom donné au projet de réseau cyclable idéal proposé par A Pied A Vélo en pays de Morlaix.<br>Concrètement, une {{ getRevName('singular') }} est un itinéraire reliant plusieurs points d'intérêt dans le pays de Morlaix, essentiellement depuis la ville centre. Il n'y a le plus souvent pas d'aménagement et c'est tout l'enjeu de ce réseau rêvé, qui propose un maillage cyclable sans discontinuités connectant la ville de Morlaix aux autres communes de l'agglomération et les communes entre elles.
        </p>
      </div>
    </div>
    <div class="mt-10 bg-white">
      <div class="relative">
        <div class="absolute inset-0 h-1/2 bg-white" />
        <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="max-w-4xl mx-auto">
            <dl class="rounded-lg bg-white shadow-lg sm:grid sm:grid-cols-3">
              <div class="flex flex-col border-b border-gray-100 p-6 text-center sm:border-0 sm:border-r">
                <dt class="order-2 mt-2 text-lg leading-6 font-medium text-gray-500">
                  Lignes<br><small>Linenn</small>
                </dt>
                <dd class="order-1 text-5xl font-extrabold text-lvv-blue-600">
                  {{ getNbVoiesCyclables() }}
                </dd>
              </div>
              <div class="flex flex-col border-t border-b border-gray-100 p-6 text-center sm:border-0 sm:border-l sm:border-r">
                <dt class="order-2 mt-2 text-lg leading-6 font-medium text-gray-500">
                  Distance<br><small>Hed</small>
                </dt>
                <dd class="order-1 text-5xl font-extrabold text-lvv-blue-600">
                  190km
                </dd>
              </div>
              <div class="flex flex-col border-t border-gray-100 p-6 text-center sm:border-0 sm:border-l">
                <dt class="order-2 mt-2 text-lg leading-6 font-medium text-gray-500">
                  Budget<br><small>Budjed</small>
                </dt>
                <dd class="order-1 text-5xl font-extrabold text-lvv-blue-600">
                  à définir
                </dd>
              </div>
            </dl>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const { getRevName, getNbVoiesCyclables } = useConfig();
</script>
