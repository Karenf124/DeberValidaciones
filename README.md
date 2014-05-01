DeberValidaciones
=================

Validaciones números primos, binarios etc
<html>
<head> <center>VALIDACION</center></P>
<head> 
<title>VALIDACIONES</title>
<ul class="nav">
        <li><a href="factura.html">FACTURA</a>
		 
		   
        	
        </li>
</head>

<script>


 function validar(x){
 a=0
y= x.length
for(i=0; i<y; i++){
z= x.substring(i,i+1);
if((z=="0") || (z=="1" ) ){
a=a+1
}

}
if (a == y){

alert("si es binario")}
else{
alert("No es binario")
} 

 }
 function cadec(tabla) {
hex=tabla.valorhex.value;
hex=hex.toUpperCase()
lon=hex.length;
simbolos="0123456789ABCDEF";
dec=0;
for (i=0; i<lon; i++)
	{
	caracter=hex.substring(i,i+1);
	for (j=0; j<16; j++) {
		if (caracter==simbolos.charAt(j)) {valcar=j;}
		}
	dec=dec+valcar*Math.pow(16,lon-i-1);
	}
tabla.valorhex.value=hex;
tabla.valordec.value=dec;
}
function cahex(tabla) {
dec=eval(tabla.valordec.value);
coc=1;
res=0;
hex=" ";
simbolos="0123456789ABCDEF";
while(coc>0)
	{
	coc=Math.floor(dec/16);
	res=dec-coc*16;
	hex=simbolos.charAt(res)+hex;
	dec=coc;
	}


tabla.valorhex.value=hex;
}

function cabin(tabla){

}
function invertir()
{
var x = document.getElementById("caja").value;
var y = " ";


for(i=x.length ; i>=0; i--)
{
   y = y + x.charAt(i);
}

alert("" +y);

}
 
            function sumaDeBinarios(bUno, bDos) {
                var primeroEnDecimal = parseInt(bUno, 2);
                var segundoEnDecimal = parseInt(bDos, 2);
                var sumaDecimal = primeroEnDecimal + segundoEnDecimal;
                var sumaBinario = deciToBin(sumaDecimal);
                alert( + sumaBinario);
            }

            function deciToBin(arg)
            {
                res1 = 999;
                args = arg;
                while (args > 1)
                {
                    arg1 = parseInt(args / 2);
                    arg2 = args % 2;
                    args = arg1;
                    if (res1 == 999)
                    {
                        res1 = arg2.toString();
                    }
                    else
                    {
                        res1 = arg2.toString() + res1.toString();
                    }
                }
                if (args == 1 && res1 != 999)
                {
                    res1 = args.toString() + res1.toString();
                }
                else if (args == 0 && res1 == 999)
                {
                    res1 = 0;
                }
                else if (res1 == 999)
                {
                    res1 = 1;
                }
                var ll = res1.length;
                while (ll % 4 != 0)
                {
                    res1 = "0" + res1;
                    ll = res1.length;
                }
                return res1;
            }

            function numPrimos() {
                var dato = document.getElementById("numero1").value;
                var divisoresEncontrados = 0;
                for (i = 0; i <= dato; i++) {
                    var residuo = dato % i;
                    if (residuo == 0) {
                        divisoresEncontrados++;
                    }
                }
                if (divisoresEncontrados == 2 || dato == 1) {
                    
                    document.getElementById("resultado").innerHTML = "PRIMO";
                } else {
                  document.getElementById("numero1").value= "";
                  document.getElementById("resultado").innerHTML = "NO PRIMO";
                }
            }
        </script>
        </script>
 </script>



</script>
</head>

<body BGCOLOR="silver">
<table border="0px"><br><br><br><br>
  

       <h4> NUMEROS PRIMOS</h4>
        <label for="numero1" >INGRESE NUMERO</label>
        <input type="text" name="numero1" id="numero1" />
        <input type="button" name="ok" value="VERIFICAR" onclick="numPrimos()" id="ok"/>
        <p id="resultado" ></p><BR>
</table>



<h4>NUMEROS BINARIOS </H4></P> 
  
		<label>INGRESE PRIMER NUMERO BINARIO:</label>
        <input type="text" id="binarioUno" onChange = "validar(this.value)"/>
        <label>INGRESE SEGUNDO VALOR BINARIO </label>
        <input type="text" id="binarioDos"onChange = "validar(this.value)"/>
        <input type="button" id="Sumar" value="Sumar" onclick="sumaDeBinarios(document.getElementById('binarioUno').value, document.getElementById('binarioDos').value)"/><BR>
    

INGRESE PALABRAS A INVERTIR<input type="text" name="caja" id="caja">
<input type="button" value="Invertir Cadena" onClick="invertir()" >

</body>

</html>


