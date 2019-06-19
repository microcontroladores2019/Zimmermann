# Programação
O programa atualmente está configurado para que um botão SW no PC15 ative o interrupt que vai se comunicar por SPI com o controlador de LED para acender outro LED.
## Pinagem:

![Pinagem](pinagem.png)

- SW (PC15): recebe o sinal para ativar o interrupt
- LED_RED (PB5): para teste de funcionamento do programa
- LED_YELLOW (PB6): indica que ocorreu o interrupt (nao necessariamente que a comunicação SPI funcionou)


## Configuração do CLK
![Clock](clk.png)

## Periféricos:

- O TLC5922DAP, responsavel por acender os LEDs, é controlado por SPI, desta forma, o uC envia um comando de 16 bits que corresponde a quais LEDs serão acesos. Nele, será conectado um LED em seu Output 6 para verificar se a comunicação teve sucesso.

- O DS2413P+ é o circuito que faz a detecção da armadilha, ele se comunicará por 1wire, mas inicialmente está sendo utilizado um botão SW

## Observação

O botão SW na verdade deveria ser uma ativação por 1wire, mas a biblioteca que consegui é apenas para os modelos STM32F4 e STM32F7, deixei na pasta um arquivo .zip que contém diversas bibliotecas, dentre elas a tm_stm32_onewire.