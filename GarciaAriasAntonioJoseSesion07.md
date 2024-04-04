---


---

<h1 id="garciaariasantoniojosepractica2">GarciaAriasAntonioJosePractica2</h1>
<h2 id="diseño-e-implementacion-de-funcionamiento-líneas-autobuses">Diseño e implementacion de funcionamiento líneas autobuses</h2>
<h3 id="monitores">Monitores</h3>
<h3 id="control-de-autobuses">Control de autobuses</h3>
<h4 id="condiciones">Condiciones:</h4>
<p><strong>Bajar Bus</strong> : Que el usuario deje el autobús cuando llegue a la parada de destino de su viaje.<br>
<strong>SubirAutobus</strong> : Que el usuario suba al bus cuando sea posible.<br>
<strong>EsperaAutobus</strong>:  Que un usuario espere en una parada la llegada de un autobús para dirigirse a su parada de destino.<br>
<strong>BusEnParada</strong> : Que un autobús llegue a una parada para dejar a los usuarios que se bajan en esa parada antes de dejar subir a los que estén esperando en esa parada.<br>
<strong>MontaBus</strong>  : Que el usuario deberá montar en el autobús cuando llegue a la parada donde se encuentra esperando si hay sitio en el autobús.</p>
<h3 id="proceso-usuario">Proceso Usuario:</h3>
<p>Este proceso simulara	el comportamiento de un usuario que quiere entrar en el autobús y parar en su debida parada.<br>
-Parada de origen<br>
-Parada de destino</p>
<ul>
<li>Sube en el bus y si baja se termina el proceso</li>
</ul>
<h1 id="analisis">Analisis</h1>
<pre><code>Para esta practica hablare de los elementos compartidos que utilizaré entre diferentes procesos .
</code></pre>
<h3 id="constantes">Constantes</h3>
<p><strong>PARADAS</strong> paradas de una línea.<br>
<strong>NAUTOB</strong> número de autobuses recorriendo la línea.<br>
<strong>NPASAJEROS</strong> numero de pasajeros que puede ir por autobús .</p>
<h3 id="variables-compartidas--no-hay-puesto-lo-unico-que-compartire-es-el-monitor.">Variables compartidas : No hay puesto lo unico que compartire es el monitor.</h3>
<h3 id="monitorcontrolautobus">MonitorControlAutobus</h3>
<pre><code>Se encargara de controlar la entrada y salida de personas al  autobus. Para ello dispondrá de los siguientes procesos
 

Autobus esperaAutobus ( paradaDeOrigen) 
//Este procedimineto permite a una persona esperar al autobus
//Parada de Origen es la parada donde se encuentra el bus
Autobus subirAutobus(idAutobus)
//Se comprueba 
//1 -&gt; Si  el autobus esta lleno o no
// 1a -&gt; Si no esta lleno entra persona y va avisando diferentes 	personas hasta que se quede sin capacidad el bus
// 1b-&gt; En caso de estar lleno la persona se esperara a que el autobus este vacio 
Autobus autoBusEnParada(idAutobus)
//1 .Se comprueba si hay persona que quieran bajar del bus . 
// 1a Si las hay se liberan y se bloquea
// 1b Si no , se comprueba que hay alguna persona que quiera subir al bus .Si hay capacidad y hay persona se liberara y se bloqueara
</code></pre>

