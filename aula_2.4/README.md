# Começando com Primefaces
## Aula 2.4 Criando um template com facelets

- Crie uma pasta chamada /resources/algaworks e insira uma imagem para o logo do template e um arquivo css.
- Crie a pasta `/WEB-INF/templates` e adicione o seguinte arquivo chamado `Layout.xhtml`

```xml
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml"
	xmlns:h="http://xmlns.jcp.org/jsf/html"
	xmlns:f="http://xmlns.jcp.org/jsf/core"
	xmlns:ui="http://xmlns.jcp.org/jsf/facelets"
	xmlns:p="http://primefaces.org/ui">
<h:head>
	<meta charset="UTF-8"/>

	<h:outputStylesheet library="algaworks" name="estilo.css" />
</h:head>
<h:body>

	<header>
		<h:graphicImage library="algaworks" name="logo.png" />
	</header>

	<div id="conteudo">
		<ui:insert name="corpo" />
	</div>

	<footer>
		Workshop online "Começando com PrimeFaces"
	</footer>

</h:body>
</html>
```

Para incluir a folha de estilo css usamos o componete JSF `<h:outputStylesheet library="algaworks" name="estilo.css" />`, onde a library contém a pasta dentro de  /resources (no nosso caso algaworks) e name é o nome do arquivo css (estilo.css) .

Para incluir uma imagem na tag `header` usamos o componente do JSF `<h:graphicImage library="algaworks" name="logo.png" />`, onde library é o nome da pasta dentro de resources e name é o nome da imagem.

O componete `<ui:insert name="corpo" />` do JSF será responsável por receber o conteúdo das páginas.

Altere o arquivo /GestaoEmpresas.xhtml do exemplo abaixo:

```xml
<!DOCTYPE html>
<ui:composition template="/WEB-INF/templates/Layout.xhtml"
	xmlns="http://www.w3.org/1999/xhtml"
	xmlns:h="http://xmlns.jcp.org/jsf/html"
	xmlns:f="http://xmlns.jcp.org/jsf/core"
	xmlns:ui="http://xmlns.jcp.org/jsf/facelets"
	xmlns:p="http://primefaces.org/ui">

	<ui:define name="corpo">
		<f:metadata>
			<f:viewAction action="#{gestaoEmpresasBean.consultar}" />
		</f:metadata>

		<h1>Cadastro de Empresas</h1>

		<h:form id="frm">

			<p:dataTable value="#{gestaoEmpresasBean.todasEmpresas}" var="empresa"
					emptyMessage="Nenhuma empresa cadastrada." rows="10"
					paginator="true" paginatorPosition="bottom">
				<p:column headerText="Razão social" sortBy="#{empresa.razaoSocial}">
					<h:outputText value="#{empresa.razaoSocial}" />
				</p:column>
				<p:column headerText="Nome fantasia" width="250">
					<h:outputText value="#{empresa.nomeFantasia}" />
				</p:column>
				<p:column headerText="CNPJ" width="160">
					<h:outputText value="#{empresa.cnpj}" />
				</p:column>
			</p:dataTable>

		</h:form>

	</ui:define>
</ui:composition>
```

O componete JSF responsável por incluir o template é:

```<ui:composition template="/WEB-INF/templates/Layout.xhtml"
	xmlns="http://www.w3.org/1999/xhtml"
	xmlns:h="http://xmlns.jcp.org/jsf/html"
	xmlns:f="http://xmlns.jcp.org/jsf/core"
	xmlns:ui="http://xmlns.jcp.org/jsf/facelets"
	xmlns:p="http://primefaces.org/ui">```

Onde `template` é o caminho para o arquivo _/WEB-INF/templates/Layout.xhtml_ e o restantes são as inclusões das bibliotecas.

E todo conteúdo dentro de `<ui:define name="corpo">` será exibido dentro do seu template _(/WEB-INF/templates/Layout.xhtml)_
