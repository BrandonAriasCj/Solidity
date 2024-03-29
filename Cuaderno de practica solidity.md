#### Ahorro de gas con "view"
``` Solidity 
funcion test() external view returns(){
//esta funcion de tipo "external view" no gasta gas.
//ya que solo sirve para consultar datos de un nodo local, externamente.
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

#### Modificador de propidad
Otorga permisos de propiedad
``` Solidity
//Owner ya fue definido
modifier onlyOwner(){
	require(msg.sender == owner);
	_;
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

#### Apuntadores
``` Solidity
pragma solidity ^0.4.19;
/* Son objetos en programacion que sirven para almacenar direcciones de memoria */

contract Apuntador{
	struct Persona{
		string name;
		uint DNI;
	}
	
	//Digamos que se tiene el registro de toda la ciudadania de una ciudad.
	Persona[] Ciudadania;
	function CambiarNombre(uint _id, string _NewName) public {
		Persona storage Fulano = Ciudadania[_id];
		// Se puede especificar "storage" o "memory" segun los requerimientos.
		Fulano.name = _NewName;
	}
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

#### Llamar atributos de estructuras en colección
``` Solidity
pragma solidity ^0.4.25;

struct Gato{
	uint fechaAdopcion;
	string nombre;
}

//supongamos que ya tengamos la base de datos de gatos en el array
//cada gato identiifcado con su id
Gato[] Gatos;
fuction CuandoLoAdoptaron(uint _id) public returns(uint){
	uint fecha = Gatos[_id].fechaAdopcion;
	return fecha;
}

```

#### Id de estructuras en colección
``` Solidity
//SPDX-License-Identifier: MIT
pragma solidity ^0.4.25;

contract test {
    event NewPersona(uint id, string name, uint age);

    struct Persona{
	    string name;
	    uint age;
    }

    Persona[] Comunidad;
    function crearPersona(string _name, uint _age) public {
	    uint id = Comunidad.push(Persona(_name, _age)) - 1;
        emit NewPersona(id, _name, _age);
    }
}

```

#### keccak256
``` Solidity
//SPDX-License-Identifier: MIT
pragma solidity ^0.4.25;
//keccak es un algoritmo hash de cifrado.
contract test{
    function kaccek(string _name) public view returns(uint) {
	    uint id = uint(keccak256(abi.encodePacked(_name)));
        return id;
    }
}
```

#### Estructuras y  matrices.
``` Solidity
//SPDX-License-Ientifier: MIT
pragma solidity ^0.8.3;

contract ZombieFactory{
    struct Zombie{
        string name;
        uint dna;
    }

    Zombie[] Cuartel;
	//función que crea un "Zombie" y lo guarda en "Cuartel"
    function CrearZombie(string calldata _name, uint _dna) public {
        Cuartel.push(Zombie("prueva", 1));
    }
}

```

#### Función de tipo "pure"
``` Solidity 
contract functionPure{
	//Facilita la realización de operaciones matemáticas.
	function sumar(uint a, uint b) public pure returns(uint c){
		c = a + b;
	}
}
```














