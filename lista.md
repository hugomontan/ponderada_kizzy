
**1)** Considere o seguinte código JavaScript:

```javascript
//EX01
let p = 10;
let q = 3;
let r = 6;

let resultado = (p % q === 1) && (r * 2 > p) || (q + r < p);
console.log(resultado);

const valores = [3, 6, 9, 12, 15];
let produto = 1;

for (let j = 0; j < valores.length; j++) {
  produto *= valores[j];
}

console.log('O produto dos valores é:', produto);


```
Qual das seguintes alternativas melhor descreve o que o código faz?

A) O código avalia a expressão booleana, imprime `true`, calcula o produto dos números na lista e imprime o resultado no console.

B) O código avalia a expressão booleana, imprime `false`, calcula o produto dos números na lista e imprime o resultado no console.

C) O código avalia a expressão booleana, imprime `true` e, em seguida, verifica se o número 6 está na lista.

D) O código avalia a expressão booleana, imprime `false` e ordena os valores em ordem crescente.

** RESPOSTA: **

(A)

Após definir p, q e r, o código faz a avaliação de uma expressão lógica na linha 6: 

```let resultado = (p % q === 1) && (r * 2 > p) || (q + r < p)```

Nela, ele verifica o resto da divisão entre p e q, e se ele possui igualdade estrita com 1. Essa condição está conectada com &&, na colocação de que o dobro de r é maior que p. 

Como 10/3 possui resto 1 e 6*2 é maior que 10, as duas primeiras colocações são culminam em true. A terceira colocação (q + r < p), também é verdadeira, uma vez que (3+6 < 10). 

Logo ```true || true = true```, imprimindo. 

Em sequência, o código apresenta um array composto por 5 números, iterando eles mesmos e obtendo o resultado de 29160, que é impresso. 

______

**2)** O código a seguir contém duas funções que calculam o limite de crédito de um cliente com base nos seus gastos e na renda mensal.

```javascript
// Versão 1 da função de análise de crédito
function analisarCredito1() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    do {
        totalCompras += compras[i];
        i++;
    } while (limite >= totalCompras && i < compras.length);

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```

```javascript
// Versão 2 da função de análise de crédito
function analisarCredito2() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    while (limite >= totalCompras && i < compras.length) {
        totalCompras += compras[i];
        i++;
    }

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```
Se ambas as funções forem executadas com os valores fornecidos, qual será a saída exibida no console?

A) Ambas as funções exibirão: 'Seu crédito foi aprovado. Saldo disponível: 400.'

B) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -600.', enquanto analisarCredito2() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.'

C) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.', enquanto analisarCredito2() exibirá: 'Seu crédito foi aprovado. Saldo disponível: 100.'

D) Ambas as funções exibirão: 'Seu crédito foi aprovado Saldo disponível: 500.'

** RESPOSTA: **

(A) 

Ambas as funções irão retornar o mesma resposta, comunicando crédito aprovado e um saldo disponível de 400, uma vez que a lógica do código é exatamente a mesma. 

A única diferença entre os mesmos é a estrutura de do ‘while/do’. Enquanto a versão 1, que utiliza ‘do/while’ , roda o bloco de código para cada um dos blocos possíveis, a versão 2, que utiliza ‘while’, verifica a condição antes da execução, descartando possibilidades sem de fato rodar o cenário em questão. 
______

**3)** Considere o seguinte trecho de código em JavaScript:
```javascript
//EX03
const idade = 21;

if (idade >= 18 && idade < 60) {
  console.log('Você é um adulto!');
} else if (idade < 18) {
  console.log('Você é menor de idade!');
} else {
  console.log('Você está na melhor idade!');
}
```
Qual das seguintes alternativas melhor descreve o comportamento do código?

A) O código verifica se a idade indica um adulto ou um idoso e exibe a mensagem correspondente.

B) O código verifica se a idade pertence à faixa adulta. Se for, exibe 'Você é um adulto!'. Caso contrário, verifica se é menor de idade e exibe 'Você é menor de idade!'. Se nenhuma das condições anteriores for verdadeira, exibe 'Você está na melhor idade!'.

C) O código verifica se a idade está entre 18 e 60 anos e, se for, imprime 'Você é um adulto!'. Se não estiver nesse intervalo, imprime 'Você está na melhor idade!'.

D) O código verifica se a idade é menor de 18, entre 18 e 60 ou acima de 60, imprimindo uma mensagem específica para cada caso.

** RESPOSTA: **

(B)

O código verifica primeiramente se a idade está na faixa adulta, ou seja, se é maior ou igual a 18 e menor que 60. Se isso é verdadeiro, ele imprime 'Você é um adulto!'. Caso contrário, ele verifica se a idade é menor que 18, e se for, imprime 'Você é menor de idade!'. 
Se ambas as condições não forem verdade, ele exibe a mensagem ‘Você está na melhor idade’, se referindo a acima de 60 anos. 

______

**4)** Qual será o resultado impresso no console após a execução do seguinte código?
```javascript
//EX04
var energiaDisponivel = 1200;
var bateriaExtra = 400;
var consumoDispositivos = [300, 600, 500, 200, 400];

for (var i = 0; i < consumoDispositivos.length; i++) {
    var consumo = consumoDispositivos[i];

    if (consumo <= energiaDisponivel) {
        console.log('Dispositivo ' + (i+1) + ' ligado. Energia restante: ' + (energiaDisponivel - consumo));
        energiaDisponivel -= consumo;
    } else if (consumo <= energiaDisponivel + bateriaExtra) {
        console.log('Dispositivo ' + (i+1) + ' ligado com bateria extra. Energia restante: ' + ((energiaDisponivel + bateriaExtra) - consumo));
        energiaDisponivel = 0;
        bateriaExtra -= (consumo - energiaDisponivel);
    } else {
        console.log('Dispositivo ' + (i+1) + ' não pode ser ligado. Energia insuficiente.');
    }
}
```

Escolha a opção que responde corretamente:

A)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 ligado com bateria extra. Energia restante: 0

Dispositivo 5 ligado. Energia restante: -200

B)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

C)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 400

Dispositivo 4 não pode ser ligado. Energia insuficiente.

D)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado. Energia restante: 300

Dispositivo 3 ligado com bateria extra. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

** RESPOSTA: **

(D)
______

**5)** Qual é a principal função do método update() em um jogo desenvolvido com Phaser.js?

Escolha a opção que melhor descreve seu propósito:

A) O método update() é responsável por carregar os assets do jogo antes da cena ser exibida.

B) O método update() é chamado continuamente a cada quadro (frame) do jogo, sendo usado para atualizar a lógica, movimentação e interações dos objetos na cena.

C) O método update() renderiza todos os sprites na tela e garante que a física do jogo seja processada corretamente.

D) O método update() é chamado apenas uma vez após a criação da cena, sendo utilizado para configurar variáveis iniciais do jogo.

** RESPOSTA: **

(B)

O método update() no Phaser é chamado a cada quadro do jogo, sendo vital para atualizar a movimentação lógica entre outros, garantindo a atualização constante do jogo diante das interações dos usuários.

______


**6)** Qual é o principal objetivo do módulo Matter.js Physics em Phaser.js?

Escolha a opção que responde corretamente:

A) Simular física avançada, incluindo corpos rígidos, colisões complexas e interação entre objetos com gravidade e forças.

B) Gerenciar eventos de entrada do usuário, como cliques e toques na tela, permitindo movimentação de personagens.

C) Renderizar gráficos otimizados para jogos 2D e garantir uma taxa de quadros estável.

D) Criar animações automáticas para sprites e objetos interativos sem necessidade de programação de movimentação.

** RESPOSTA: **

(A) 

Matter.js no Phaser serve para simular a física no jogo, sendo o responsável por colisões e movimentos realistas dos objetos e lidando com conceitos simulados como gravidade, forças e interações entre os objetos.

______

# Questões dissertativas

**7)** Uma loja online deseja implementar um sistema de classificação de pedidos com base no valor total da compra. O sistema deve determinar a categoria de um pedido com as seguintes regras:

```

Pedidos abaixo de R$50,00 → 'Frete não disponível!'

Pedidos entre R$50,00 e R$199,99 (inclusive) → 'Frete com custo adicional!'

Pedidos de R$200,00 ou mais → 'Frete grátis!'
```
Implemente um pseudocódigo que receba o valor total da compra e exiba a classificação correta do frete para o cliente.

** RESPOSTA: **
```pseudocodigo
inicio
   leia valortotal
   se valortotal < 50
      escreva 'Frete não disponível!'
   senão se valortotal >= 50 e valortotal <= 199.99
      escreva 'Frete com custo adicional!'
   senão
      escreva 'Frete grátis!'
fim
```
______

**8)** Considere a implementação da classe base Veiculo em um sistema de modelagem de veículos. Sua tarefa é implementar, utilizando pseudocódigo, as classes derivadas Carro e Moto, que herdam da classe Veiculo, adicionando atributos específicos e métodos para calcular o consumo de combustível de um carro e de uma moto, respectivamente.

```
classe Veiculo:
   atributos:
      modelo
      ano

   metodo construtor(modelo, ano):
      definir this.modelo = modelo
      definir this.ano = ano

   metodo calcularconsumo():
      escreva 'Método calcularconsumo não implementado na classe base.'
classe Carro herda Veiculo:
   atributos:
      eficiencia  // km/l

   metodo calcularconsumo(quilometragem):
      retornar quilometragem / eficiencia

classe Moto herda Veiculo:
   atributos:
      eficiencia  // km/l
   metodo calcularconsumo(quilometragem):
      retornar quilometragem / eficiencia
```

Implementação genérica para cálculo de consumo, a ser sobrescrita pelas subclasses.
Agora, implemente as classes Carro e Moto, garantindo que ambas herdem de Veiculo e possuam métodos específicos para calcular o consumo de combustível com base na quilometragem e eficiência do veículo.

** RESPOSTA: **

```
classe automovel:
   atributos:
      modelo
      ano

   metodo construtor(modelo, ano):
      definir this.modelo = modelo
      definir this.ano = ano

   metoodo calcularconsumo():
      escreva 'metodo calcularconsumo não implementado na classe base.'’
```

______

**9)** Você é um cientista da NASA e está ajudando no desenvolvimento de um sistema de pouso para sondas espaciais em Marte. Seu objetivo é calcular o tempo necessário para que a sonda reduza sua velocidade até um nível seguro para pouso, considerando uma velocidade inicial de entrada na atmosfera marciana e uma taxa de desaceleração constante causada pelo atrito atmosférico e retrofoguetes.

Entretanto, a sonda não pode ultrapassar um tempo máximo de descida para evitar desvios orbitais, nem pode desacelerar além de um limite mínimo, pois isso poderia causar instabilidade no pouso.

Implemente a lógica dessa simulação em pseudocódigo, considerando a seguinte equação para atualização da velocidade:

Considere a fórumla de atualização velocidade:
```
    velocidade = velocidadeInicial - desaceleracao * tempo
```
Seu programa deve determinar quanto tempo será necessário para que a sonda atinja uma velocidade segura de pouso, sem ultrapassar os limites estabelecidos.

** RESPOSTA: **

```
inicio
   leia velocidadeInicial
   leia desaceleracao
   leia velocidadesegura
   leia tempoMaximo
   tempo = 0
   velocidade = velocidadeInicial
   
   enquanto velocidade > velocidadesegura e tempo < tempoMaximo:
      velocidade = velocidade - desaceleracao
      tempo = tempo + 1

   se velocidade <= velocidadesegura:
      escreva 'A sonda atingiu a velocidade segura de pouso em ' + tempo + ' segundos.'
   senao se tempo >= tempoMaximo:
      escreva 'Tempo máximo de descida atingido antes de atingir a velocidade segura.'
fim
```

______

**10)** Em um sistema de análise financeira, as operações de investimento de uma empresa podem ser representadas por matrizes, onde cada linha representa um tipo de investimento e cada coluna representa um período de tempo.

A seguir, é fornecida a implementação da função SomarMatrizesInvestimento(matrizA, matrizB), que soma os valores de duas matrizes de investimento. Sua tarefa é implementar uma função semelhante, porém que realize a multiplicação das matrizes de investimento, determinando como os investimentos afetam os resultados ao longo do tempo.

```
função multiplicarMatrizesInvestimento(matrizA, matrizB):  
    se tamanho(matrizA[0]) ≠ tamanho(matrizB) então:  
        retornar 'Não é possível multiplicar - dimensões incompatíveis'  
    
    senão:  
        linhasA < - tamanho(matrizA)  
        colunasA < - tamanho(matrizA[0])  
        colunasB < - tamanho(matrizB[0])  
        matrizResultado < - novaMatriz(linhasA, colunasB)  

        para i de 0 até linhasA-1 faça:  
            para j de 0 até colunasB-1 faça:  
                matrizResultado[i][j] < - 0  
                para k de 0 até colunasA-1 faça:  
                    matrizResultado[i][j] < - matrizResultado[i][j] + matrizA[i][k] * matrizB[k][j]  

        retornar matrizResultado  

função imprimirMatriz(matriz):
   para cada linha na matriz:
      escrever(linha)
```
