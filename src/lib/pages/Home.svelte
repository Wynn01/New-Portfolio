<script>
  	import Anchor from "$lib/components/Anchor.svelte";
	import IconButton from "$lib/components/IconButton.svelte";
	import Fa from 'svelte-fa'
	import { faGithub,faFacebook,faLine } from '@fortawesome/free-brands-svg-icons';
	import { faEnvelope } from '@fortawesome/free-solid-svg-icons';
	

	import Modal from "$lib/components/Modal.svelte";;
	let showModal = false;

  let color = "text-primary-300";
  let hover = "sm:hover:text-amber-500";
  let colorClass = `${color} ${hover}`;
  let spacingClass = "mx-5";
  let sizeClass = "h-8 w-8";

	
</script>

<svelte:head>
	<title>Pakorn Kanjanapan - Main page</title>
</svelte:head>
<Anchor id = "home"/>
<main class="flex flex-col items-center justify-center bg-center bg-no-repeat bg-cover page lg:bg-fixed bg-neutral-600 bg-blend-soft-light dark:bg-blend-soft-light dark:bg-neutral-700 text-white text-center"
id="bg">
	<h1 class = "font-mono text-6xl"> <span class = "text-amber-500 font-bold text">Hi!</span> <br /> I'm Pakorn Kanjanapan </h1>
	<h2 class = "font-mono text-3xl">Beginner level <span class = "text-amber-500 font-bold">Front-end </span>Web Developer </h2>
	<div class="icons flex">
		
		<div class = "icon"
			role="button"
			tabindex="0"
			on:keypress={() => (showModal = true)}
			on:click={() => (showModal = true)}>
			
			
			<div class="icon">
				<Fa icon={faEnvelope} />
			</div>
		</div>

			

		<a
			href="https://github.com/Wynn01"
			aria-label="GitHub"
			target="_blank"
			rel="noopener noreferrer"
		>
			<div class="icon">
				<Fa icon={faGithub} />
			</div>
		</a>
		<a
			href="https://www.facebook.com/winpk.p"
			aria-label="Facebook"
			target="_blank"
			rel="noopener noreferrer"
		>
			<div class="icon">
				<Fa icon={faFacebook} />
			</div>
		</a>
		<a
			href="https://linevoom.line.me/user/_dUzuCVS3bc-J1LUBlNQj-RZmwXWZEMKH_dsU1_Q?utm_medium=windows&utm_source=desktop&utm_campaign=Profile"
			aria-label="Medium"
			target="_blank"
			rel="noopener noreferrer"
		>
			<div class="icon">
				<Fa icon={faLine} />
			</div>
		</a>
	</div>
	<div>
		<IconButton link="#about" name="scroll down" newTab={false}>
		  <svg
			aria-hidden="true"
			focusable="false"
			data-prefix="fas"
			data-icon="chevron-circle-down"
			class="svg-inline--fa fa-chevron-circle-down fa-w-16 {colorClass} my-20 {sizeClass}"
			role="img"
			xmlns="http://www.w3.org/2000/svg"
			viewBox="0 0 512 512"
		  >
			<path
			  fill="currentColor"
			  d="M504 256c0 137-111 248-248 248S8 393 8 256 119 8 256 8s248 111 248 248zM273 369.9l135.5-135.5c9.4-9.4 9.4-24.6 0-33.9l-17-17c-9.4-9.4-24.6-9.4-33.9 0L256 285.1 154.4 183.5c-9.4-9.4-24.6-9.4-33.9 0l-17 17c-9.4 9.4-9.4 24.6 0 33.9L239 369.9c9.4 9.4 24.6 9.4 34 0z"
			/>
		  </svg>
		</IconButton>
	  </div>
</main>

<Modal bind:showModal>
	<h2 slot="header">
		Email
	</h2>
	<div slot = "info">pakorn4326@gmail.com</div>
	<a href="mailto:pakorn4326@gmail.com"><button class = "button" >Send mail</button></a>
	
	
</Modal>

<style>
 	#bg {
    /* The image used */
    background-image: url("wizard.png");
 	}	
	
	main {
		min-height: calc(100vh - 4rem);
   		width: 100%;
	}	
	
	.icons {
		display: flex !important;
		justify-content: center !important;
		align-items: center;
		gap: 20px;
		cursor: pointer;
		font-size: 30px;
		max-width: 200px;
		margin: 50px auto 0;
	}

	.icon:hover {
		color: orange;
		transition: all 0.5s;
		transform: rotate(15deg);
	}
	.button {
		border-radius: 2px;
	}
	.button:hover {
		color: black;
		background-color: orange;
	}

</style>
