<style scoped>
	@import '../styles/home.css';
</style>


<template>
	<wrapper>
		<div class="home">
			<div class="content">
				<ul>
					<blogItem v-for="item in blogs" :blog="item" :key="item._id"></blogItem>
				</ul>
			</div>

			<weeklyList></weeklyList>
		</div>
	</wrapper>
</template>

<script>
import wrapper from '../components/wrapper.vue';
import blogItem from '../components/blogItem.vue';
import weeklyList from '../components/weeklyList.vue';

export default {
	components: {
		wrapper,
		blogItem,
		weeklyList
	},
	data() {
		return {
			blogs: [],
			api: 'http://norma0119.cn:3000/api/todo_all'
		}
	},

	methods: {
		getBlogs() {
			this.$http.get(this.api).then((response) => {
				this.blogs = response.data;
			})
		}
	},

	mounted() {
		this.getBlogs();
	}
}
</script>

