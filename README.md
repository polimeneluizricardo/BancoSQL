
# README — Introdução ao SQL usando o Banco Northwind

Este documento explica **conceitos fundamentais de SQL** utilizando o banco de exemplo **Northwind**, que é distribuído pela Microsoft.

---

## 📘 1. O que é SQL?

**SQL (Structured Query Language)** é a linguagem usada para consultar e manipular dados em bancos relacionais.

Com SQL você pode:

- Buscar dados (`SELECT`)
- Filtrar resultados (`WHERE`)
- Ordenar (`ORDER BY`)
- Relacionar tabelas (`JOIN`)
- Inserir dados (`INSERT`)
- Atualizar (`UPDATE`)
- Excluir (`DELETE`)

Este README foca em **consulta de dados** usando SELECT.

---

## 🛠️ 2. Estrutura das Tabelas no Northwind

Algumas tabelas importantes do banco Northwind:

| Tabela | O que contém |
|--------|--------------|
| Customers | Clientes |
| Orders | Pedidos |
| Order Details | Itens do pedido |
| Products | Produtos |
| Suppliers | Fornecedores |
| Employees | Funcionários |

---

## 🔎 3. SELECT — Consultando Dados

### ✔ Exemplo 1 — Selecionar todos os clientes
```sql
SELECT * FROM Customers;
```
**Resultado:** lista todos os clientes.

### ✔ Exemplo 2 — Selecionar colunas específicas
```sql
SELECT CompanyName, Country
FROM Customers;
```
**Resultado:** mostra apenas empresa e país.

### ✔ Exemplo 3 — Filtrar com WHERE
```sql
SELECT *
FROM Customers
WHERE Country = 'Brazil';
```
**Resultado:** mostra apenas clientes brasileiros.

---

## 🔗 4. INNER JOIN — Relacionando Tabelas

### ✔ Exemplo 4 — Pedidos + Clientes
```sql
SELECT 
    o.OrderID,
    c.CompanyName,
    o.OrderDate
FROM Orders o
INNER JOIN Customers c ON o.CustomerID = c.CustomerID;
```
**Resultado:** une o cliente ao pedido.

### ✔ Exemplo 5 — Itens de pedido + Produtos
```sql
SELECT 
    od.OrderID,
    p.ProductName,
    od.Quantity,
    od.UnitPrice
FROM [Order Details] od
INNER JOIN Products p ON od.ProductID = p.ProductID;
```
**Resultado:** mostra os itens de cada pedido.

---

## 🗂️ 5. ORDER BY — Ordenando Dados

### ✔ Exemplo — Produtos mais caros
```sql
SELECT ProductName, UnitPrice
FROM Products
ORDER BY UnitPrice DESC;
```

---

## 🧮 6. GROUP BY — Agrupando Dados

### ✔ Exemplo — Total vendido por produto
```sql
SELECT 
    ProductID,
    SUM(Quantity) AS TotalVendido
FROM [Order Details]
GROUP BY ProductID;
```

---

## 📚 Conclusão

Este README serve como introdução prática ao SQL usando o banco Northwind. Use estes exemplos como base para criar consultas mais complexas.

