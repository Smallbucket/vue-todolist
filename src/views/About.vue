<template>
	<div class="about">
		<h1>This is an about page</h1>

<div v-viewer="options" class="images clearfix">
      <template v-for="{source, thumbnail} in images">
        <img :src="thumbnail" :data-source="source" class="image" :key="source" :alt="source.split('?image=').pop()">
      </template>
    </div>
	</div>
</template>

<script>
import 'viewerjs/dist/viewer.css'
import Viewer from 'v-viewer/src/component.vue'

const sourceImages = []
const base = parseInt((Math.random() * 60), 10) + 10
for (let i = 0; i < 10; i++) {
  sourceImages.push({
    thumbnail: `https://picsum.photos/id/${base + i}/346/216`,
    source: `https://picsum.photos/id/${base + i}/1440/900`
  })
}

export default {
	
	components: {
		Viewer
	},
	data() {
		return {
			options: {
		        toolbar: true,
		        url: 'data-source'
		      },
			images: [...sourceImages].splice(0, 5)
		}
	},
	methods: {
		inited (viewer) {
			this.$viewer = viewer
		},
		show () {
			this.$viewer.show()
		}
	}
}
</script>