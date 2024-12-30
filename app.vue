<template>
  <div>
    <ul>
      <li>
        <NuxtLink :to="'/pdf'">
            Go to pdf
        </NuxtLink>
      </li>
      <li>
        <NuxtLink :to="'/pdf-manual-load'">
          Go to manual load pdf
        </NuxtLink>
      </li>
      <li>
        <NuxtLink :to="'/'">
            Go home
        </NuxtLink>
      </li>
      <li>
        <NuxtLink :to="'/non-pdf'">
            Go to large dom
        </NuxtLink>
      </li>
    </ul>
    <NuxtPage :key="$route.fullPath"/>
  </div>
</template>
