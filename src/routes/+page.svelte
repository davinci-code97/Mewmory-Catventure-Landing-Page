<script lang="ts">
	import language_preference, { display_text, LayoutLanguage } from "$lib/components/language/config";

	import backgroundVideo from "$lib/assets/videos/loading_screen.mp4";

	import MainMenuImg from "$lib/assets/images/main_menu.png";
	import food_collection_img from "$lib/assets/images/food_collection.png";
	import fix_sword_img from "$lib/assets/images/fix_sword.png";
	import stories_archive_img from "$lib/assets/images/stories_archive.png";
	import footer_bg_img from "$lib/assets/images/bg.png";

</script>

<svelte:head>
	<title>Mewmory Catventure</title>
</svelte:head>

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

<video autoplay muted loop id="background-video">
	<source src={backgroundVideo} type="video/mp4" />
</video>

<h1>{display_text($language_preference, "Bữa tiệc Buffet văn hoá Việt", "A Vietnamese Cultural Buffet")}</h1>

<div class="two-column-layout">
	<div class="column">
		<img src={MainMenuImg} alt="Main Menu" />
	</div>
	<div class="column">
		<h2>{display_text($language_preference, "Tiêu đề 1", "Title 1")}</h2>
		<p>{display_text($language_preference, "Nội dung 1", "Content 1")}</p>
	</div>
</div>

<div class="two-column-layout">
	<div class="column">
		<h2>{display_text($language_preference, "Tiêu đề 2", "Title 2")}</h2>
		<p>{display_text($language_preference, "Nội dung 2", "Content 2")}</p>
	</div>
	<div class="column">
		<img src={food_collection_img} alt="Food Collection" />
	</div>
</div>

<div class="two-column-layout">
	<div class="column">
		<img src={fix_sword_img} alt="Fix Sword" />
	</div>
	<div class="column">
		<h2>{display_text($language_preference, "Tiêu đề 3", "Title 3")}</h2>
		<p>{display_text($language_preference, "Nội dung 3", "Content 3")}</p>
	</div>
</div>

<div class="two-column-layout">
	<div class="column">
		<h2>{display_text($language_preference, "Tiêu đề 4", "Title 4")}</h2>
		<p>{display_text($language_preference, "Nội dung 4", "Content 4")}</p>
	</div>
	<div class="column">
		<img src={stories_archive_img} alt="Stories Archive" />
	</div>
</div>

<footer style="background-image: url({footer_bg_img});
		width: 100%;
		height: auto;">
	<h3>Mewlab</h3>
</footer>


<style>
	:global(body) {
		font-family: Arial, Helvetica, sans-serif;
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

	video {
		width: 100%;
	}

	h1 {
		text-align: center;
		font-size: 3rem;
		margin: 20px 0;
	}

	.two-column-layout {
		display: grid;
		grid-template-columns: 1fr 1fr; /* Creates two equal-width columns */
		gap: 20px; /* Adds space between columns */
	}

	.column {
		/* Optional styling for individual columns */
		padding: 15px;
	}

	h2 {
		font-size: 2rem;
		margin-bottom: 10px;
	}

	p {
		font-size: 1.2rem;
		line-height: 1.6;
	}

	h3 {
		text-align: center;
		font-size: 5em;
		padding: 10px 0;
	}
</style>
