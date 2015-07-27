# Começando com Primefaces
## Aula 2.5 Abrindo um diálogo suspenso
Insira o seguinte código dentro de seu componente form:
```xml
<p:dialog header="Nova empresa" widgetVar="edicaoEmpresaDialog"
	 id="empresa-dialog" resizable="false" modal="true"
	 closeOnEscape="true">
	<p:commandButton value="Teste 1" />
</p:dialog>
```
Altere o botão que abrirá o modal da seguinte forma:
```xml
<p:commandButton value="Nova" icon="ui-icon-document"
						onclick="PF('edicaoEmpresaDialog').show()" />
```
