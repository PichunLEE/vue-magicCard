<template>

     <div id="main-wrapper">
		<div class="wrapper style2">
			<div class="inner">
				<div class="container">
					<div id="content">

						<!-- Content -->
						<article>
							<header class="major">
								<h2>Ma Collection</h2>
							</header>
							<div class='card-list' v-for="(card,idx) in cards" :key="idx" >
								<div class='card-title'><b>{{'#'+(idx+1)}}</b> {{card.name}}</div>
								<div style="cursor :pointer" class='card-action' @click="pickACard(card.id)">👀</div>
							</div>  
						</article>

					</div>
				</div>
			</div>
		</div>

	</div>
</template>

<script>
import axios from 'axios'
const MAGIC_API_URL = "https://api.magicthegathering.io/v1/cards "
export default {
  name: 'CollectionView',
  components:{
  },
  data:()=>({
  cards:[]    
  }), 
  methods:{
	pickACard(id){
	this.$router.push({ name: 'CardDetails', params:{cardId: id }})
	},
  },
  async created(){
    const cards = await axios.get(MAGIC_API_URL)
    this.cards = cards.data.cards
  }  
}
</script>
<style scoped>
@import '@/assets/css/card-list.css'
</style>