---


---

<h1 id="garciaariasantoniojosesesion07">GarciaAriasAntonioJoseSesion07</h1>
<h1 id="primer-problema">Primer Problema</h1>
<h3 id="declaración--y-inicialización-de-semáforos">Declaración  y inicialización de Semáforos</h3>
<pre><code>Semaforo semAlqRep = 1;
Semaforo semRep = 1;
</code></pre>
<p><strong>Le pasamos por parámetros Lista de Bicicletas bloqueDeBicicletas</strong></p>
<pre><code>Proceso generadorBicicletas(bloqueDeBicicletas):
	para cada bici -&gt; bloqueDeBicicletas:  
    	
		si hayBiciDisponible(bici):
			//Generamos una bici alquilada o repetida para garantizar que  todos los procesos a la vez no generen el estado 
			creo el semaforo alquilada repetida
			wait(semAlqRep);
		    	 generarEstadoBici(bici); 
    		signal(semAlqRep ); 
    	
			si No biciEnReparacion:
				wait(semRep);
					generarEstadoEnRep(bici);
				signal(semRep);
			fin si
		fin si
	fin para
fin proceso
</code></pre>
<h1 id="segundo-problema">Segundo Problema</h1>
<h3 id="declaracion-de-variables-y-semaforos">Declaracion de Variables y Semaforos</h3>
<pre><code>		enumerado estados = {DISPONIBLE, ALQUILADA, EN_REPARACION, EN_TRANSITO,ASIGNADO};
		enumerado smsEstados = { DISPONIBLE: semáforo(1), ALQUILADA: semáforo(1), EN_REPARACION: semáforo(1), EN_TRANSITO: semáforo(1) }
</code></pre>
<h3 id="funciones-para-la-implementacion-del-proceso">Funciones para la implementacion del proceso</h3>
<pre><code> funcion recogerBici(estacion,estado):
	 wait(smsEstados [estado]);
	 //recoge la bici
	 signal(smsEstados[estado]);
</code></pre>
<h2 id="proceso">Proceso</h2>
<pre><code> proceso estacion(estacion):
	  mientras true : 
			  bici = esperarBiciSolicitada();
			 si   bici.estado == estados.ASIGNADO :
					 recogerBicicleta(estacion,bici.estado);
			 fin si 
			 si no 
				 imprimir ( "Bici no esta disponible")
			fin si
		fin mientras
fin proceso
</code></pre>

