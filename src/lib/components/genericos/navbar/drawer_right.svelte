<script>
	/* 
		Drawer, menu responsivo - v0.0.1
		https://daisyui.com/components/drawer/

		Props:
			- linkPagina: link para a página inicial atribuído à logomarca.
			- srcLogo: caminho para a imagem da logomarca.
			- buttonClasses: possibilidade de estilizar a tag label que aciona o menu mobile (útil quando não há slot button definido).
		Slots:
			- button: botão que aciona o menu mobile.
			- itens-menu (repete no drawer-side): itens do menu de navegação.
			- conteudo: conteúdo da página.
	*/

	export let linkPagina = "";
	export let srcLogo = "";
	export let buttonClasses = "";
</script>
<div class="drawer drawer-end">
	<!-- input que aciona o menu mobile -->
	<input id="my-drawer-4" type="checkbox" class="drawer-toggle" />
	<!-- conteúdo interno do drawer (que é levemente empurrado à direita ao abrir o menu) -->
	<div class="drawer-content flex flex-col">
		<!-- Navbar -->
		<div class="w-full navbar min-h-200 mb-10 justify-between container mx-auto">
			<!-- label/botão do input que aciona o menu -->
			<label for="my-drawer-4" class="lg:hidden {buttonClasses}">
				<slot name="button"/>
			</label>
			<!-- logo -->
			<a href="{linkPagina}" class="w-1/2 h-auto min-w-100 max-w-200">
                <img src="{srcLogo}" alt="Logomarca">
            </a>
			<!-- menu horizontal em telas maiores -->
			<nav class="flex-none hidden lg:block">
				<ul class="menu menu-horizontal">
					<!-- itens do menu -->
					<slot name="itens-menu"/>
				</ul>
			</nav>
		</div>
		<!-- Conteúdo da página -->
		<slot name="conteudo"/>
	</div>
	<!-- menu vertical aberto ao lado esquerdo em telas menores -->
	<div class="drawer-side">
		<!-- overlay (fica acima do conteúdo interno do drawer) -->
		<label for="my-drawer-4" class="drawer-overlay" />
		<ul class="menu p-4 overflow-y-auto w-80 bg-base-100">
			<!-- itens do menu -->
			<slot name="itens-menu"/>
		</ul>
	</div>
</div>