# Assembly

* Atividade 1

## Como funciona a alocação de memoria dinamica para armazenar seu nome?

A alocação de memoria dinâmica é um procedimento que destina espaço na memória do computador conforme exigido durante a execução de um programa. Enquanto a reserva estática reserva um espaço específico de memória para variáveis previamente conhecidas, a reserva dinâmica possibilita a adaptação do espaço conforme demandado durante a execução do programa. Esta capacidade é particularmente vantajosa quando o tamanho exato da memória necessária não é previamente conhecido ou pode variar. Diferentemente da alocação estática, que pode ser realizada através da atribuição de valores hexadecimais para cada caractere de uma string, a alocação dinâmica é comumente executada através de funções como malloc() em linguagens de alto nível ou por meio de chamadas de sistema em Assembly. Essas abordagens permitem a alocação e a liberação de memória conforme exigido, aumentando a flexibilidade e a eficiência do programa em termos de gerenciamento de recursos.

* Atividade 2

## O que é DOS?

Em linguagem Assembly, o termo "DOS" se refere ao "Disk Operating System", um sistema operacional de disco que era amplamente utilizado em computadores pessoais durante as décadas de 1980 e 1990. Tipicamente, programas escritos em Assembly para o "DOS" interagem diretamente com os componentes físicos do computador, como a tela e o teclado, utilizando chamadas específicas do sistema operacional ou chamadas de BIOS. Os registradores, que são pequenas unidades de armazenamento dentro do processador, desempenham um papel crucial. Eles mantêm temporariamente dados, endereços de memória e sinais de status, sendo indispensáveis para garantir que as operações sejam executadas de forma eficiente.

Print marie.js

![print marie js](https://github.com/AlbertoZamarchi/Assemblye/assets/107437069/24af87b2-5871-4bef-ae68-b1bf7bdbc951)

* Programa de início no endereço 000
* Load = Carregando o valor
* Store = Definindo como esse valor vai ser chamado futuramente dentro do processo
* Halt = Encerrar uma execução

### Código do print comentado.

```
.MODEL small;Define o modelo de memoria small
.STACK 64;Aloca 
um escopo de 64 bytes para a pilha

.DATA ;Inicia a seção de dados
message db 'Soldador', '$'; Uma string com o texto "Soldador" e o caractere $ (fim da string)

.CODE ;Inicia a seção de código

.CODE ;Define  o ponto de entrada do programa, é executado automaticamente quando o programa in
main proc ;Define  o procedimento main como o ponto de entrada do programa

mov ax, @data ;Carrega os dados na memória
mov  ds, ax ;Coloca o segmento dos dados no registrador DS

mov ah, 9h ;Prepara o registrador  AH para enviar uma mensagem de saída

mov dx, offset message ;Pega o endereço da variável message e coloca em DX

int 21h ; Instrução de interrupção

main endp ; Marca o fim do procedimento
end main; Indica o fim
```

* Print do código rodando

![Captura de Tela (60)](https://github.com/AlbertoZamarchi/Assemblye/assets/107437069/4cfbdfeb-7a0c-4afa-b3ba-2dba91d5dc80)


