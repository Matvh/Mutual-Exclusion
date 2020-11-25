# Mutual-Exclusion

<h2>Descripción</h2>
Este proyecto trata de que hay procesos independientes que quieren escribir un mensaje por pantalla. Para alocar el turno se cada proceso se usan los algoritmos de Lamport y Ricart y Agrawala.

<br>

<h2>Entorno</h2>
<br>
1) Hay siete procesos:<br>
        1 HeavyWeight A (HWA)<br>
        1 HeavyWeight B (HWB)<br>
        3 LightWeight A (LWA)<br>
        2 LightWeight B (LWB)<br>
<br> 
2) Hay dos posibles entornos:

        Modo "normal"<br>
        Modo "router"<br>
 <br>
 
 <h4> Modo Normal</h4>
 
 La jerarquía de comunicación es la siguiente:<br>
         Nodo HWA se comunica con los LWAs mediante un socket<br>
         Nodo HWA se comunica con el HWB mediante otro socket<br>
         El Nodo HWB se comunica con los LBBs mediante otro socket<br>
 <br>
 
 ![Version0](https://user-images.githubusercontent.com/24244834/100260976-e4473000-2f28-11eb-81a3-907a6f3e43d6.png)
 
 
 <h4>Modo Router</h4>
 
 La jerarquía de comunicación es la siguiente:<br>
         La comunicación entre los nodos ocurre mediante un "router" que dirije los mensajes al nodo correspondiente<br>
 
<br>

![Version1](https://user-images.githubusercontent.com/24244834/100261025-f032f200-2f28-11eb-94f2-cee7a6b78724.png)

<h2>Funcionamiento</h2>

El programa empieza con el HWA indicandoles a los LWAs que pueden empezar a escribir. Una vez los 3 LWAs hayan escrito en la pantalla, el HWA le indica al HWB que es su turno. El HWB les indica a los 2 LWBs que pueden escribir. Una vez estos terminan el HWB le indica al HWA que es es su turno de escribir y el proceso entero vuelve a empezar.<br>
Para elegir la verisón unicamente hay que cambiar la versión que retorna la función getVersion() de la clase Config.<br>

<h2>Requisitos</h2>

*Los nodos LightWeight escriben por la pantalla<br>
*Los nodos HeavyWeight le indican a los LightWeight que pueden empezar a escribir por pantalla<br>
*Los nodos HeavyWeight "comparten" el recurso mediante un algoritmo Token Based<br>
*Los nodos LightWeightA "comparten" el recurso mediante Lamport<br>
*Los nodos LightWeightB "comparten" el recurso mediante Ricart y Agrawala<br>
*Todas las counicaciones son mediante sockets


<h2>Resultados</h2>

En las siguientes imagenes se pueden ver 2 de los nodos printando por pantalla el mensaje.

<img width="1029" alt="LWA2" src="https://user-images.githubusercontent.com/24244834/100272118-5aec2980-2f39-11eb-8c74-cff791faba91.png">

<img width="1029" alt="LWB1" src="https://user-images.githubusercontent.com/24244834/100272136-62abce00-2f39-11eb-9bf3-beb700bb9e2a.png">

