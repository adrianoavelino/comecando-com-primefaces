# Começando com Primefaces
## Aula 2.2 Configurando paginação na tabela de dados

A páginação é muito simples, basta adicionar a propriedade ```paginator``` como ```true``` e paginação já está funcionando.  
_OBS: Como temos somente 4 registro na tabela do banco de dados adicionaremos a propriedade **rows** com o valor 2 _

Ex:
```xml
<p:dataTable value="#{gestaoEmpresasBean.todasEmpresas}" var="empresa"
emptyMessage="Nenhuma empresa cadastrada" paginator="true" rows="2"
style="width: 70%; margin:auto;">
    <p:column headerText="Razão social">
        <h:outputText value="#{empresa.razaoSocial}" />
    </p:column>
    <p:column headerText="Nome fantasia" width="250">
        <h:outputText value="#{empresa.nomeFantasia}" />
    </p:column>
    <p:column headerText="CNPJ" width="160">
        <h:outputText value="#{empresa.cnpj}" />
    </p:column>
</p:dataTable>
```

Para deixar a tabela coma paginação somente embaixo utilize o atributo ```paginator``` com o valor **bottom**   

Ex:
```xhtml
<p:dataTable value="#{gestaoEmpresasBean.todasEmpresas}" var="empresa"
emptyMessage="Nenhuma empresa cadastrada" paginator="true" rows="2" paginatorPosition="bottom"
style="width: 70%; margin:auto;">
    <p:column headerText="Razão social">
        <h:outputText value="#{empresa.razaoSocial}" />
    </p:column>
    <p:column headerText="Nome fantasia" width="250">
        <h:outputText value="#{empresa.nomeFantasia}" />
    </p:column>
    <p:column headerText="CNPJ" width="160">
        <h:outputText value="#{empresa.cnpj}" />
    </p:column>
</p:dataTable>
```
