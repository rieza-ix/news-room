<template>
  <div class="p-6" v-for="article in news" :key="article.id">
    <!-- Header -->
    <div class="shadow-sm pb-4 mb-2">
      <div>
        <Header :imageUrl="article.image_url" :day="getDay(article.created_at)"
          :month="getMonthName(article.created_at)" />
      </div>
      <div>
        <ShareButton />
      </div>
    </div>
    <!-- Sub Header -->
    <div class="mb-8">
      <SubHeader :author="getAuthorName(article.author_id)" :title="article.title" :body="article.body" />
    </div>
  </div>
  <!-- Pagination -->
  <div class="p-3 mb-3">
    <Pagination />
  </div>
</template>

<script setup>
// Fetch the data from the JSON file provided
const { data: news } = await useFetch('https://tmsph-sdi-challenges.pages.dev/challenges/news.json');
const { data: authors } = await useFetch('https://tmsph-sdi-challenges.pages.dev/challenges/authors.json');

// Take the author id and name then store it as array of objects
const authorData = authors.value.map(row => {
  return { author_id: row.id, name: row.name };
});

// Function that accepts the author_id from the loop and find the match author_id to get the author name
const getAuthorName = (author_id) => {
  const author = authorData.find(author => author.author_id === author_id);
  return author ? author.name : 'Unknown Author';
};

// Format the created_at date to 3-word month name
const getMonthName = (dateString) => {
  const date = new Date(dateString);
  const month = date.toLocaleString('default', { month: 'short' });
  return month.toUpperCase();
};

// Get the date only from created_at date
const getDay = (dateString) => {
  const date = new Date(dateString);
  return date.getDate();
};
</script>
