<template>
	<!-- Main Wrapper -->
		<div id="main-wrapper">
			<div class="wrapper style2">
				<div class="inner">
					<div class="container">
						<div class="row">
							<div class="col-8 col-12-medium">
								<div id="content">

									<!-- Content -->

										<article>
											<header class="major">
												<h2>{{card.title}}</h2>
												<p>{{card.artist}}</p>
											</header>

											<span class="image featured">
												<img :src="card.imageUrl" alt="" />
											</span>

											<h3 style="width:50%; margin-left:25%; margin-bottom:10px; height=150px; color:red" v-if="!card.imageUrl">
											Oops, there's no this card.
											</h3>
											<!-- <img style="width:50%; margin-left:25%; margin-bottom:10px; height=150px" :src="hasCoverUrl(card)" alt="..." />	 -->

											<p>{{card.text}}</p>
										</article>

								</div>
							</div>
							<div class="col-4 col-12-medium">
								<div id="sidebar">

									<!-- Sidebar -->

										<section>
											<header class="major">
												<h2>Infos</h2>
											</header>
											<p>set name: <b>{{card.name}}</b></p>
											<p >rarity:  <b>{{card.rarity}}</b></p>
											<p >toughness:  <b>{{card.toughness}}</b></p>

											<span class="button alt icon ">
												Card power{{displayPower(card.power)}}
											</span>
										</section>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>

		</div>
</template>

<script>
import axios from 'axios'
const MAGIC_API_URL = "https://api.magicthegathering.io/v1/cards/"
export default {
    name: 'CardDetails',
    data: () => ({
        card: {},
    }),
    async created() {
        const { cardId } = this.$route.params
        const apiDetailsUrl = MAGIC_API_URL+cardId
		this.oneCard = await axios.get(apiDetailsUrl)
        this.card = this.oneCard.data.card
        console.log(this.card)
    },
	methods:{
        displayPower(nb) {
			let a = "🔥";
			return a.repeat(nb)
		},
		/*
		hasCoverUrl(card) {
			if (card?.coverUrl) {
				return card.coverUrl
			} else {
				return 'https://via.placeholder.com/100'
			}
		}
		*/
	},     
        
}
</script>

<style >
</style>
© 2022 GitHub, Inc.
Terms
Privacy
Security
Status
Docs
Contact GitHub
Pricing
API
Training
Blog
About
