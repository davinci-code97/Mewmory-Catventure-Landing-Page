<script lang="ts">
	import language_preference, { display_text, LayoutLanguage } from "$lib/components/language/config";

	import backgroundVideo from "$lib/assets/videos/loading_screen.mp4";

	import CoverImg from "$lib/assets/images/cover.png";
	import MainMenuImg from "$lib/assets/images/1.png";
	import MidAutumnImg from "$lib/assets/images/1.png";
	import Img3 from "$lib/assets/images/3.png";
	import Img4 from "$lib/assets/images/4.png";

	import footer_bg_img from "$lib/assets/images/bg.png";
	import mewlab from "$lib/assets/images/Mewlab.jpg";

	let scrollY = 0;
</script>

<svelte:head>
	<title>Mewmory Catventure</title>
</svelte:head>

<svelte:window bind:scrollY={scrollY} />

<header>
	<div class="translate-wrapper">
		<button
			onclick={() => {
				let language: LayoutLanguage;

				switch ($language_preference.language) {
					case LayoutLanguage.English:
						language = LayoutLanguage.Vietnamese;
						break;
					case LayoutLanguage.Vietnamese:
						language = LayoutLanguage.English;
						break;
					default:
						language = LayoutLanguage.Vietnamese;
						break;
				}

				$language_preference.language = language;
			}}
		>
			{display_text(
				$language_preference,
				"This page is also available in English. Read this page in English.",
				"Trang này cũng có phiên bản tiếng Việt. Đọc trang này bằng tiếng Việt.",
			)}
		</button>
	</div>
</header>

<div class="cover" style="background-image: url({CoverImg}); background-size: cover; background-position: center;">
	<video autoplay muted loop id="background-video">
		<source src={backgroundVideo} type="video/mp4" />
	</video>
</div>

<h1 class="slide-up-heading">
	{display_text(
		$language_preference,
		"Chơi vui khắp chốn - Học hỏi khắp nơi - Tuổi thơ rạng ngời",
		"Play with joy - Learn with wonder - Let childhood shine",
	)}
</h1>

<!-- 1 -->
<div class="two-column-layout">
	<div class="column">
		<img src={MainMenuImg} alt="Main Menu" />
	</div>
	{#if scrollY > 250}
	<div class="column slide-up-heading">
		<h2>
			{display_text(
				$language_preference,
				"Khám phá thế giới muôn màu cùng chú mèo Zera",
				"Explore a colorful world with Zera the cat",
			)}
		</h2>
		<p>
			{display_text(
				$language_preference,
				"Những câu chuyện kỳ thú và những bài học ý nghĩa đang chờ bạn đồng hành cùng Zera để khám phá thế giới quanh mình!",
				"Amazing stories and meaningful lessons are waiting for you to accompany Zera to explore the world around you!",
			)}
		</p>
	</div>
	{/if}
</div>

<!-- 2 -->
<div class="two-column-layout">
	{#if scrollY > 800}
	<div class="column slide-up-heading">
		<h2>{display_text($language_preference, "Mini game dễ chơi, đầy màu sắc Việt", "Colorful and Easy Mini Games")}</h2>
		<p>
			{display_text(
				$language_preference,
				"Các trò chơi quen thuộc, gần gũi trong đời sống hằng ngày được thổi hồn mới đầy sáng tạo — vừa vui nhộn vừa mang đậm hơi thở văn hóa Việt.",
				"Familiar, everyday games are given a new, creative life — both fun and imbued with Vietnamese culture.",
			)}
		</p>
	</div>
	{/if}
	<div class="column">
		<img src={MidAutumnImg} alt="Food Collection" />
	</div>
</div>

<!-- 3 -->
<div class="two-column-layout">
	<div class="column">
		<img src={Img3} alt="Fix Sword" />
	</div>
	{#if scrollY > 1200}
	<div class="column slide-up-heading">
		<h2>
			{display_text(
				$language_preference,
				"Nhân vật đáng yêu, gắn liền với truyện dân gian",
				"Adorable characters from folk tales",
			)}
		</h2>
		<p>
			{display_text(
				$language_preference,
				"Người bạn đồng hành của bạn là chú mèo vàng Zera năng động và dí dỏm. Với sự tinh nghịch và đáng yêu của Zera, mỗi phút chơi đều trở nên thật vui và ấm áp.",
				"Meet Zera — your cheerful golden cat buddy! Full of mischief and cuteness, Zera makes every playtime a burst of fun and warmth.",
			)}
		</p>
	</div>
	{/if}
</div>

<!-- 4 -->
<div class="two-column-layout">
	{#if scrollY > 1900}
	<div class="column slide-up-heading">
		<h2>
			{display_text(
				$language_preference,
				"Vừa giải trí, vừa học tiếng Anh và kiến thức văn hoá",
				"Learning English and Cultural Knowledge through Entertainment",
			)}
		</h2>
		<p>
			{display_text(
				$language_preference,
				"Không chỉ đơn thuần là trò chơi, mà qua từng hành trình khám phá, bạn sẽ học thêm nhiều điều thú vị về ngôn ngữ, văn hóa và thế giới xung quanh — giúp nuôi dưỡng trí tò mò và niềm vui học hỏi mỗi ngày.",
				"It's not just about games — every adventure helps you explore new words, cultures, and wonders of the world, sparking curiosity and making learning fun every day!",
			)}
		</p>
	</div>
	{/if}
	<div class="column">
		<img src={Img4} alt="Stories Archive" />
	</div>
</div>

<!-- Footer -->
<footer style="background-image: url({footer_bg_img}); background-size: cover; background-position: center;">
	<img src={mewlab} alt="Mewlab Logo" style="display: block; margin: 0 auto; width: 150px; height: auto;" />
	<h3>Mewlab</h3>
	<a
		href="https://www.facebook.com/profile.php?id=61581194390336"
		target="_blank"
		rel="noopener noreferrer"
		aria-label="Visit Mewlab's Facebook"
	>
		<svg
			xmlns="http://www.w3.org/2000/svg"
			x="0px"
			y="0px"
			width="24"
			height="24"
			viewBox="0 0 50 50"
			style="fill:#FFFFFF;"
		>
			<path
				d="M25,3C12.85,3,3,12.85,3,25c0,11.03,8.125,20.137,18.712,21.728V30.831h-5.443v-5.783h5.443v-3.848 c0-6.371,3.104-9.168,8.399-9.168c2.536,0,3.877,0.188,4.512,0.274v5.048h-3.612c-2.248,0-3.033,2.131-3.033,4.533v3.161h6.588 l-0.894,5.783h-5.694v15.944C38.716,45.318,47,36.137,47,25C47,12.85,37.15,3,25,3z"
			></path>
		</svg>
	</a>

	<a
		href="https://www.instagram.com/mewmory.catventure/"
		target="_blank"
		rel="noopener noreferrer"
		aria-label="Visit Mewlab's Instagram"
	>
		<span>
			<svg width="24" height="24" fill="currentColor" viewBox="0 0 16 16">
				<path
					d="M8 0C5.829 0 5.556.01 4.703.048 3.85.088 3.269.222 2.76.42a3.9 3.9 0 0 0-1.417.923A3.9 3.9 0 0 0 .42 2.76C.222 3.268.087 3.85.048 4.7.01 5.555 0 5.827 0 8.001c0 2.172.01 2.444.048 3.297.04.852.174 1.433.372 1.942.205.526.478.972.923 1.417.444.445.89.719 1.416.923.51.198 1.09.333 1.942.372C5.555 15.99 5.827 16 8 16s2.444-.01 3.298-.048c.851-.04 1.434-.174 1.943-.372a3.9 3.9 0 0 0 1.416-.923c.445-.445.718-.891.923-1.417.197-.509.332-1.09.372-1.942C15.99 10.445 16 10.173 16 8s-.01-2.445-.048-3.299c-.04-.851-.175-1.433-.372-1.941a3.9 3.9 0 0 0-.923-1.417A3.9 3.9 0 0 0 13.24.42c-.51-.198-1.092-.333-1.943-.372C10.443.01 10.172 0 7.998 0zm-.717 1.442h.718c2.136 0 2.389.007 3.232.046.78.035 1.204.166 1.486.275.373.145.64.319.92.599s.453.546.598.92c.11.281.24.705.275 1.485.039.843.047 1.096.047 3.231s-.008 2.389-.047 3.232c-.035.78-.166 1.203-.275 1.485a2.5 2.5 0 0 1-.599.919c-.28.28-.546.453-.92.598-.28.11-.704.24-1.485.276-.843.038-1.096.047-3.232.047s-2.39-.009-3.233-.047c-.78-.036-1.203-.166-1.485-.276a2.5 2.5 0 0 1-.92-.598 2.5 2.5 0 0 1-.6-.92c-.109-.281-.24-.705-.275-1.485-.038-.843-.046-1.096-.046-3.233s.008-2.388.046-3.231c.036-.78.166-1.204.276-1.486.145-.373.319-.64.599-.92s.546-.453.92-.598c.282-.11.705-.24 1.485-.276.738-.034 1.024-.044 2.515-.045zm4.988 1.328a.96.96 0 1 0 0 1.92.96.96 0 0 0 0-1.92m-4.27 1.122a4.109 4.109 0 1 0 0 8.217 4.109 4.109 0 0 0 0-8.217m0 1.441a2.667 2.667 0 1 1 0 5.334 2.667 2.667 0 0 1 0-5.334"
				/>
			</svg>
		</span>
	</a>

	<a
		href="https://www.tiktok.com/@chu_meo_zera?_t=ZS-8zrGVkTnEMy&_r=1"
		target="_blank"
		rel="noopener noreferrer"
		aria-label="Visit Mewlab's TikTok"
	>
		<svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="24" height="24" viewBox="0,0,256,256">
			<g
				fill="#ffffff"
				fill-rule="nonzero"
				stroke="none"
				stroke-width="1"
				stroke-linecap="butt"
				stroke-linejoin="miter"
				stroke-miterlimit="10"
				stroke-dasharray=""
				stroke-dashoffset="0"
				font-family="none"
				font-weight="none"
				font-size="none"
				text-anchor="none"
				style="mix-blend-mode: normal"
				><g transform="scale(5.12,5.12)"
					><path
						d="M41,4h-32c-2.757,0 -5,2.243 -5,5v32c0,2.757 2.243,5 5,5h32c2.757,0 5,-2.243 5,-5v-32c0,-2.757 -2.243,-5 -5,-5zM37.006,22.323c-0.227,0.021 -0.457,0.035 -0.69,0.035c-2.623,0 -4.928,-1.349 -6.269,-3.388c0,5.349 0,11.435 0,11.537c0,4.709 -3.818,8.527 -8.527,8.527c-4.709,0 -8.527,-3.818 -8.527,-8.527c0,-4.709 3.818,-8.527 8.527,-8.527c0.178,0 0.352,0.016 0.527,0.027v4.202c-0.175,-0.021 -0.347,-0.053 -0.527,-0.053c-2.404,0 -4.352,1.948 -4.352,4.352c0,2.404 1.948,4.352 4.352,4.352c2.404,0 4.527,-1.894 4.527,-4.298c0,-0.095 0.042,-19.594 0.042,-19.594h4.016c0.378,3.591 3.277,6.425 6.901,6.685z"
					></path></g
				></g
			>
		</svg>
	</a>

	<p>2025 Mewlab</p>
</footer>

<style>
	:global(body) {
		font-family: sans-serif;
		font-weight: bold;
	}

	header {
		position: fixed;
		top: 0;
		z-index: 1000;
		background-color: var(--white);
		width: 100%;
		transition: transform 0.3s ease;
	}

	.translate-wrapper {
		padding-left: 5px;
		font-family:
			system-ui,
			-apple-system,
			BlinkMacSystemFont,
			"Segoe UI",
			Roboto,
			Oxygen,
			Ubuntu,
			Cantarell,
			"Open Sans",
			"Helvetica Neue",
			sans-serif;

		button {
			text-decoration: underline;
			cursor: pointer;
		}
	}

	.cover {
		position: relative;
		width: 100%;
		height: 75vh;
		overflow: hidden;
	}

	#background-video {
		width: 100%;
		margin-top: -20%;
	}

	h1 {
		text-align: center;
		font-size: 3rem;
		margin: 1em 0;
		color: darkblue;
	}

	.two-column-layout {
		display: grid;
		grid-template-columns: 30% 30%; /* Creates two equal-width columns */
		gap: 20px; /* Adds space between columns */
		align-items: center; /* Vertically centers content */
		justify-content: center;
		margin-top: 10%;
		margin-bottom: 10%;
	}

	.column {
		/* Optional styling for individual columns */
		padding: 15px;
	}

	h2 {
		font-size: 2rem;
		margin-bottom: 10px;
		color: darkblue;
	}

	p {
		font-size: 1.2rem;
		line-height: 1.6;
		color: darkslategrey;
	}

	footer {
		width: 100%;
		height: auto;
		text-align: center;
		color: white;
		padding: 20px 0;
		margin-top: 20px;
	}

	h3 {
		text-align: center;
		font-size: 5rem;
		padding: 10px 0;
		color: darkblue;
	}

	.slide-up-heading {
		animation: slideUp 1s cubic-bezier(0.4, 0, 0.2, 1) 1;
		will-change: transform, opacity;
	}

	@keyframes slideUp {
		from {
			transform: translateY(100%);
			opacity: 0;
		}
		to {
			transform: translateY(0);
			opacity: 1;
		}
	}
</style>
