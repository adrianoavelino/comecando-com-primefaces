# Começando com Primefaces
## Aula 1.6. Testando alguns componentes do PrimeFaces

Altere o arquivo _/comecando-primefaces/src/main/webapp/WEB-INF/**web.xml**_ para o seguinte conteúdo:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xmlns="http://xmlns.jcp.org/xml/ns/javaee"
	xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_3_1.xsd"
	version="3.1">

	<context-param>
		<param-name>javax.faces.PROJECT_STAGE</param-name>
		<param-value>Development</param-value>
	</context-param>

	<context-param>
		<param-name>javax.faces.FACELETS_REFRESH_PERIOD</param-name>
		<param-value>0</param-value>
	</context-param>

	<servlet>
		<servlet-name>Faces Servlet</servlet-name>
		<servlet-class>javax.faces.webapp.FacesServlet</servlet-class>
		<load-on-startup>1</load-on-startup>
	</servlet>

	<servlet-mapping>
		<servlet-name>Faces Servlet</servlet-name>
		<url-pattern>*.xhtml</url-pattern>
	</servlet-mapping>

</web-app>
```
Vamos explicar algumas ```tags```:  
* Definindo o estágio do projeto, onde o valor ```Development``` define que o projeto está em desenvolvimento e o debug exibe as mensagens de erros mais completas  
```xml
<context-param>
	<param-name>javax.faces.PROJECT_STAGE</param-name>
	<param-value>Development</param-value>
</context-param>
```

* Define que o projeto terá o cache atualizado assim que salvar o arquivo xml
```xml
<context-param>
    <param-name>javax.faces.FACELETS_REFRESH_PERIOD</param-name>
    <param-value>0</param-value>
</context-param>
```

* Definindo a servlet
```xml
<servlet>
    <servlet-name>Faces Servlet</servlet-name>
    <servlet-class>javax.faces.webapp.FacesServlet</servlet-class>
    <load-on-startup>1</load-on-startup>
</servlet>
```

* Mapeando a servlet
```xml
<servlet>
    <servlet-name>Faces Servlet</servlet-name>
    <servlet-class>javax.faces.webapp.FacesServlet</servlet-class>
    <load-on-startup>1</load-on-startup>
</servlet>
```

Agora vamos criar o nosso primeiro arquivo ```xhtml```:  
Botão direito do mouse na pasta _/comecando-primefaces/src/main/webapp/ > New > HTML file_ e crie o arquivo **Teste.xhtml** com o seguinte conteúdo:
```html
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml"
	xmlns:h="http://xmlns.jcp.org/jsf/html"
	xmlns:p="http://primefaces.org/ui">
<h:head>
	<meta charset="UTF-8"/>
</h:head>
<h:body>

	<h:form>

		<p:panel header="Cadastro de cliente">
			<h:panelGrid columns="2">
				<p:outputLabel value="Nome" />
				<p:inputText />

				<p:outputLabel value="CPF" />
				<p:inputMask mask="999.999.999-99" />

				<p:outputLabel value="Data de nascimento" />
				<p:calendar pattern="dd/MM/yyyy" mask="99/99/9999" />

				<p:outputLabel/>
				<p:commandButton value="Salvar"/>
			</h:panelGrid>
		</p:panel>

	</h:form>

</h:body>
</html>
```
Vamos entender um pouco do conteúdo desse arquivo:
* importa o JSF no arquivo com o apelido ```h```:
```xml
xmlns:h="http://xmlns.jcp.org/jsf/html"
```
* importa o Primefaces no arquivo com o apelido ```p```:
```xml
xmlns:p="http://primefaces.org/ui"
```
