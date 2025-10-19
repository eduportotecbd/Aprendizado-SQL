# 📊 SQL -- Criação de View Personalizada

Este projeto faz parte da minha jornada de aprendizado em **SQL com foco
em Segurança da Informação**.\
Aqui utilizei o SQL Server Management Studio para criar uma **View** que
organiza e formata dados da tabela `DimCustomer`.

------------------------------------------------------------------------

## 🚀 Objetivo da View

-   Concatenar **Primeiro Nome + Último Nome** em um campo de **Nome
    Completo**\
-   Exibir **E-mail**\
-   Formatar **Renda Anual** em Real (R\$)\
-   Traduzir o campo **Gênero** (M/F → Masculino/Feminino)

------------------------------------------------------------------------

## 📝 Código SQL

``` sql
CREATE VIEW VWCLIENTES AS
SELECT
    CONCAT(FirstName, ' ', LastName) AS 'NOME COMPLETO',
    EmailAddress AS 'E-MAIL',
    FORMAT(YearlyIncome, 'C', 'pt-BR') AS 'RENDA ANUAL',
    CASE 
        WHEN Gender = 'M' THEN 'MASCULINO'
        ELSE 'FEMININO'
    END AS 'GENERO'
FROM DimCustomer
WHERE FirstName IS NOT NULL;
```

------------------------------------------------------------------------

## 📊 Resultado (Exemplo)

  -----------------------------------------------------------------------------
  NOME COMPLETO       E-MAIL                           RENDA ANUAL  GENERO
  ------------------- -------------------------------- ------------ -----------
  Jon Yang            jon24@adventure-works.com        R\$ 90.000   MASCULINO

  Eugene Huang        eugene10@adventure-works.com     R\$ 60.000   MASCULINO

  Elizabeth Johnson   elizabeth5@adventure-works.com   R\$ 70.000   FEMININO
  -----------------------------------------------------------------------------

------------------------------------------------------------------------

## 🔐 Por que isso é importante?

Esse tipo de prática reforça não apenas o domínio de **consultas SQL**,
mas também boas práticas de **organização e formatação de dados** ---
essenciais para trabalhar com **Segurança da Informação e Blue Team**.

------------------------------------------------------------------------

👉 Hashtags para GitHub:\
`#SQL #Database #Security #Learning #BlueTeam`
