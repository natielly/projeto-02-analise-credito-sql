# Projeto 02: Análise de Risco de Crédito e Modelagem de Dados

## 1. Contexto de Negócio
Num cenário financeiro, a identificação precoce de perfis com propensão ao atraso nos pagamentos é crucial para a mitigação de riscos. Este projeto simula o ambiente de dados de uma instituição financeira, com o objetivo de modelar as informações dos clientes e cruzar esses dados com a carteira de empréstimos para identificar focos de inadimplência.

## 2. Tecnologias e Metodologia Aplicada
* **Linguagem:** SQL (Structured Query Language)
* **Conceitos:** Modelagem de Dados Relacional, Chaves Primárias (Primary Keys) e Cruzamento de Tabelas (INNER JOIN).
* **Processo:** Construção de um banco de dados relacional do zero, dividindo as informações nas tabelas `Clientes` e `Emprestimos`, ligadas de forma lógica pelo `ID_Cliente`.

## 3. Código de Extração (Query Principal)
Para identificar o perfil demográfico e financeiro dos clientes em atraso, foi executada a seguinte consulta cruzando as duas tabelas:

```sql
SELECT Clientes.Nome, Clientes.Idade, Clientes.Renda_Mensal, Emprestimos.Valor_Emprestimo
FROM Clientes
INNER JOIN Emprestimos ON Clientes.ID_Cliente = Emprestimos.ID_Cliente
WHERE Emprestimos.Status_Pagamento = 'Atrasado';
