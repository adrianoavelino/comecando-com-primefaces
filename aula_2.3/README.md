# Começando com Primefaces
## Aula 2.3 Ordenando tabela de dados por coluna

Para ordenar uma tabela por coluna primeiramente deve-se adicionar a o componente datatable dentro do componete form do JSF e depois basta adicionar a propriedade `sortBy` e adicionar como valor a expression languagem, que no nosso caso será `#{empresa.razaoSocial}`.

_OBS: Caso esqueça de adicionar o componete form do JSF será gerado um erro._

Ex:

```xml
<h:form>
    <p:dataTable value="#{gestaoEmpresasBean.todasEmpresas}" var="empresa"
    emptyMessage="Nenhuma empresa cadastrada" paginator="true"  paginatorPosition="bottom"
    style="width: 70%; margin:auto;">
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
```
