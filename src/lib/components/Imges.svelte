<script lang="ts">
	interface imgList {
		title: string;
		link: {
			text: string;
			url: string;
		};
	}

	let imgList: imgList[] = [
		{
			title: 'Zadbaj o posiłki dla pracowników',
			link: {
				text: 'Utwórz konto firmowe',
				url: '//www.uber.com/business/eats'
			}
		},
		{
			title: 'Ty zapewniasz menu, a my dostawę',
			link: {
				text: 'Dodaj swoją restaurację',
				url: '//merchants.ubereats.com/s/signup/'
			}
		},
		{
			title: 'Realizuj dostawy z Uber Eats',
			link: {
				text: 'Zarejestruj się, aby realizować dostawy',
				url: '//www.uber.com/drive/delivery/'
			}
		}
	];
</script>

<div>
	{#each imgList as img, i}
		<a href={img.link.url}>
			<img src="/img/{i}.webp" alt="" />
			<p class="title">{img.title}</p>
			<p class="link">{img.link.text}</p>
		</a>
	{/each}
</div>

<style lang="scss">
	div {
		display: flex;
		justify-content: space-between;

		@media (max-width: 500px) {
			flex-direction: column;
			gap: 32px;
		}

		a {
			padding: 0 12px;

			@media (max-width: 500px) {
				padding: 0;
			}

			img {
				width: 100%;
			}

			.title {
				font-size: 28px;
				font-weight: 700;

				@media (max-width: 500px) {
					font-size: 24px;
				}
			}

			.link {
				text-decoration: underline;
			}
		}
	}
</style>
