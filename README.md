# Student-grade-average-algorithm
An algorithm that reads the grades of a student, then does the average of them, if the result is below the grade 7, they can do a replacement grade for the lowest one and then check again if they will pass or not


# Algoritmo de média de notas de um aluno
Um algoritmo que lê as notas de um aluno, depois faz a média delas, caso o resultado fique abaixo da nota 7, ele pode fazer uma substituição da nota mais baixa e depois verificar novamente se vai passar ou não

const prompt = require('prompt-read')

console.clear()

var n1, n2, n3, n4, media, subs, menorNotaOriginal //declara as variáveis

n1 = prompt('Digite a primeira nota: ', 'number')
n2 = prompt('Digite a segunda nota: ', 'number')
n3 = prompt('Digite a terceira nota: ', 'number')
n4 = prompt('Digite a última nota: ', 'number')

media = (n1 + n2 + n3 + n4) / 4 //faz o cálculo da média

console.log('#############################\n')

console.log('Sua nota final foi de: ', media) //resultado da média

if (media >= 7){    
    console.log('Parabéns!!! Você passou!!!') //mensagem de aprovado caso a média seja maior que 7
} else{
    console.log('A que pena, você ficou de recuperação!!! Mas você tem a oportunidade de fazer uma prova de substituição!!!') //mensagem de recuperação
    subs = prompt('Digite a nota de substitução: ', 'number')

    menorNotaOriginal = n1 //variável recebe nota 1 e assume ser a menor nota
    if(n2 < menorNotaOriginal){
        menorNotaOriginal = n2
    }
    if(n3 < menorNotaOriginal){
        menorNotaOriginal = n3
    }
    if(n4 < menorNotaOriginal){
        menorNotaOriginal = n4 //verifica com todos se é a menor nota, caso não seja, troca com a menor nota
    }
    media = (n1 + n2 + n3 + n4 - menorNotaOriginal + subs) / 4; //utiliza a nota para a média nova
console.log('Sua nota final após a substituição é: ', media) //mostra resultado de média

//se for maior ou igual a 7, mostra mensagem de reprovado
if (media >= 7) {
    console.log('Parabéns você passou com a nota nova')
} else {
    console.log('Que pena, você reprovou :(')
}
}
