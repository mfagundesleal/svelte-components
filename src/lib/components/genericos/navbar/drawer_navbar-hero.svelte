<script>
    /*
        Navbar e seção hero com background, para uso com menu drawer

        Props:
			- linkPagina: link para a página inicial atribuído à logomarca.
			- srcLogo: caminho para a imagem da logomarca.
			- buttonClasses: possibilidade de estilizar a tag label que aciona o menu mobile (útil quando não há slot button definido).
			- bgClasses: possibilita editar o posicionamento do background da seção hero.
			- bgUrl: url da imagem de background.
        Slots:
			- button: botão que aciona o menu mobile.
			- itens_menu-horizontal: itens do menu de navegação.
            - hero: seção hero com background que envolve o cabeçalho (se houver).
    */

    export let linkPagina = "";
	export let srcLogo = "";
	export let buttonClasses = "";
	export let bgClasses = "";
	export let bgUrl="";


</script>
<div class="bg-cover {bgClasses}" style="background-image: url('{bgUrl}');">
    <!-- Navbar -->
    <div class="w-full navbar min-h-200 mb-10 justify-between container mx-auto">
        <!-- logo -->
        <a href="{linkPagina}" class="w-1/2 h-auto min-w-[10rem] max-w-[15rem]">
            <img src="{srcLogo}" alt="Logomarca">
        </a>
        <!-- label/botão do input que aciona o menu -->
        <label for="my-drawer-4" class="lg:hidden {buttonClasses}">
            <slot name="button"/>
        </label>
        <!-- menu horizontal em telas maiores -->
        <nav class="flex-none hidden lg:block">
            <ul class="menu menu-horizontal">
                <!-- itens do menu -->
                <slot name="itens_menu-horizontal"/>
            </ul>
        </nav>
    </div>
    <!-- conteúdo da seção hero -->
    <slot name="hero"></slot>
</div>