<style scoped>
.blog-item {
    background-color: #ffffff;
    margin-bottom: 25px;
    padding: 15px 30px;
    box-sizing: border-box;
    transition: box-shadow 0.8s;

    &:hover{
        box-shadow:0px 0px 15px #ccc;
        -webkit-box-shadow: 0px 0px 15px #ccc;
        -moz-box-shadow: 0px 0px 15px #ccc;
    }

    .blog-item-url {
        font-size: 35px;
        
        &:hover {
            color: #666;
        }
    }

    .blog-item-author {
        margin-top: 5px;
        padding-top: 5px;
        border-top: 1px solid #999;
        display: flex;
        flex-direction: row;
        justify-content: flex-start;
        align-items: center;

        .blog-item-author-img {
            display: inline-block;
            width: 40px;
            height: 40px;
            border-radius: 100%;
            margin-right: 5px;
        }

        .blog-item-author-name {
            display: inline;
            margin-right: 10px;
        }

        .blog-item-author-date {
            color: #999;
        }
    }

    .blog-item-desc {
        margin: 20px 0 20px 0;
        p {
            text-indent: 2rem;
            font-size: 0.9rem;
            color: #666;
        }
    }
    
    .blog-item-tags {
        height: 40px;
        line-height: 40px;
        display: flex;
        align-items: center;

        .title {
            display: inline-block;
            margin-right: 15px;
            font-size: 1.6rem;
            font-weight: 400;
            color: #666;
        }

        .blog-item-tag {
            display: inline-block;
            box-sizing: border-box;
            height: 24px;
            line-height: 24px;
            border-radius: 22px;
            padding: 0 10px 0 10px;
            margin: 0 5px 0 5px;
            font-size: 0.5rem;
            border: 1px solid #999;
            color: #666;
        }

    }
}
</style>

<template>
    <li class="blog-item">
        <router-link to="/blog" class="blog-item-url">{{blog.title}}</router-link>
        <div class="blog-item-author">
            <img class="blog-item-author-img" src="../static/images/20160921_IMG_2989.jpg">
            <span class="blog-item-author-name">作者1</span>
            <span class="blog-item-author-date">2017-10-20</span>
        </div>
        <div class="blog-item-desc">
            <p>{{blog.content}}</p>
        </div>
        <div class="blog-item-tags">
            <span class="title iconfont icon-tag"></span>
            <router-link to="/category" class="blog-item-tag">标签一</router-link>
            <router-link to="/category" class="blog-item-tag">标签二</router-link>
            <router-link to="/category" class="blog-item-tag">标签三</router-link>
        </div>
    </li>
</template>

<script>
export default {
    props: {
        blog: Object
    },
    data() {
        return {

        }
    }

    
}
</script>