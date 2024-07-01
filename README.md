# Fonte de tensão ajustável
## Lista de componentes Eletrônicos
| componenente | quantidade | preço R$|
| ------------- | ----------- | ------------- |
| transformador 16.9v | 1 | emprestado |
| resistor 1k 0.25w | 5 | 5 * 0.07 |
| resistor 100 0.25w | 2 | 0.07 |
| resistor 120 2w | 2 | 2 * 1.90 |
| resistor 330 0.25w | 1 | emprestado |
| LED vermelho | 1 | 0.50 |
| potênciometro 10k | 1 | 7.00 |
| transistor NPN | 1 | 1.55 |
| capacitor 470uF | 1 | 4.27 |
| diodo retificador | 4 | 4 * 0.20 |
| protoboard | 1 | emprestado |
| diodo zener 13v | 1 | 0.50 |
| jumper | 9 | 9 * 0.70|
| total | 18 | 25.21 |

## Explicação dos componentes
* ### Transformador
Recebe uma tensão de 127v e fornece uma tensão de 16.9v.
* ### Resistores
Servem para regular a corrente que percorre pelas regiões do circuito
* ### Diodos retificadores
Utilizados na construção da ponte de diodos, módulo que tem a função de permitir que a corrente alternada só flua em um único sentido.
* ### Diodo zener
Serve para regular a tensão máxima, quando a tensão supera 13v, a tensão de ruptura, o zener permite a passagem de corrente, mantendo a tensão em 13v. Caso a tensão seja inferio a à tensão de ruptura ele não conduz corrente e não afeta o circuito.
* ### Transistor
Componente que permite a passagem de corrente do coletor ao emissor em uma proporção relacionada à corrente da base.
* ### Potenciômetro
Serve como um resistor variável, aplicado para controlar a corrente que chega à base do transistor.
* ### LED
Utilizado para indicar que a fonte está ligada.

## Cálculos

#### Tensão de Pico
$$ V_{\text{pico}} = V_{\text{eficaz}} \times \sqrt{2} $$

Onde:
-  V(eficaz) é a tensão de saída do transformador(16.9V).

Portanto:

$$ V_{\text{pico}} = 16.9V \times \sqrt{2} = 23.9V $$

Pelo fato do diodo necessitar 0.7v para funcionar, ao passar pela ponte de diodos a tensão de pico no circuito passa a ser:

$$  V_{\text{pico}} = 23.9V - 1.4V = 22.5V $$

##

### Cálculo da Tensão de Ripple (Vripple)

Foi calculada para um ripple de 10%

$$ V_{\text{ripple}} = 0.1 \times V_s $$

Substituindo o valor da tensão:

$$ V_{\text{ripple}} = 0,1 \times 22.5V = 2.25 $$

##

### Cálculo da Tensão Média

$$ V_{\text{médio}} = V_{\text{pico}} - \frac{V_{\text{ripple}}}{2} $$

Substituido valores:

$$ V_{\text{médio}} = 22.5V - 2.25V = 20.25V $$

##
    
### Correntes:

Para calcular a corrente total, realizamos os seguintes cálculos:

1. Corrente através do LED:

$$ i_{LED} = \frac{V_{máxs} - V_{LED}}{R_{LED}} = \frac{22.5V - 2V}{3000 \ \Omega} = 6.83 \ mA $$

2. Corrente através do diodo Zener:

$$ i_{ZENNER} = \frac{V_{máxs} - V_{ZENNER}}{R_{ZENNER}} = \frac{22.5V - 13V}{1000 \ \Omega} = 9.5 \ mA $$

3. Corrente através do potenciômetro:

$$ i_{POTENCIÔMETRO} = \frac{V_{máxs}}{R_{POTENCIÔMETRO}} = \frac{22.5V}{11330 \ \Omega} = 1.98 \ mA $$

4. Corrente através do dispositivo carregado:
Pela especificação do projeto desejado:

$$ i_{dispositivo} = \frac{V_{dispositivo}}{R_{dispositivo}} = \frac{12V}{120 \ \Omega} = 100 \ mA $$

Somando todas as correntes, obtemos a corrente total:

$$ i_{TOTAL} = 6.83 \ mA + 9.5 \ mA + 1.98 \ mA + 100 \ mA = 118 \ mA $$

##
### Capacitância:

$$ C = \frac{i_{TOTAL}}{2 \cdot f \cdot V_{ripple}} = \frac{118 \cdot 10^{-3} \ A}{2 \cdot 60 \ Hz \cdot 2,25 \ V} = 437.14 \ \mu F $$

O capacitor com valores mais próximos do calculado foi o de 470 μF e 50V


## Circuito no falstad
![Screen Shot 2024-07-01 at 10 47 07 AM](https://github.com/arturkenzo/Fonte-12v/assets/170135026/fe80ed29-d668-4f3f-bb52-e5e1243fb663)

link para o circuito: [https://tinyurl.com/yv4239pf](https://tinyurl.com/2ear38xq)

## Circuito no EAGLE
![Screen Shot 2024-07-01 at 10 51 47 AM](https://github.com/arturkenzo/Fonte-12v/assets/170135026/1e5b13a0-0bd2-4efd-98c3-c520a975d593)

## PCB
![Screen Shot 2024-07-01 at 10 51 00 AM](https://github.com/arturkenzo/Fonte-12v/assets/170135026/95fe7174-6d24-477a-ac77-6137011e5b10)

## Vídeos
Funcionamento : https://youtu.be/CFbQPkqZoBA?si=sZFjp3oOQ8Yp5rht

Explicação : https://youtu.be/kjJQ-7R_JkI?si=ItOPBa2mSkVKAqxD

## Autores :

* Artur Kenzo Obara Kawazoe - 15652663    
* João Victor Alonso de Mello - 10951790
* Murilo Leandro Garcia - 15480943





