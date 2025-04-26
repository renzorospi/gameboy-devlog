## Formatos numéricos
Hexadecimal: $
Binario: %
Decimal: Sin signo

## Sintaxis
![[Pasted image 20250425192927.png]]

Solo se puede tener un elemento de cada tipo por línea.
Cada elemento es opcional.
Si se tiene más de un elemento, el orden importa. 

## Etiquetas
Símbolos seguidos por dos puntos (:)
Deben definirse una sola vez y se les asigna una dirección cuando el toolchain procese nuestro código. 

## Comentarios
Todo lo que venga luego de un ; es ignorado.

## Instrucciones
En la DMG solo hay 107 instrucciones, pero realmente muchos son similares así que solo hay que aprender 44 mnemónicos. 

![[Pasted image 20250425193624.png]]

## Costo de bytes

The more specific the instruction, the less byte it takes.
Usually, using registers as parameters increase specificity. On the other hand, literals and addresses
decrease specificity.

## Costo de ciclos

A natural way to express the execution cost of an instruction would be to use T-states, also known as clock ticks. For example, nop takes 4 T-states and ld a, $FF takes 8 T-states to execute. Every
instruction takes a multiple of four T-states to execute, i.e. they take either 4, 8, 12, 16, 20 or 24 clock
ticks to complete. In this book, execution time is expressed in machine cycles (M-cycles) instead. A M-cycle is equal to 4 T-states.

La cpu anda a 4.194303MHz o, expresado en M-cycles, 1.048576 MHz. Es decir el máximo teórico de instrucciones que puede ejecutar por segundo.

