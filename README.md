Natural_Language_Processing
===========================

Summer School Big Data 2014

# Day One

##Introdução
* Forma Linguística - Generative Syntax - regras que geram estrturas sintáticas
* Significado e Conteúdo - como colocar "conteúdo" em forma linguística? Como extrair o "conteúdo"?

##Significado e Conteúdo

* Tradução forma linguística e "linguagem da mente"
* Estados mentais

##Exemplo

Barack Hussein Obama II (born August 4, 1961) is the 44th and current President of the United States, and the first African American to hold the office. Born in Honolulu, Hawaii, Obama is a graduate of Columbia University and Harvard Law School, where he served as president of the Harvard Law Review. He was a community organizer in Chicago before earning his law degree. He worked as a civil rights attorney and taught constitutional law at the University of Chicago Law School from 1992 to 2004. He served three terms representing the 13th District in the Illinois Senate from 1997 to 2004, running unsuccessfully for the United States House of Representatives in 2000.

* Como podemos extrair informações do texto?

Entidades nomeada - Barack Hussein Obama II (nome), president (função), 

## Expressão Regular

* Falso Positivo/ Falso Negativo - minimizar

## Processamento de Linguagem Natural vs Big Data

Textos Não-Estruturados > Big Data > Big knowledge

Querying & Reasoning <- Large-scae unstructured data + Structured/logic/ Knowledge Baes

Resolver questões do tipo "What is the relationship between Barack Obama and Indonesia?" - questão em linguagem natural e através de bases de dados ser possível respondê-la


## Pré Processamento

* Tokenization

Tem como objetivo detectar os limites de palavras e sentenças
Ferramenta: NLTK (open source possui diversas ferramentas de segmentação de sentença, tokenitização)
Problemas: Como definir o que é um token?

* Normalização

Permite a definição de classes de equivalência dos termos
UFRJ x U.F.R.J. ou UFRJ x ufrj

Definir representação padrão

* Stemming/ Lemmatization

Aplicados como um passo de normalização, mapeia variantes morfológicas a seu correspondente básico.

Stemming (Algoritmo de Porter - Mais usado em inglês) - processo heurístico que normalmente corta o final da palavra (remoção de afixos de derivação)

foxes - fox  going - go

Lemmatization - utiliza análise morfológica para identificar a forma padrão

saw - verb see

* Segmentação de sentença

Determinar os limites de uma sentença. Porém (Prof.) o ponto não determina neste caso uma sentença.
Utilizar um classificador para definir se temos ou não uma sentença.

Exemplo - Árvore de decisão.

* Part of Speech - (POS) tagging

Stanford Log-Linear Part of Speech Tagger (VERIFICAR)

Penn Treebank POS target - corpus formado por mais de 4.5 milhões de palavras (VERIFICAR - VALE A PENA) - Árvores anotadas com informações sintáticas e semânticas.

Problema - Determinar qual o POS-tag de uma dada palavra
Acurácia - 95% a 97%
muitas palavras não possuem ambiguidade
baseline - 90% (já inicia com solução simples)

* Resolução de Coreferência

Identificar todos os sintagmas nominais (noun phrases - NPs) que se referem a uma mesma entidade do mundo real em um texto. Obama, Barack Obama, tudo a mesma pessoa.

Reconcile - sistema para NPL

Input Documents-> Pre processing Vector -> Classifier -> Cluster

=====================================================================

* Chunking/ Shallow or Partial Parsing

Técnica de processamento superficial (expressões regulares) para agrupar palavras em constituintes sintáticos maiores e com um significado.

Chunk : unidades sintáticas. (Não possui overlapping/ Não recursivo/ Não exaustivo/ Não identificam relações gramaticais/ Ambiguidade sintática)

Como identificar? Passar o pos tagging para separar a estrutura.

Phrase Structure
NP - Noun Phrase
VP - Verb Phrase
PP - Prepositional Phrase

Phrase Structure Grammars - Chomsky

Forma normal de Chomsky - derivações de árvores binárias

* Stanford Parser

Como resolver o problema da ambiguidade?
Associado ao número de regras que a gramática possui
Gramática mais restritivas
Statistical Parsing!! (Solução) análise estatística

Exemplo - Gramática livre de contexto probabilística (PCFG)

Dependency Structure
Em uma sentença, todas as palavras (menos uma, raiz) dependem das outras. Criar árvore de dependências para criar rótulos e hierarquia de classes gramaticais. Estruturas complexas são baseadas em hierarquias que associa e fazum relacionamento de dependencia entre os tipos palavras que temos na sentença. Software usado: Stanford Dependencies Parser.


* Semântica

Como damos significados?
Existem lemas que possuem vários significados. Por exemplo, a palavra "bank"
Sense ou Word Sense - representação do significado de uma palavra.

Homonyms: palavras qu possuem a mesmaforma e significados distintos (Homographs/Homophones)

Problemas: Recuperação da informação/ Tradução de máquina/ Text-to-Speech

Polysemy: palavras que possuem significados relacionados. Podemos estabelecer relacionamenos entre os senses: Building <-> Organization

Como sabemos se duas palavras tem o mesmo sense?

Ex. Construir uma frase com o mesmo verbo e verificar se a nova frase faz sentido. "A Gol está em São Paulo" e "A Gol serve lanche"

WordNet (VERIFICAR) is a large lexical database of English. MUITO UTILIZADO EM LINGUAGEM NATURAL

Antonyms

Hyponymy - o primeiro sense é mais específico que o segundo (carro - veículo)
Hypernymy - inverso de hyponymy (fruta - manga)













