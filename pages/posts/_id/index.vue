<template>
    <div class="single-post-page">
        <section class="post">
            <h1 class="post-title">{{ loadedPost.title }}</h1>
            <div class="post-details">
                <div class="post-detail" >Last updated on {{ loadedPost.updatedDate }}</div>
                <div class="post-detail" >Write by {{ loadedPost.author }}</div>
            </div>
            <p class="post-content">{{ loadedPost.content }}</p>
        </section>
        <section class="post-feedback">
            <p>Let me know what you think about the post, send a mail to <a href="mailto:feeedback@my-awesome-domain.com">feeedback@my-awesome-domain.com</a>.</p>
        </section>
    </div>
</template>

<script>
export default {
  asyncData(context, callback) {
    return new Promise().catch( e => {
      context.error(new Error())
    })
    setTimeout(() => {
      callback(null, {
        loadedPost: {
          id: '1', 
          title: 'First Post (ID: '+ context.route.params.id +')', 
          previewText: 'This is our first post!',
          author:  'Krishna',
          updatedDate: new Date(),
          content: 'Some dummy text which is definitly not the preview text though!',
          thumbnail: 'https://todayidol.com/wp-content/uploads/2015/11/Shimazaki-Haruka-Baito-AKB48.jpg'
        }
      })
    },1000)
  }
}
</script>

<style scoped>
.single-post-page {
  padding: 30px;
  text-align: center;
  box-sizing: border-box;
}

.post {
  width: 100%;
}

@media (min-width: 768px) {
  .post {
    width: 600px;
    margin: auto;
  }
}

.post-title {
  margin: 0;
}

.post-details {
  padding: 10px;
  box-sizing: border-box;
  border-bottom: 3px solid #ccc;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

@media (min-width: 768px) {
  .post-details {
    flex-direction: row;
  }
}

.post-detail {
  color: rgb(88, 88, 88);
  margin: 0 10px;
}

.post-feedback a {
  color: red;
  text-decoration: none;
}

.post-feedback a:hover,
.post-feedback a:active {
  color: salmon;
}
</style>