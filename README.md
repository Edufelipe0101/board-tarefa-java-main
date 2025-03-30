# 📋 Board de Tarefas com Java

![Java](https://img.shields.io/badge/Java-21-blue)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.2.3-brightgreen)
![MySQL](https://img.shields.io/badge/MySQL-8.0-orange)

Sistema completo para gerenciamento de quadros (boards) e tarefas (tasks) com categorias e controle de status.

## 🛠 Tecnologias Utilizadas

| Tecnologia       | Versão   | Uso Principal            |
|------------------|----------|--------------------------|
| Java             | 21       | Linguagem principal      |
| Spring Boot      | 3.2.3    | Framework backend        |
| MySQL            | 8.0      | Banco de dados           |
| Liquibase        | 4.25.0   | Migrações de BD          |
| Lombok           | 1.18.30  | Redução de boilerplate   |


## 📊 Modelo de Dados

```mermaid
classDiagram
    class Board {
        +Long id
        +String name
        +List~Task~ tasks
    }
    
    class Task {
        +Long id
        +String title
        +String description
        +Category category
        +Status status
    }
    
    class Category {
        <<enum>>
        PESSOAL
        TRABALHO
        ESTUDO
    }
    
    class Status {
        <<enum>>
        INICIAL
        PENDENTE
        FINALIZADO
        CANCELADO
    }
    
    Board "1" *-- "n" Task
    Task --> Category
    Task --> Status
