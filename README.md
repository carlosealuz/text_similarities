# Similaridade entre sentenças 

# Considerações

* testei dm = 0 e a acurácia caiu bastante 
* alpha 0.01 e 0.001 não fizeram tanta diferença 
* window 5 teve queda na acurácia 
* negative 15 ajudou bem pouco na acurácia

Um ponto importante a se considerar é que no dataset existem mais sentenças parecidas do que diferentes. Isso pode influenciar no treinamento pois ele vai ser viesado para sentenças semelhantes. Como podemos ver na matrix de confusão. Algo que podemos fazer pra ajudar a resolver isso, seria acrescentar sentenças diferentes no dataset. Outra coisa a considerar seria tentar outro tipo de modelo como bag of words ou TfidfVectorizer do sklearn que também se baseia na semelhança de cossenos para detectar similaridade.