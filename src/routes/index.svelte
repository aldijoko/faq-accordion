<script>
	let isOpen = false;

	const accordionList = [
		{
			name: 'How many team members can I invite?',
			subtitle:
				'You can invite up to 2 additional users on the Free plan. There is no limit on team members for the Premium plan.'
		},
		{
			name: 'What is the maximum file upload size?',
			subtitle: 'No more than 2GB. All files in your account must fit your allotted storage space.'
		},
		{
			name: 'How do I reset my password?',
			subtitle:
				'Click “Forgot password” from the login page or “Change password” from your profile page. A reset link will be emailed to you.'
		},
		{
			name: 'Can I cancel my subscription?',
			subtitle: 'Yes! Send us a message and we’ll process your request no questions asked.'
		},
		{
			name: 'Do you provide additional support?',
			subtitle:
				'Chat and email support is available 24/7. Phone lines are open during normal business hours.'
		}
	];
</script>

<div class="card">
	<div class="img-left">
		<img class="img-box" src="images/illustration-box-desktop.svg" alt="" />
		<img class="img-woman" src="images/illustration-woman-online-desktop.svg" alt="" />
	</div>
	<div class="accordion-right">
		<h1>FAQ</h1>
		{#each accordionList as al}
			<div class="accordion">
				<div 
                class="accordion-header"
                aria-expanded={isOpen === al.name}
                class:is-active={isOpen === al.name}
                on:click={() => {
                    if(isOpen !== al.name){
                        isOpen = al.name
                    }
                }}>
					<p>{al.name}</p>
					<button class="btn">
						<img src="images/icon-arrow-down.svg" alt="" />
					</button>
				</div>
				{#if isOpen === al.name}
					<div class="text">
						<p class="answer">
							{al.subtitle}
						</p>
					</div>
				{/if}
			</div>
		{/each}
		
        <div class="attribution">
            Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>. 
            Coded by <a href="#">Aldi Joko</a>.
          </div>
	</div>
</div>

<style>
     .attribution {
        font-size: 11px;
        text-align: center;
        margin-top: 20px;
      }
      .attribution a {
        color: hsl(197, 98%, 47%);
      }

	.card {
		display: flex;
		align-items: center;
		justify-content: center;
		min-height: 450px;
		background-color: #fff;
		width: 900px;
		border-radius: 25px;
		/* padding-top: 5%; */
		/* margin: 10% auto; */
	}

	.img-left {
		width: 100%;
		height: 100%;
		position: relative;
	}

	.img-box {
		position: absolute;
		top: 40%;
		left: -26px;
		z-index: 2;
	}


	.accordion-right {
		width: 100%;
		height: 100%;
		padding: 60px 50px;
	}

	.accordion-right h1 {
		margin-bottom: 20px;
		font-size: 28px;
	}

	.accordion {
		/* padding-top: 20px; */
		border-bottom: 1px solid #e6e6e6;
		cursor: pointer;
	}

	.accordion-header {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.accordion-header p {
		font-size: 15px;
	}

	.accordion-header p:hover {
		color: hsl(14, 88%, 65%);
	}

	.text {
		font-size: 11px;
		line-height: 1.5;
		color: hsl(240, 6%, 50%);
		margin-bottom: 10px;
	}

	.btn {
		border: none;
		padding: 1rem;
		background: none;
		cursor: pointer;
	}

	[aria-expanded='true'] .btn {
		transform: rotate(0.5turn);
	}

    .is-active {
		font-weight: 700;
	}

	/* @media screen and (max-width: 850px) {
		.card {
			width: 60%;
			display: flex;
			flex-direction: column;
		}

		.img-box {
			display: none;
		}

		.img-left {
			background: none;
			width: 100%;
			position: relative;
			height: 100%;
		}

		.img-woman {
			position: absolute;
			display: block;
			width: 50%;
			top: -62px;
			left: 68px;
		}

		.accordion-right {
			display: flex;
			flex-direction: column;
		}
	} */
</style>
