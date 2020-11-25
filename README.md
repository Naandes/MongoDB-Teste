# Desafio

## Api de notícias

### **Overview**

Api para agendamento serve para agendar horários, sendo possível cadastrar um agendamento por: dia especifico, diária ou semanal, deletar o agendamento criado, consultar todos os agendamentos e também consultar por intervalo de dia

### **Tecnologies**

- Flask
- MongoDb
- Venv

### **Quick start**

- Clonar Repositorio: `git clone git@github.com:joaogn/desafio-cubos.git`
- Instalar Python : `https://python.org.br/instalacao-windows/` 
- Instalar Virtualenv: `pip install virtualenv --user`
- Acessar pasta Scripts através do terminal: `cd .\MongoDB-Teste\meuvenv\Scripts`
- Iniciar o Virtualenv no terminal: `activate`
- Acessar pasta src através do terminal: `cd .\MongoDB-Teste\src`
- Iniciar a aplicação: `python app.py`


### **Database**

Os arquivos de dados são src/database.json e src/testDatabase.json (usado somente para testes)

### **Endpoints**

### Cadastrar regras de horário para atendimento

http://localhost:5000/add **POST**

**Dados Válidos**

Os dados válidos são através da seguinte forma:
```json

  "titulo" : "titulo que deseja para sua noticia",
  "noticia" : "Campo de texto que deseja para sua noticia",
  "autor" : "Autor da sua noticia"

```

**Dados de Retorno**

"Noticia adicionada com sucesso"



### **Busca da noticia**

http://localhost:5000/busca **GET**

**Dados Válidos**

```javascript
  busca: "Palavra a ser buscada";
```

**Dados de Retorno**

```json
[
  {
    "_id": {"$oid": "5fbe86dd00ce1690bd75f871"}, 
    "noticia": "Rainha", 
    "titulo": "Camilla", 
    "autor": "Deus"
  }
]
```

**Obs**

Caso não encontre nada na busca, o vetor retona o vetor vazio

### **Busca da noticia**

http://localhost:5000/delete/<id> **DELETE**

**Dados Válidos**

Somente acessar com o ID da notícia e com a url acima deleta a notícia.

**Dados de Retorno**

"Notícia deleta com sucesso"

### **Busca da noticia**

http://localhost:5000/update/<id> **PUT**  

**Dados Válidos**

Os dados válidos são através da seguinte forma:
```json

  "titulo" : "Modificação do titulo, caso exista",
  "noticia" : "Modificação do campo do título, caso exista",
  "autor" : "Modificação do autor, caso exista"

```

**Dados de Retorno**

"Noticia alterada com sucesso"
