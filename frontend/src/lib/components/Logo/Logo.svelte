<script lang="ts">
	// AT-GRCA: logo de Athanor Tech (versión para fondo claro y para modo oscuro).
	import logo from '#lib/assets/athanor-logo.png';
	import logoOscuro from '#lib/assets/athanor-logo-oscuro.png';

	interface Props {
		height?: number;
		width?: number;
	}

	let { height = 200, width = 200 }: Props = $props();
</script>

<img class="c dark:hidden" {height} {width} src={logo} alt="AT-GRCA · Athanor Tech" data-testid="logo-image" />
<img class="c hidden dark:block" {height} {width} src={logoOscuro} alt="AT-GRCA · Athanor Tech" />
