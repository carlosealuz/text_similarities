# Similaridade entre sentenças 

No notebook encontra-se o código utilizado para criar um modelo Doc2Vec para classificar se duas sentenças são semelhantes ou não.

Foi feita a remoção de stopwords utilizando a biblioteca NLTK.

A partir daí as sentenças do dataframe foram divididas em duas listas e processadas com o TaggedDocument para criar um objeto que pudesse ser utilizado pelo modelo.

Para verificação de similaridade eu considerei que as sentenças eram similares se o output fosse maior ou igual a 80%. Utilizei esse valor pois no momento me pareceu aceitável.

Por fim, fiz o cálculo da acurácia do modelo baseando na coluna "same-security" do dataframe e na classificação obtida nos outputs. Fiz também uma matrix de confusão para visualizar em qual classe o modelo performou bem ou mal. 

# Considerações

* testei dm = 0 e a acurácia caiu bastante 
* alpha 0.01 e 0.001 não fizeram tanta diferença 
* window 5 teve queda na acurácia 
* negative 15 ajudou bem pouco na acurácia

Um ponto importante a se considerar é que no dataset existem mais sentenças parecidas do que diferentes. Isso pode influenciar no treinamento pois ele vai ser viesado para sentenças semelhantes, como podemos ver na matrix de confusão. Algo que podemos fazer pra ajudar a resolver isso, seria acrescentar sentenças diferentes no dataset. 

Outra coisa a considerar seria tentar outro tipo de modelo como bag of words ou TfidfVectorizer do sklearn que também se baseia na semelhança de cossenos para detectar similaridade.
