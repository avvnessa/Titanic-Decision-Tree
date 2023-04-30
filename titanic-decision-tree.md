---
title: Titanic Decision Tree
author: "M. Vanessa Sousa Mesquita"
date: "`r format(Sys.time(), '%d/ %B/ %Y')`"
output:
     html_document:
       highlight: textmate
       theme: flatly
       number_sections: yes
       toc: yes
       toc_float:
         collapsed: yes
         smooth_scroll: no
---

# Pacotes
```{r}
library(dplyr)  # para manipulação de dados
library(rpart)  # para criação de árvores de decisão
library(rpart.plot)  # para visualização das árvores de decisão
```

# Importar dados
```{r}
titanic_data <- read.csv("train.csv")
```

#Remover colunas desnecessárias
```{r}
 titanic_data <- titanic_data[c("Survived", "Pclass", "Sex", "Age", "SibSp", "Parch", "Fare", "Embarked")]
```

# Converter variáveis categóricas em fatores
```{r}
titanic_data$Sex <- as.factor(titanic_data$Sex)
titanic_data$Embarked <- factor(titanic_data$Embarked)
titanic_data$Survived <- factor(titanic_data$Survived)
```

# Dividir em conjunto de treinamento e teste
```{r}
library(caTools)
set.seed(123)  # para garantir a reprodutibilidade dos resultados
train_index <- sample(nrow(titanic_data), round(0.7 * nrow(titanic_data)))
train_data <- titanic_data[train_index, ]
test_data <- titanic_data[-train_index, ]
```

# Criar árvore de decisão
```{r}
titanic_tree <- rpart(Survived ~ Sex + Age + Fare + Embarked, data = train_data, method = "class")
```

# Visualize a árvore de decisão
```{r}
rpart.plot(titanic_tree, type = 2, extra = 101, under = TRUE, clip.right.labs = FALSE)
```



Isso irá produzir um gráfico da árvore de decisão que pode ser interpretado para entender quais variáveis influenciaram mais as chances de sobrevivência no Titanic.


# Calcular a precisão da árvore de decisão
```{r}
test_data$predicted_survival <- predict(titanic_tree, newdata = test_data, type = "class")
test_data$predicted_survival <- as.integer(as.character(test_data$predicted_survival))
test_data$Survived <- as.integer(as.character(test_data$Survived))
accuracy <- sum(test_data$predicted_survival == test_data$Survived) / nrow(test_data)
```

