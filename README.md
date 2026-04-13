# provaP1_bancdedadonaoRelacionados
P1 da Prova de banco de dados não relacionados

# 📚 Prova MongoDB — Banco de Dados

## 👨‍💻 Autor

Eduardo Lima

---

## 🚀 Tecnologias Utilizadas

* Docker
* MongoDB
* MongoDB Compass

---

## 🗄️ Estrutura do Banco de Dados

* **Banco:** escola
* **Collection:** alunos

Cada documento segue o modelo:

```json
{
  "nome": "João Silva",
  "idade": 20,
  "curso": "ADS",
  "notas": [7, 8, 9],
  "endereco": {
    "cidade": "Maricá",
    "estado": "RJ"
  }
}
```

---

## 📥 Inserção de Dados

Foram inseridos 5 alunos seguindo o modelo proposto, contendo:

* Nome
* Idade
* Curso
* Notas (array)
* Endereço (objeto)

---

## 🔍 Consultas Realizadas

### 1. Buscar todos os alunos

Consulta geral retornando todos os documentos da coleção.

### 2. Buscar alunos do curso "ADS"

Filtro aplicado no campo `curso`.

### 3. Buscar alunos com idade maior que 21

Utilização do operador `$gt`.

---

## ✏️ Operações Realizadas

### 4. Atualização de dados

Atualização da idade de um aluno utilizando `$set`.

### 5. Adição de nova nota

Inclusão de um novo valor no array `notas` com `$push`.

### 6. Remoção de aluno

Exclusão de um documento com `deleteOne`.

---

## 📊 Aggregations

### 7. Média de notas por aluno

Utilização do operador `$avg` para cálculo da média:

```js
db.alunos.aggregate([
  {
    $project: {
      nome: 1,
      media: { $avg: "$notas" }
    }
  }
])
```

---

### 8. Quantidade de alunos por curso

Agrupamento com `$group`:

```js
db.alunos.aggregate([
  {
    $group: {
      _id: "$curso",
      total: { $sum: 1 }
    }
  }
])
```

---

## 📸 Evidências

Todos os resultados das operações estão disponíveis na pasta:

📁 **/prints**

Contendo:

* Inserção dos dados
* Consultas
* Atualizações
* Remoção
* Aggregations

---

## ✅ Conclusão

O projeto demonstra a utilização prática do MongoDB com operações de:

* Inserção
* Consulta
* Atualização
* Remoção
* Agregação de dados

Aplicando conceitos fundamentais de bancos de dados não relacionais.

---
