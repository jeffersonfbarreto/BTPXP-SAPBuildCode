[![solution](https://flat.badgen.net/badge/solution/available/green?icon=github)](https://github.com/SAP-samples/teched2023-AD265/tree/code/exercises/ex2)
[![demo](https://flat.badgen.net/badge/demo/deployed/blue?icon=github)](https://sap-samples.github.io/teched2023-AD283v/ex2/test/flpSandbox-cdn.html?sap-ui-xx-viewCache=false#keepcoolsensormanager-display)

# Exercício 2 - Adicionar primeiro conteúdo

Neste exercício, você adicionará algum conteúdo ao seu aplicativo. Uma exibição da UI5 mostrando vários sensores de temperatura será a primeira parte do seu aplicativo.

## Exercício 2.1 – Entender as exibições XML

Depois de concluir essas etapas, você terá escrito sua primeira exibição de UI5. Mas antes de criar conteúdo, vamos dar uma olhada nas visualizações pré-criadas - primeiro na view raiz do aplicativo localizada em `sensormanager/webapp/view/App.view.xml`. Ele contém apenas um único controle `App`, que é um controle UI5 especial, que pode ser usado para exibir e navegar entre páginas diferentes. Veremos como as páginas são adicionadas e como essa navegação funciona, quando dermos uma olhada no *routing* mais tarde.

```xml
<mvc:View controllerName="keepcool.sensormanager.controller.App"
    displayBlock="true"
    xmlns:mvc="sap.ui.core.mvc"
    xmlns="sap.m">
    <App id="app">
    </App>
</mvc:View>
```

A segunda view, `sensormanager/webapp/view/Sensors.view.xml`, contém um único controle `Page` com conteúdo vazio:

```xml
<mvc:View controllerName="keepcool.sensormanager.controller.Sensors"
    xmlns:mvc="sap.ui.core.mvc"
    xmlns="sap.m">
    <Page id="page" title="{i18n>title}">
    </Page>
</mvc:View>

```

> #### 🧑‍🎓 Explanation
> As views XML são a maneira recomendada (mas não a única) no SAPUI5 para definir a estrutura da interface do usuário. As tags com letras maiúsculas representam controles UI5 - elementos da interface do usuário fornecidos como parte do UI5 ou criados como controles personalizados no código do aplicativo. O UI5 vem com centenas desses controles, de botões simples a layouts animados complexos ou coisas como tabelas e gráficos.
>
> Controles de contêiner como `App` e `Page` têm a capacidade de incorporar controles filho aninhados, o que é bem refletido na estrutura XML. Às vezes, esses contêineres têm áreas diferentes ("agregações") para controles filho. Elas são representadas como tags todas em minúsculas como `<content>` e definem em qual área os elementos filho contidos devem ir.
>
> Os atributos das tags XML como `id` e `title` são usados ​​para atribuir propriedades declarativamente, manipuladores de eventos etc.
>
> Como os controles UI5 são desenvolvidos dentro de diferentes "bibliotecas", os namespaces XML são usados ​​para indicar corretamente de qual biblioteca (e subpasta dentro de uma biblioteca) cada controle deve vir. Por exemplo, o namespace padrão nesta visualização XML é "sap.m". Isso significa que todas as tags XML sem namespace como `<Page>` representam controles da biblioteca sap.m. A tag raiz `<mvc:View>`, por outro lado, é o controle `View` dentro da pasta `mvc` na biblioteca `sap.ui.core`.
>
> No tempo de execução, o UI5 instancia os respectivos controles, atribui as propriedades, coloca os controles juntos em uma estrutura de árvore aninhada e os faz criar o HTML real exibido pelo navegador.

## Exercício 2.2 – Adicionar conteúdo ao Sensors.view.xml

Agora vamos finalmente adicionar algum conteúdo!

1. Adicione um `sap.m.IconTabBar` vazio a `Sensors.view.xml` substituindo seu conteúdo da seguinte forma:

###### sensormanager/webapp/view/Sensors.view.xml

```xml
<mvc:View controllerName="keepcool.sensormanager.controller.Sensors"
    xmlns:mvc="sap.ui.core.mvc"
    xmlns="sap.m">
    <Page id="page" title="{i18n>title}">
        <content>
            <IconTabBar id="iconTabBar" class="sapUiResponsiveContentPadding">
                <content>
                </content>
            </IconTabBar>
        </content>    
    </Page>
</mvc:View>
```

> #### 🧑‍🎓 Explicação
> A agregação `<content>` de `<Page>` agora contém um controle `<IconTabBar>`. O atributo `class="sapUiResponsiveContentPadding"` significa que a classe CSS `sapUiResponsiveContentPadding` deve ser escrita no HTML. Esta é uma das classes CSS predefinidas do UI5 e adiciona algum preenchimento ao redor do conteúdo do IconTabBar (adicionaremos este conteúdo em breve). Este preenchimento é *responsivo*, o que significa que depende do tamanho da tela/janela e será menor quando o espaço disponível for limitado.


## Exercício 2.3 – Adicionar dependências

Além da biblioteca principal do UI5 `sap.m`, você usará outras bibliotecas de controle como `sap.ui.layout` em seu aplicativo. O ponto central para configurar seu aplicativo UI5 é o arquivo `manifest.json`, que está localizado em `sensormanager/webapp/manifest.json`.

1. Você pode localizar este arquivo no File Explorer no lado esquerdo ou acessar diretamente `manifest.json` usando o link na página *Application Info*. Se você fechou a página *Application Info* novamente ou não a abriu no exercício anterior, você pode abri-la usando o comando `Fiori: Open Application Info` da paleta de comandos (`CTRL + Shift + P` no Windows/Linux, `Cmd + Shift + P` no Mac).

![](images/02_02_0030.png)

![](images/02_02_0040.png)

2. Em `manifest.json`, vá para a seção `sap.ui5` (CUIDADO: NÃO a seção `sap.ui`!).
3. Adicione duas bibliotecas na seção `dependencies/libs`. O UI5 cuidará de carregar todas as bibliotecas listadas aqui quando seu aplicativo for iniciado.

###### sensormanager/webapp/manifest.json

```json
        "dependencies": {
	    ...
            "libs": {
                ... ,
                "sap.ui.layout": {},
                "sap.suite.ui.microchart": {}
            }
        },
```
>💡 Não se esqueça de adicionar uma vírgula após a entrada anterior quando adicionar esses dois!



Para ver o resultado do que você fez, abra a aba do navegador com a pré-visualização do aplicativo (ou pressione a seta verde "play" no canto superior direito novamente, caso tenha fechado a aba). O aplicativo está sendo atualizado automaticamente sempre que você faz alterações no código. Você não consegue ver o `sap.m.IconTabBar` muito bem ainda, pois ele ainda está vazio. Mas há uma linha adicional agora e você verá muito mais em breve!

![](images/02_02_0050.png)

## Resumo

Ótimo trabalho! Você adicionou conteúdo ao seu aplicativo com sucesso e adicionou mais bibliotecas ao arquivo `manifest.json` do seu aplicativo para uso futuro. Continue com o bom trabalho enquanto continua com [Exercício 3 - Mostrar conteúdo do sensor](../ex3/README.md).


## Mais informações

* UI5 SDK (toda a documentação): https://ui5.sap.com/
* Views em UI5: https://ui5.sap.com/#/topic/91f27e3e6f4d1014b6dd926db0e91070
* Usando classes CSS de preenchimento de conteúdo de contêiner: https://ui5.sap.com/#/topic/c71f6df62dae47ca8284310a6f5fc80a
* Temas: https://experience.sap.com/internal/fiori-design-web/theming/
