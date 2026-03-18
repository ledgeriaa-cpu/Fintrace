index.html<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>FinTrace Analytics</title>

<style>
body{
  font-family: Arial;
  background:#0f172a;
  color:white;
  text-align:center;
  padding:40px;
}

textarea{
  width:80%;
  height:120px;
  margin:20px;
}

button{
  padding:12px 20px;
  background:#22c55e;
  border:none;
  color:white;
  cursor:pointer;
}

#loader{
  display:none;
  margin-top:20px;
}

#resultados{
  display:none;
  margin-top:30px;
}

table{
  width:80%;
  margin:auto;
  border-collapse: collapse;
}

td, th{
  border:1px solid #444;
  padding:10px;
}
</style>
</head>

<body>

<h1>FinTrace Analytics</h1>
<p>Detección inteligente de patrones financieros</p>

<textarea id="input" placeholder="Pega aquí tu estado de cuenta..."></textarea>
<br>
<button onclick="analizar()">Analizar</button>

<div id="loader">
  <p>Procesando datos...</p>
  <p>Detectando patrones...</p>
  <p>Aplicando inferencia...</p>
</div>

<div id="resultados">
  <h2>Resultados</h2>

  <table>
    <tr><th>Fecha</th><th>Descripción</th><th>Monto</th></tr>
    <tr><td>01/03</td><td>OXXO</td><td>$120</td></tr>
    <tr><td>02/03</td><td>Spotify</td><td>$129</td></tr>
  </table>

  <div id="ocultos" style="display:none;">
    <h3>Actividad no visible detectada</h3>

    <table>
      <tr><th>Descripción</th><th>Monto</th><th>Estado</th></tr>
      <tr><td>MercadoPago*Arellanos</td><td>$180</td><td>Inferido</td></tr>
      <tr><td>MercadoPago*Cass</td><td>$95</td><td>Inferido</td></tr>
    </table>
  </div>

</div>

<script>
function analizar(){
  let input = document.getElementById("input").value;

  document.getElementById("loader").style.display="block";

  setTimeout(()=>{
    document.getElementById("loader").style.display="none";
    document.getElementById("resultados").style.display="block";

    if(input.includes("#PRO")){
      document.getElementById("ocultos").style.display="block";
    }

  }, 2000);
}
</script>

</body>
</html>
