---


---

<h1 id="monitores">Monitores</h1>
<h2 id="primer-problema">Primer Problema</h2>
<pre><code>Monitor BD{
	export;
	variables :
		esperaM,esperaN: condition
		contadorA : int
		contadorB:int
	funcion incio()
		contadorA=0
		contadorB=0
	procedimiento accederM
		if ( contadorA &gt;4){
			delay(esperaM)
		}
		contadorA++;
	}
	procedimiento liberarM{
		contadorA--;
		resume(esperaM);
	}
	procedimiento accederN
		if ( contadorB &gt;5 ){
			delay(esperaN)
		}
		contadorB++;
	}
	procedimiento liberarN{
		contadorB--;
		resume(esperaN);
	}
	procedimiento accederO
		if ( contadorB == contadorA &amp;&amp; contadorA&lt;=4 &amp;&amp; contadorB =4 ){
			delay(esperaO)
		}

	}
}
procedimiento liberarO{
	resume(esperaO);
}
</code></pre>
<h2 id="segundo-problema">Segundo Problema</h2>
<pre><code>Monitor controlaRecursos{
	export iniBusq, finBusq, iniInserc, finInserc, iniDel, finDel
	variables:
		inser,busq,del : condition
		nBusq : int
		borrando,insertando : boolea
	funcion iniBusq(){
		Si(borrando)
			delay(busq);
		Fin_Si
		nBusq++;
		resume(busq)
		
	}
	 funcion finBusq(){
		 nBusq-.;
		Si(nBusq = 0)
			resume(del);
		Fin_Si
		
	}
	funcion iniInserc(){
		si( borrando o insertando)
			delay(inser);
		fin_si
		inser = verdad;

	}
	funcion finInserc(){
		insertando = falso;
		si( no esta vacio (inser))
			resume (inser);
		fin_si
		si no  Si( nBusq = 0)
			resume(del);
		fin_si

	}
	funcion iniDel(){
		si( nBusq &gt; 0)
			delay(del);
		fin_si
		borrando = verdad;

	}
	funcion finDel(){
		borrando = falso;
		si( no esta vacio (busq))
			resume (busq);
		fin_si
		si no  Si(no esta vacio (inser)
			resume(inser);
		fin_si
		resume(del);

	}
</code></pre>
<p>}</p>

