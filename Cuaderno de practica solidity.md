#### Implementación de una interfaz
``` Solidity
/* imaginamos que ya creamos una interfaz (Interfaz) que dentro tiene
una funcion (gerNumber) que debuelve un numero */

address _DireccionContact = 2x542234d533s35444..
Interfaz _Apuntador = Interfaz(_DireccionContract);

funcion somefuncion(address _skt){
	uint num = _Apuntador.gerNumber(_skt);
	// ahora puedo hacer algo con num
}

```

#### Cómo relizar una herencia e importarlo
``` Solidity
/* Para poder heredar un contrato es necesario comenzar el contrato
heredero de la siguiente forma. */

contract _Heredero is _Origen {
}

/* Y para poder anexarlo se debe importar de la siguiente manera en la
parte superio */

import "./_origen.sol";

------------------------------------------------------------------
// junto saldría así:
import "./_origen.sol";

contract _Heredero is _Origen {
}
```

#### Manejar multiples valores
Sirve para guardar los valores de retorno de una funcion en variables para utilizarlas.
``` Solidity
function RetornosMultiples() public returns(uint a, uint b, uint c){
	return (1, 2, 3);
}

function obtenerUltimoValorRetorno() external {
	uint c;
	(,,c) = RetornosMultiples();
}
```

#### Modificador de propidad
Otorga permisos de propiedad
``` Solidity
//Owner ya fue definido
modifier onlyOwner(){
	require(msg.sender == owner);
	_;
}
```

#### Usabilidad del tiempo
Manejando algunos conceptos de tiempo.

``` Solidity 
// SPDX-License-Identifier: MIT
pragma solidity ^0.6.0;

contract carreraDay{
	uint tiempoDisponible = 1 days;
 
 //El Keyword "now" solo es valido hasta antes de la version 0.7.0
 	function Now() public view returns(uint){
 		return now;
 	}
 
 	function obtenerTiempoTerminado() public view returns(uint){
 		uint tiempo = uint(now + tiempoDisponible);
 		return tiempo;
 	}
}
```

#### Usabilidad del tiempo
Manejando algunos conceptos de tiempo.

``` Solidity 
// SPDX-License-Identifier: MIT
pragma solidity ^0.6.0;

contract carreraDay{
	uint tiempoDisponible = 1 days;
 
 //El Keyword "now" solo es valido hasta antes de la version 0.7.0
 	function Now() public view returns(uint){
 		return now;
 	}
 
 	function obtenerTiempoTerminado() public view returns(uint){
 		uint tiempo = uint(now + tiempoDisponible);
 		return tiempo;
 	}
}
```

#### Ahorro de gas con "view"
``` Solidity 
funcion test() external view returns(){
//esta funcion de tipo "external view" no gasta gas.
//ya que solo sirve para consultar datos de un nodo local, externamente.
}

```


