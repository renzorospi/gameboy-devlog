Las instrucciones más comunes, hay 22. 

Toman dos operandos: el destino y la fuente, y copian el valor de la fuente en el destino.

`ld c, 57 ; load value 57 into (c)`
`ld d, b ; load the value of (b) into (d)`
`ld a, [$1234] ; load the value at address $1234 into (a)`
`ld [hl], a ; load the value of (a) into the address inside (hl)`

Los corchetes indican una dirección en vez de un valor.
Si usamos un registro de 16bits, como dirección entre corchetes, se le llama direccionamiento indirecto. 

Note that many load instructions are onlyavailable for (a) or (hl). For example, loading from a hardcoded address is only possible with (a).
Likewise, some forms of indirect addressing are only possible through (hl), not through (bc) or (de).

Out of the 22 variations of loads, 4 are ldh instructions. ldh works like ld, but it can only load to and from an address in the range [$FF00-$FFFF], i.e. I/O registers, HRAM and IE. The advantage of the ldh instruction is that it is both smaller and faster.

`ld [$FF80], a ; 3 bytes, 4 cycles`
`ldh [$FF80], a ; 2 bytes, 3 cycles`
`ldh [c],a ; 1 byte, 2 cycles (assuming (c) holds $80)`

Algunos loads tienen efectos secundarios. Solo hay 4 de esos:
- (hli) y (hld) en lugar de (hl) para incrementar o decrementar (hl) luego de que la instrucción de load se ejecuta. (hli y (hld) no son registros, la instrucción se hace en (hl)). Al usar (hli) el incremento en (hl) es gratis. Lo mismo con (hld)

`Listing 5. Load side effects`
`ld [hli], a ; 1 byte, 2 cycles`
`Listing 6. Load side effects`
`ld [hl], a ; 1 byte, 2 cycles`
`inc hl ; 1 byte, 2 cycles`

- (ldi) y (ldd) es el equivalente a usar ld con [hli] y [hld]

`ldd a, [hl]`

`es lo mismo que`

`ld a, [hld]`