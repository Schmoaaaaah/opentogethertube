<template>
	<div class="home">
		<v-container class="hero" fluid fill-height grid-list-md text-xs-center>
			<v-row align="center" justify="center" no-gutters>
				<div class="hero-text" cols="12" sm="10" md="8" lg="6">
					<h1>Enjoy Together.</h1>
					<span>
						Real-time syncronized playback. Optional voting system.<br>
						Dark theme. No sign up required. All Open Source.<br>
						It's never been easier to watch videos together.
					</span>
					<div class="hero-buttons">
						<v-btn elevation="12" x-large @click="createTempRoom">Create Room</v-btn>
						<v-btn elevation="12" x-large to="/rooms">Browse Rooms</v-btn>
						<v-btn elevation="12" x-large href="https://github.com/dyc3/opentogethertube">View Source</v-btn>
					</div>
				</div>
			</v-row>
		</v-container>
		<v-container class="content">
			<v-row>
				<v-col>
					<h1>Simple and Easy.</h1>
					<p>
						The original TogetherTube was loved for it's simple interface,
						and how easy it was to start watching videos right away.
						OpenTogetherTube aims to be just as easy, and then improve on
						top of that to make it even better.
					</p>
					<p>
						Currently, you can watch online videos with your friends from Youtube, Vimeo, Dailymotion, direct links to .mp4 videos, and
						<a href="https://github.com/dyc3/opentogethertube/labels/service%20support%20request">more are on the way</a>.
					</p>
				</v-col>
			</v-row>
			<v-row>
				<v-col>
					<h1>Core Features</h1>
					<v-row dense class="features">
						<v-col cols="12" sm="6" md="4">
							<v-card hover :height="cardHeight">
								<v-card-title>Syncronized Playback</v-card-title>
								<v-card-text>
									You hit play, and the video plays for everybody
									in the room. Simple as that.
								</v-card-text>
							</v-card>
						</v-col>
						<v-col cols="12" sm="6" md="4">
							<v-card hover :height="cardHeight">
								<v-card-title>Permanent Rooms</v-card-title>
								<v-card-text>
									You and the squad come here often? Avoid the hastle
									of sending out a new link every time. Permanent
									rooms get a custom url that doesn't change.
								</v-card-text>
							</v-card>
						</v-col>
						<v-col cols="12" sm="6" md="4">
							<v-card hover :height="cardHeight">
								<v-card-title>Dark Theme</v-card-title>
								<v-card-text>
									Watching Vine compilations late at night?
									OpenTogetherTube has a dark theme by default so
									your eyes won't suffer.
								</v-card-text>
							</v-card>
						</v-col>
						<v-col cols="12" sm="6" md="4">
							<v-card hover :height="cardHeight">
								<v-card-title>Room Permissions (WIP)</v-card-title>
								<v-card-text>
									Tired of random goofballs joining your room and
									adding lots of loud videos to your chill lofi hip-hop
									listening session? Just block them from adding videos.
								</v-card-text>
							</v-card>
						</v-col>
						<v-col cols="12" sm="6" md="4">
							<v-card hover :height="cardHeight">
								<v-card-title>Voting System</v-card-title>
								<v-card-text>
									Can't decide what to watch next? Switch the queue
									to the vote system and let democracy do what it
									does best.
								</v-card-text>
							</v-card>
						</v-col>
						<v-col cols="12" sm="6" md="4">
							<v-card hover :height="cardHeight">
								<v-card-title>Playlist Copying</v-card-title>
								<v-card-text>
									Add entire playlists or channels to the video queue
									all at once so you don't have to sit there adding
									each video to the queue one by one. It's the best
									way to binge watch that new channel with your friends.
								</v-card-text>
							</v-card>
						</v-col>
					</v-row>
				</v-col>
			</v-row>
			<v-row>
				<v-col>
					<em style="opacity: 0.5">Disclaimer: The OpenTogetherTube project is not associated with TogetherTube nor Watch2Gether.</em>
				</v-col>
			</v-row>
			<v-footer>
				<v-container pa-0>
					<v-row no-gutters align="center" justify="center">
						{{ new Date().getFullYear() }} - <a class="side-pad" href="https://carsonmcmanus.com/">Carson McManus</a> - Made in America - Special Thanks to <a class="side-pad" href="https://softe.club">SEC</a> @ Stevens
					</v-row>
					<v-row no-gutters align="center" justify="center">
						<router-link to="/privacypolicy">Privacy Policy</router-link>
					</v-row>
				</v-container>
			</v-footer>
		</v-container>
	</div>
</template>

<script>
import RoomUtilsMixin from "@/mixins/RoomUtils.js";

export default {
	name: 'home',
	mixins: [RoomUtilsMixin],
	data() {
		return {};
	},
	computed: {
		cardHeight() {
			return 180;
		},
	},
};
</script>

<style lang="scss" scoped>
@import "../variables.scss";

.home {
	width: 100%;
}

.hero {
	background: linear-gradient(217deg, rgb(125, 74, 239), rgb(227,141,174) 30%, rgb(247, 208, 109));
	color: white;
	font-size: 22px;
	height: 100vh;
	min-height: 350px;
	display: flex;

	h1 {
		font-size: 52px;
	}

	@media only screen and (max-width: $xs-max) {
		h1 {
			font-size: 48px;
		}
	}

	.hero-text {
		display: flex;
		flex-direction: column;

		.hero-buttons {
			display: flex;
			flex-direction: row;
			justify-content: space-between;

			.v-btn {
				background: transparent !important;
				// margin: 0 10px;
				@media only screen and (max-width: $md-max) {
					margin-top: 22px;
				}
			}

			@media screen and (max-width: $sm-max) {
				flex-direction: column;
			}
		}
	}
}
</style>
