<template>
    <div class="post-page">
        <PostList :posts="loadedPosts"/>
    </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'

export default {
    components:{
        PostList
    },
    asyncData(context) {
        return new Promise((resolve, reject) => {
            setTimeout (() => {
                resolve({
                    loadedPosts: [
                        { 
                            id: '1', 
                            title: "First Post", 
                            previewText: 'This is our first post!', 
                            thumbnail: 'http://akb48wup.com/wp-content/uploads/2012/08/shimazaki-haruka-akb48-78.jpg'
                        },
                        { 
                            id: '2', 
                            title: "Second Post", 
                            previewText: 'This is our second post!', 
                            thumbnail: 'http://akb48wup.com/wp-content/uploads/2012/08/shimazaki-haruka-akb48-78.jpg'
                        }
                    ]
                });
            }, 1500)
        })
        .then(data => {
            return data
        })
        .catch(e => {
            context.error(new Error())
        })
    },
}
</script>

<style scoped>
.post-page{
    display: flex;
    justify-content: center;
    align-items: center;
}

</style>