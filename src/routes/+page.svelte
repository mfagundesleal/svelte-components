<script>
	import CardPerfil from "$lib/components/cards/card-perfil.svelte";
	import CardSideImgTxt from "$lib/components/cards/card-side-img_txt.svelte";
	import Card from "$lib/components/cards/card.svelte";
	import Accordion from "$lib/components/elements/accordion.svelte";
	import WrapBlock from "$lib/components/wrappers/wrap-block.svelte";
	import WrapFlex from "$lib/components/wrappers/wrap-flex.svelte";

    // Cores e demais estilos próprios do tema devem ser configurados no arquivo tailwind.config.cjs (consultar https://tailwindcss.com/docs/guides/sveltekit)
    // Fontes devem ser adicionadas por font-face em app.css.
</script>

<WrapBlock type="section" classes="gap-5 p-10">
    <div class="text-center">
        <h1 class="mb-2">Componentes Sveltekit com Tailwind CSS</h1>
        <p>Componentes baseados em Tailwind CSS. Bibliotecas externas podem ser utilizadas (como Daisy UI e Flowbite).</p>
    </div>
    <Accordion
        tituloAccordion="Componentes"
        sumClasses="items"
    >
        <WrapBlock classes="gap-10" slot="container">
            <h2>Cards</h2>
            <WrapBlock classes="gap-10">
                <div>
                    <h3>Card v0.0.1</h3>
                    <WrapFlex classes="mt-3 gap-5 flex-nowrap h-96">
                        <Card
                            srcBgCard="https://picsum.photos/500"
                            titleCard="Card v0.0.1 com imagem de background"
                            descCard="Imagem de background e descrição, sem classes adicionais. <strong>Possível de utilizar html dentro do props</strong>."
                        />
                        <Card
                            srcBgCard="https://picsum.photos/500"
                            titleCard="Card v0.0.1 com imagem de background e sem descrição"
                        />
                        <Card
                            srcImageCard="https://picsum.photos/500"
                            titleCard="Card v0.0.1 com imagem"
                            descCard="Imagem com descrição, sem classes adicionais. <strong>Possível de utilizar html dentro do props</strong>."
                        />
                    </WrapFlex>
                </div>
                <div>
                    <h3>Card para perfil com foto - v0.0.1</h3>
                    <WrapFlex classes="mt-3 gap-5 flex-nowrap">
                        <CardPerfil
                            cargo="Cargo do profissional"
                            src="https://picsum.photos/500"
                            titleCard="Nome da pessoa"
                            descCard="Card com descrição, sem utilização de classes adicionais, sem borda."
                        />
                    </WrapFlex>
                </div>
                <div>
                    <h3>Card para destaques - v0.0.1</h3>
                    <WrapFlex classes="mt-3 gap-5 flex-nowrap">
                        <CardSideImgTxt
                            src="https://picsum.photos/200"
                            titleCard="Nome do destaque, <a href='https://google.com.br' class='underline'>passível de utilizar um link</a>"
                            descCard="Detalhes acerca do destaque, texto <em>passível de conter elementos html.</em> Sem borda. Sem classes CSS adicionais."
                        />
                        <CardSideImgTxt
                            src="https://picsum.photos/200"
                            imgClasses="rounded-full shadow-xl shadow-black/20"
                            titleCard="Nome do destaque, <a href='https://google.com.br' class='underline'>passível de utilizar um link</a>"
                            descCard="Detalhes acerca do destaque, texto <em>passível de conter elementos html.</em> Imagem estilizada com classes adicionais."
                        />
                    </WrapFlex>
                </div>
            </WrapBlock>
        </WrapBlock>

    </Accordion>
    <Accordion
        tituloAccordion="Elementos"
        sumClasses="items"
    >
        <WrapBlock classes="gap-10" slot="container">
            <div>
                <h2>Accordion v0.0.1</h2>
                <WrapBlock classes="mt-5 gap-10">
                    <div>
                        <h3>Sem marcador (sumClasses="items")</h3>
                        <WrapFlex classes="mt-3 gap-5 flex-nowrap">
                            <Accordion
                                tituloAccordion="Distribui items e outros componentes internamente"
                                sumClasses="items"
                            >
                                <div slot="container">
                                    <p>Deve conter um container, e este container deve possuir um atributo slot="container"</p>
                                </div>
                            </Accordion>
                        </WrapFlex>
                    </div>
                    <div>
                        <h3>Com marcador (sem classes adicionais)</h3>
                        <WrapFlex classes="mt-3 gap-5 flex-nowrap">
                            <Accordion
                                tituloAccordion="Para FAQ, por exemplo"
                            >
                                <div slot="container">
                                    <p>Deve conter um container, e este container deve possuir um atributo slot="container"</p>
                                </div>
                            </Accordion>
                        </WrapFlex>
                    </div>
                    <div>
                        <h3>Com marcador e blur no background</h3>
                        <WrapFlex classes="mt-3 gap-5 h-40 flex-nowrap bg-[url('https://picsum.photos/1000')] w-full bg-no-repeat bg-cover">
                            <Accordion
                                tituloAccordion="Clique"
                                accContentClasses="only-blur"
                            >
                                <div slot="container">
                                    <p class="text-white">Deve conter um container, e este container deve possuir um atributo slot="container"</p>
                                </div>
                            </Accordion>
                        </WrapFlex>
                    </div>
                </WrapBlock>
            </div>
        </WrapBlock>

    </Accordion>
</WrapBlock>