# Começando com Primefaces
## Aula 1.5. Adicionando Primefaces no projeto

Abra o seu arquivo pom.xml e acrescente o seguinte conteúdo após a tag `<properties>`:
```xml
<dependencies>
    <dependency>
        <groupId>org.glassfish</groupId>
        <artifactId>javax.faces</artifactId>
        <version>2.2.8-02</version>
        <scope>compile</scope>
    </dependency>
    <dependency>
        <groupId>org.primefaces</groupId>
        <artifactId>primefaces</artifactId>
        <version>5.1</version>
        <scope>compile</scope>
    </dependency>
</dependencies>
```
Clique com o botão direito do mouse no Projeto > Maven > Update Project _(ALT + F5)_  

Abra **proprerties** do seu Projeto > **Project Facets**:
* selecione **Dynamic Web Module** e altere para a versão **3.1**
* selecione **JavaServer Faces** e altere para a versão **2.2**

Botão direito do mouse em **Deplyment Descriptior: nome-do-projeto** dentro do seu projeto e selecione a opção **Generate Deplyment Descriptior Stub** paraa gerar o arquivo _/comecando-primefaces/src/main/webapp/WEB-INF/web.xml_.  
**Obs:** _caso o arquivo esteja com a versão anterior a 3.1, exclua o arquivo **web.xml** e repita o procedimento acima._
