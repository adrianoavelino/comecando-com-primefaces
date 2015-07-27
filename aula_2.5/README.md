# Começando com Primefaces
## Aula 2.5 Adicionando uma barra de ferramentas

Para adicionar uma toolbar acrescente o seguinte componete:
```xml
<p:toolbar>
	<f:facet name="left">
		<p:commandButton value="Nova" icon="ui-icon-document" />

		<span class="ui-separator">
			<span class="ui-icon ui-icon-grip-dotted-vertical" />
		</span>

		<p:commandButton icon="ui-icon-pencil" title="Editar" />

		<p:commandButton icon="ui-icon-trash" title="Excluir" />

		<p:commandButton icon="ui-icon-arrowthick-1-s" title="Exportar para XLS" />
	</f:facet>
</p:toolbar>
```

O componete `<p:toolbar>` insere uma toolbar e o componente `<f:facet name="left">` define o alinhamento dos elementos, onde no nosso caso está definido como  _"left"_.

Para criamos um botão utilizamos o componente `<p:commandButton value="Nova" icon="ui-icon-document" />`, onde o `value` é o texto do botão e `icon` é a classe css referente a imagem.

Para inserir um separador entre os botões utilizamos:
```xml
<span class="ui-separator">
	<span class="ui-icon ui-icon-grip-dotted-vertical" />
</span>
```

_OBS: O nome das classes do ícones podem ser encontrados [aqui](http://www.petefreitag.com/cheatsheets/jqueryui-icons/). _
