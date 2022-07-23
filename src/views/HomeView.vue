<template>
	<div id="main-wrapper">
		<div class="wrapper style1"  >
			<div class="inner">

				<!-- Feature 1 -->
					<section class="container box feature1">
						<div class="row">
							<div class="col-12">
								<header class="first major">
									<h2>Mes 3 Dernières Cartes</h2>
								</header>
							</div>
							<div class="col-4 col-12-medium">
								<section>
									<a href="#" class="image featured" @click="pickACard(cards[29].id)"><img :src="cards[29].imageUrl" alt="" /></a>
									<header class="second icon solid fa-dragon">
										<h3>{{cards[29].name}}</h3>
										<p>{{cards[29].type}}</p>
									</header>
								</section>
							</div>
							<div class="col-4 col-12-medium">
								<section>
									<a href="#" class="image featured" @click="pickACard(cards[68].id)"><img :src="cards[68].imageUrl" alt="" /></a>
									<header class="second icon solid fa-dragon">
											<h3>{{cards[68].name}}</h3>
										<p>{{cards[68].type}}</p>
									</header>
								</section>
							</div>
							<div class="col-4 col-12-medium">
								<section>
									<a href="#" class="image featured" @click="pickACard(cards[6].id)"><img :src="cards[6].imageUrl" alt="" /></a>
									<header class="second icon solid fa-dragon">
										<h3>{{cards[6].name}}</h3>
										<p>{{cards[6].type}}</p>
									</header>
								</section>
							</div>

						</div>
					</section>

			</div>
		</div>
	</div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'HomeView',
  components:{
  },
  data:()=>({
  cards:[]    
  }),
  methods:{
      pickACard(id){
		this.$router.push({ name:'CardDetails', params: {cardId:id}})
	}
  },
  async created(){
    const cards = await axios.get('https://api.magicthegathering.io/v1/cards ')
    this.cards=cards.data.cards
  }
}
</script>
<style >
   
</style>