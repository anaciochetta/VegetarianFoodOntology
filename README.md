# VegetarianFoodOntology

Este repositório apresenta uma ontologia semântica desenvolvida para classificar e organizar o conhecimento sobre alimentos, com foco em comidas típicas (brasileiras, italianas e japonesas) e suas adequações dietéticas dentro do vegetarianismo

## O que é?
Uma ontologia é uma representação formal do conhecimento de um domínio específico, facilitando a comunicação entre humanos e sistemas computacionais.  Foi usado a linguagem OWL (Web Ontology Language) e o WebProtégé para estruturar essa informação de forma que máquinas possam compreendê-la e processá-la. 

## 🎯 **Objetivo**
Responder a perguntas como:
- "Quais pratos brasileiros são vegetarianos?"
- "Quais sobremesas italianas são vegetarianas?"
- "Listar entradas japonesas que podem ser vegetarianas"

## 🛠️ Como foi estruturado? 
- **Classes principais**: `Dessert`, `MainCourse`, `Starter`
- **Propriedades**: 
  - `hasCuisine` (brasileira/italiana/japonesa)
  - `hasDietType` (vegetariana, vegana, etc.)
  - `hasIngredient` (carnes, laticínios, vegetais)
- **Exemplos incluídos**:
  - Brigadeiro, Feijoada, Sushi, Lasanha
 
## ✨ **Destaques**
isVegetarianByDefault (Booleano)
Indica se o prato é naturalmente vegetariano em sua receita tradicional:
- true: Pratos que nunca contêm ingredientes animais (ex: bruschetta, pão de queijo)
- false: Pratos que tradicionalmente levam carne/peixe (ex: feijoada, coxinha)

canBeVegetarian (Booleano)
Indica se o prato pode ser adaptado para versão vegetariana:
- true: Tem versões sem ingredientes animais (ex: lasagna com vegetais, gyoza de tofu)
- false: Não pode ser modificado sem perder a essência (ex: tonkatsu)

obs: foi considerado vegetariano nesse caso receitas sem carne.

## 🌱 Exemplo

```
:brigadeiro a :Dessert ;
    rdfs:label "brigadeiro" ;
    :hasCuisine :brazilianCuisine ;
    :isVegetarianByDefault true ;
    :hasIngredient :chocolate ;
    :hasDietType "lactoVegetarian" .

:lasagna a :MainCourse ;
    rdfs:label "lasagna" ;
    :hasCuisine :italianCuisine ;
    :isVegetarianByDefault false ;
    :canBeVegetarian true ;
    :hasIngredient :cheese, :tomato ;
    
```
