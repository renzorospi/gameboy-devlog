(a). Acumulador: aritmética en 8bits y lógica.
(b), (c), (d), (e), (h), (l). Guardar datos temporalmente mientras se trabaja con (a)
(bc), (de), (hl). Normalmente usado para sostener valores 16bits y ejecutar direcciones indirectas. (hl) es el más versátil y puede hacer operaciones de 16 bits.
(f). Flag o status. No es usado directamente, tiene más bien 4 flags: Z, N, H y C. Esto son bits que se setean o resetean depediendo del resultado de la última instrucción que les afectó.

Banderas:

Z: Zero. Si el resultado de una operación es Zero, Z se setea. Si no, Z se resetea. Para implementar instrucciones condicionales o if/else statements y loops.

C: Carry. Para hacer carry/borrow a adiciones y sustracciones.

N y H: Relacionados a BCD (Binary-Coded Decimal). N es la bandera de Añadir y sustraer, Negative Flag. Indica si la operación fue una resta. H es la Half carry flah. Sostiene la parte menor (los 4 bits más bajos) de una operación aritmética. La única instrucción que pueden recibir es **daa**, que se usa para convertir el resultado de una operación aritmética de dos números BCD de vuelta a BCD. BCD sirve para representar números decimales pero no es relevante para la programación típica para DMG a menos que quieras hacer una calculadora o aplicación financiera.

(pc): Program Counter. Apunta a la siguiente instrucción que será ejecutada por la cpu. 
(sp): Stack counter. Para guardar data temporalmente, pero más se usa para llamadas a funciones. Cuando se llama una función, la dirección de retorno es guardada en el stack. El stack de DMG es siempre push-down. Al iniciar el programa, (sp) siempre se inicializa en la dirección más alta de la HRAM ($FFFE) pero puede reubicarse, por ejemplo en la WRAM solo cambiando el valor de (sp). Llamar una función resta sp y retornar de una función lo aumenta.![[Pasted image 20250425192730.png]]