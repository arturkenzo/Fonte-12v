# Fonte de tensão ajustável
## Lista de componentes Eletrônicos
| componenente | quantidade | preço R$|
| ------------- | ----------- | ------------- |
| transformador 16.9v | 1 | emprestado |
| resistor 1k 0.25w | 4 | 4 * 0.07 |
| resistor 100 0.25w | 1 | 0.07 |
| resistor 120 2w | 1 | 1.90 |
| resistor 2.2k 0.25w | 1 | emprestado |
| LED vermelho | 1 | 0.50 |
| potênciometro 10k | 1 | 7.00 |
| transistor NPN | 1 | 1.55 |
| capacitor 470uF | 1 | 4.27 |
| diodo retificador | 4 | 4 * 0.20 |
| protoboard | 1 | emprestado |
| diodo zener 13v | 1 | 0.50 |
| jumper | 9 | 9 * 0.70|
| total | 18 | 23.17 |

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

## Circuito no falstad
![Screen Shot 2024-06-24 at 4 37 45 PM](https://github.com/arturkenzo/Fonte-12v/assets/170135026/58c8345f-d820-4dd6-b9ad-2a56ab3fc841)

## Cálculos

#### Tensão de Pico
$$ V_{\text{pico}} = V_{\text{eficaz}} \times \sqrt{2} $$

Onde:
- V_{\text{eficaz}} é a tensão de saída do transformador(16.9V).

Portanto:

$$ V_{\text{pico}} = 16.9V \times \sqrt{2} = 23.9V $$

Pelo fato do diodo necessitar 0.7v para funcionar, ao passar pela ponte de diodos a tensão de pico no circuito passa a ser:

$$  V_{\text{pico}} = 23.9V - 1.4V = 22.5V $$

### Cálculo da Tensão de Ripple (Vripple)

Foi calculada para um ripple de 10%

$$ V_{\text{ripple}} = 0.1 \times V_s $$

Substituindo o valor da tensão:

$$ V_{\text{ripple}} = 0,1 \times 22.5V = 2.25 $$

### Cálculo da Tensão Média

$$ V_{\text{médio}} = V_{\text{pico}} - \frac{V_{\text{ripple}}}{2} $$

Substituido valores:

$$ V_{\text{médio}} = 22.5V - 2.25V = 20.25V $$
    
### Correntes:

Para calcular a corrente total, realizamos os seguintes cálculos:

1. Corrente através do LED:

$$ i_{LED} = \frac{V_{máxs} - V_{LED}}{R_{LED}} = \frac{21,1V - 9V}{4400 \ \Omega} \approx 2,75 \ mA $$

2. Corrente através do diodo Zener:

$$ i_{ZENNER} = \frac{V_{máxs} - V_{ZENNER}}{R_{ZENNER}} = \frac{21,1V - 12,9V}{2200 \ \Omega} \approx 3,72 \ mA $$

3. Corrente através do potenciômetro:

$$ i_{POTENCIÔMETRO} = \frac{V_{máxs}}{R_{POTENCIÔMETRO}} = \frac{21,1V}{5000 \ \Omega} \approx 4,22 \ mA $$

4. Corrente através do transistor:

$$ i_{TRANSISTOR} = \frac{V_{máxs}}{R_{TRANSISTOR}} = \frac{21,1V}{230 \ \Omega} \approx 91,73 \ mA $$

Somando todas as correntes, obtemos a corrente total:

$$ i_{TOTAL} = 2,75 \ mA + 3,72 \ mA + 4,22 \ mA + 91,73 \ mA = 102,42 \ mA $$

##
### Capacitância:

Para o cálculo da capacitância, usamos a frequência f = 120 Hz, pois a frequência de saída é o dobro da frequência de entrada devido à retificação em onda completa na ponte:

$$ C = \frac{i_{TOTAL}}{f \cdot V_{ripple}} = \frac{102,42 \times 10^{-3} \ A}{120 \ Hz \cdot 2,1 \ V} \approx 405,47 \ \mu F $$

O valor comercial mais próximo do valor teórico é 470 µF 50V. Optamos por um valor com uma margem de aproximadamente 16% acima do valor teórico.

##





