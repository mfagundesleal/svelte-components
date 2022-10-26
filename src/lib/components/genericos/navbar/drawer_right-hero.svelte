<script>
	/* 
		Drawer, menu responsivo - v0.0.1
		https://daisyui.com/components/drawer/

		Slots:
			- itens_menu-side: itens do menu de navegação vertical do menu drawer.
			- conteudo: conteúdo da página.
	*/
</script>
<div class="drawer drawer-end">
	<!-- input que aciona o menu mobile -->
	<input id="my-drawer-4" type="checkbox" class="drawer-toggle" />
	<!-- conteúdo interno do drawer (que é levemente empurrado à direita ao abrir o menu) -->
	<div class="drawer-content flex flex-col">
		<!-- Conteúdo da página -->
		<slot name="conteudo"/>
	</div>
	<!-- menu vertical aberto ao lado esquerdo em telas menores -->
	<div class="drawer-side">
		<!-- overlay (fica acima do conteúdo interno do drawer) -->
		<label for="my-drawer-4" class="drawer-overlay" />
		<ul class="menu p-4 overflow-y-auto w-80 bg-base-100">
			<!-- itens do menu -->
			<slot name="itens_menu-vertical"/>
		</ul>
	</div>
</div>