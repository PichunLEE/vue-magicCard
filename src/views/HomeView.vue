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
									<a href="#" class="image featured" @click="pickACard(cards[18].id)"><img :src="cards[18].imageUrl" alt="" /></a>
									<header class="second icon solid fa-dragon">
										<h3>{{cards[18].name}}</h3>
										<p>{{cards[18].type}}</p>
									</header>
								</section>
							</div>
							<div class="col-4 col-12-medium">
								<section>
									<a href="#" class="image featured" @click="pickACard(cards[27].id)"><img :src="cards[27].imageUrl" alt="" /></a>
									<header class="second icon solid fa-dragon">
											<h3>{{cards[27].name}}</h3>
										<p>{{cards[27].type}}</p>
									</header>
								</section>
							</div>
							<div class="col-4 col-12-medium">
								<section>
									<a href="#" class="image featured" @click="pickACard(cards[42].id)"><img :src="cards[42].imageUrl" alt="" /></a>
									<header class="second icon solid fa-dragon">
										<h3>{{cards[42].name}}</h3>
										<p>{{cards[42].type}}</p>
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