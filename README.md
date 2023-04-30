# Árvore de decisão sobre o Titanic

Este repositório contém um projeto de aprendizado de máquina para prever a sobrevivência no Titanic usando árvore de decisão. A base de dados utilizada é do [Kaggle](https://www.kaggle.com/code/kaiquesotnas/titanic-rvore-de-decis-o/input?select=train.csv).

# Contexto

O naufrágio do Titanic é um dos eventos mais conhecidos da história, tendo ocorrido em 15 de abril de 1912. O navio afundou depois de colidir com um iceberg, matando mais de 1500 pessoas entre tripulantes e passageiros. Neste projeto, usaremos a base de dados do Kaggle para prever a sobrevivência de passageiros do Titanic.

# Descrição dos arquivos

* titanic.csv: base de dados utilizada neste projeto.
* titanic_decision_tree.Rmd: arquivo RMarkdown com a implementação da árvore de decisão.
* titanic_decision_tree.html: arquivo HTML gerado a partir do arquivo RMarkdown.

# Como reproduzir a análise
Para reproduzir a análise, siga as etapas abaixo:

* Baixe ou clone este repositório em sua máquina local.
* Abra o arquivo titanic.Rmd no RStudio ou em qualquer outro ambiente de desenvolvimento de sua escolha.
* Certifique-se de ter as bibliotecas necessárias instaladas. Caso não tenha, execute o comando install.packages(c("tidyverse", "rpart.plot")) para instalá-las.
* Execute o código no arquivo titanic.Rmd linha por linha ou pressione o botão "Knit" para gerar o arquivo HTML resultante.
Visualize o arquivo HTML para ver os resultados da análise.

# Resultados da análise

A árvore de decisão resultante mostra que a sobrevivência dos passageiros do Titanic foi fortemente influenciada por sua classe de passagem, sexo e idade. Passageiros da primeira classe tinham uma chance maior de sobrevivência, enquanto homens e passageiros mais velhos tinham uma chance menor.
