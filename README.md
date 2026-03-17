# PROYECTO-POO-AV2
# 🚢 Hundir la Flota
## 📌 Descripción
Juego de estrategia por turnos en consola desarrollado en C#.

## 🧩 UML                 +----------------------+
                           |       Program        |
                           +----------------------+
                           | Main()               |
                           +----------------------+
                                      |
                                      ▼
                           +----------------------+
                           |        Juego         |
                           +----------------------+
                           | jugador : Jugador    |
                           | cpu : Cpu            |
                           | render : Renderizador|
                           | gestor : GestorGuard|
                           +----------------------+
                           | Iniciar()            |
                           +----------+-----------+
                                      |
        _____________ ________________|_________________________
       |              |                |                        |
       ▼              ▼                ▼                        ▼

+----------------+  +----------------+  +---------------------+  +----------------------+
|    Jugador     |  |      Cpu       |  |    Renderizador     |  |   GestorGuardado    |
+----------------+  +----------------+  +---------------------+  +----------------------+
| nombre:string  |  |                |  |                     |  |                     |
| tablero:Tablero|  |                |  |                     |  |                     |
| disparos:int   |  |                |  |                     |  |                     |
| aciertos:int   |  |                |  |                     |  |                     |
| fallos:int     |  |                |  |                     |  |                     |
+----------------+  +----------------+  +---------------------+  +----------------------+
| Precision():dbl|  | ElegirObjetivo()| | MostrarBienvenida() |  | Guardar()           |
| RegistrarDisp()|  | ColocarFlota()  | | MostrarTableros()   |  | Cargar()            |
+--------+-------+  +--------▲-------+ | PedirCoordenada()    |  | Eliminar()          |
         |                   |         | MostrarResultado()    |  +----------+----------+
         |                   |         +----------+------------+             |
         ▼                   |                    |                          ▼
+----------------+          |                    ▼                +----------------------+
|    Tablero     |          |           +----------------+       |   EstadoPartida     |
+----------------+          |           |    Colores     |       +----------------------+
| barcos:List    |          |           +----------------+       | datos               |
+----------------+          |           | (constantes)   |       +----------------------+
| TodosHundidos  |          |           +----------------+
| BarcosRestantes|          |           +----------------+
| ObtenerCasilla()|         |           |   ArteAscii    |
| PuedeColocar() |          |           +----------------+
| ColocarBarco() |          |           | (textos UI)    |
| Disparar()     |          |           +----------------+
+--------+-------+          |
         |                  |
    _____|______            |
   |            |           |
   ▼            ▼           |
+-----------+ +-----------+ |
|  Casilla  | |   Barco   | |
+-----------+ +-----------+ |
| fila:int  | | nombre:str| |
| columna   | | tamanio   | |
| disparada | | impactos  | |
| barco     | | casillas  | |
+-----------+ +-----------+ |
| EstaVacia()| | RecibirImpacto() |
| EsImpacto()| | EstaHundido()    |
| EsAgua()   | +------------------+
+-----------+


## 🚢 Flota
- Portaaviones (5)
- Acorazado (4)
- Destructor (3)
- Submarino (3)
- Patrullera (2)

## 🎮 Mecánicas
- Turnos alternos
- Disparos por coordenadas
- Resultados: Agua, Impacto, Hundido

## 📜 Reglas
- No se permiten barcos en diagonal
- No pueden tocarse
- Tablero 10x10