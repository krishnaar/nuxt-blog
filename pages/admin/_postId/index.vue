<template>
    <div class="admin-post-page">
        <section class="update-form">
            <AdminPostForm :post="loadedPost"/>
        </section>        
    </div>
</template>

<script>
import AdminPostForm from '@/components/Admin/AdminPostForm'

export default {
    layout: 'admin',
    components: {
        AdminPostForm
    },
    data() {
        return {
            loadedPost:{
                author: 'Krishna',
                title: 'My Awesome Post',
                content: 'Super amazing, thanks for that!',
                thumbnailLink: 'https://todayidol.com/wp-content/uploads/2015/11/Shimazaki-Haruka-Baito-AKB48.jpg'
            }
        }
    }
}
</script>

<style scoped>
.update-form {
    width: 90%;
    margin: 20px auto;
}

@media (min-width: 768px) {
    .new-post-form{
        width: 500px;
    }
}
</style>