<template>
   <Layout>
    <!-- Page Header-->
    <header
      class="masthead"
      style="background-image: url('/assets/img/home-bg.jpg')"
    >
      <div class="container position-relative px-4 px-lg-5">
        <div class="row gx-4 gx-lg-5 justify-content-center">
          <div class="col-md-10 col-lg-8 col-xl-7">
            <div class="site-heading">
              <h1># {{$page.tag.title}}</h1>
              <span class="subheading">Tag</span>
            </div>
          </div>
        </div>
      </div>
    </header>
    <!-- Main Content-->
    <div class="container px-4 px-lg-5">
      <div class="row gx-4 gx-lg-5 justify-content-center">
        <div class="col-md-10 col-lg-8 col-xl-7">
          <div v-for="post in $page.tag.posts" :key="post.id">
            <!-- Post preview-->
            <div class="post-preview">
              <g-link :to="`/post/${post.id}`">
                <h2 class="post-title">
                  {{ post.title }}
                </h2>
              </g-link>
            </div>
            <!-- Divider-->
            <hr class="my-4" />
          </div>
          <!-- Pager-->
          <!-- <Pager :info="$page.posts.pageInfo"/> -->
          <!-- <div class="d-flex justify-content-end mb-4">
            <a class="btn btn-primary text-uppercase" href="#!"
              >Older Posts →</a
            >
          </div> -->
        </div>
      </div>
    </div>
  </Layout>
</template>

<page-query>
query($id: ID!) {
  tag: strapiTag(id: $id) {
    id
    title
    posts {
      id
      title
    }
  }
}
</page-query>

<script>
export default {
  name: "TagPage",
}
</script>

<style>

</style>