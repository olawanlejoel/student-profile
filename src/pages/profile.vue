<template>
  <layout>
    <div class="users w-full">
      <h1 class="text-center text-3xl font-bold mb-2">Student's Profile</h1>
      <div
        class="border border-black rounded-xl p-4 mb-2"
        v-for="edge in $page.allFaker.edges"
        :key="edge.node.email"
      >
        <p><span class="font-bold pr-2">Name:</span>{{ edge.node.author }}</p>
        <p><span class="font-bold pr-2">Email:</span> {{ edge.node.email }}</p>
        <p><span class="font-bold pr-2">Title:</span> {{ edge.node.title }}</p>
      </div>
    </div>
  </layout>
</template>

<page-query>
query allFaker {
  allFaker (perPage: 10) {
    edges {
      node {
        email,
        author,
        title,
      }
    }
  }
}
</page-query>

<script>
export default {};
</script>

<style></style>
