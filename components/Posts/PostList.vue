<template>
    <section class="post-list">
        <PostPreview
        id="1"
        thumbnail="https://todayidol.com/wp-content/uploads/2015/11/Shimazaki-Haruka-Baito-AKB48.jpg"
        title="Hello Word"
        previewText="This is my first post!" />
        <PostPreview
        id="2"
        thumbnail="https://todayidol.com/wp-content/uploads/2015/11/Shimazaki-Haruka-Baito-AKB48.jpg"
        title="Hello There - the second time"
        previewText="This is my Second post!" />
        <PostPreview
        id="3"
        thumbnail="https://todayidol.com/wp-content/uploads/2015/11/Shimazaki-Haruka-Baito-AKB48.jpg"
        title="Hi"
        previewText="This is my third post!" />
    </section>        
</template>

<script>
import PostPreview from '@/components/Posts/PostsPreview'

export default {
    components:{
        PostPreview
    }    
}
</script>

<style scoped>


.post-list {
  display: flex;
  padding: 20px;
  box-sizing: border-box;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}
</style>