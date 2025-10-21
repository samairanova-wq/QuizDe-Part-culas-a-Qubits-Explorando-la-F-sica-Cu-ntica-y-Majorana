<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Curso de Física Cuántica - Evaluaciones</title>
<style>
    body { font-family: Arial, sans-serif; background: #f4f4f9; color: #333; margin: 20px; }
    h1 { text-align: center; }
    .menu { margin-bottom: 20px; text-align: center; }
    select { padding: 8px 12px; font-size: 16px; }
    .quiz { display: none; border: 1px solid #ccc; padding: 15px; margin-top: 20px; border-radius: 8px; background: #fff; }
    button { padding: 8px 15px; margin-top: 10px; border: none; border-radius: 5px; background: #4CAF50; color: white; cursor: pointer; }
    button:hover { background: #45a049; }
    .score { font-weight: bold; margin-top: 10px; }
</style>
</head>
<body>

<h1>Curso de Física Cuántica - Evaluaciones</h1>

<div class="menu">
    <label for="moduloSelect">Seleccione un módulo:</label>
    <select id="moduloSelect" onchange="mostrarModulo()">
        <option value="">--Seleccionar módulo--</option>
        <option value="mod1">Módulo 1: Introducción a la Física Cuántica</option>
        <option value="mod2">Módulo 2: Principios fundamentales</option>
        <option value="mod3">Módulo 3: Entrelazamiento cuántico</option>
        <option value="mod4">Módulo 4: Majorana y Computación Cuántica</option>
        <option value="mod5">Módulo 5: Aplicaciones modernas y proyecto final</option>
    </select>
</div>

<script>
let intentos = { mod1: 0, mod2: 0, mod3: 0, mod4: 0, mod5: 0 };

function mostrarModulo() {
    const select = document.getElementById("moduloSelect").value;
    document.querySelectorAll('.quiz').forEach(div => div.style.display = 'none');
    if(select) document.getElementById(select).style.display = 'block';
}

function calcularScore(moduloId, totalPreguntas) {
    if(intentos[moduloId] >= 2) {
        alert("Has alcanzado el máximo de 2 intentos para este módulo.");
        return;
    }
    intentos[moduloId]++;
    let quizDiv = document.getElementById(moduloId);
    let radios = quizDiv.querySelectorAll('input[type="radio"]');
    let score = 0;
    radios.forEach(radio => {
        if(radio.checked) score += parseInt(radio.value);
    });
    document.getElementById('score-' + moduloId).innerText = "Intento " + intentos[moduloId] + " - Puntaje: " + score + " / " + totalPreguntas;
}
</script>

<!-- Módulo 1 -->
<div class="quiz" id="mod1">
    <h2>Módulo 1: Introducción a la Física Cuántica</h2>
    <form>
        <p>1. ¿Qué fenómeno no podía explicar la física clásica?</p>
        <input type="radio" name="q1" value="0"> A. Movimiento de planetas<br>
        <input type="radio" name="q1" value="1"> B. Efecto fotoeléctrico<br>
        <input type="radio" name="q1" value="0"> C. Gravedad<br>
        <input type="radio" name="q1" value="0"> D. Caída libre<br>

        <p>2. ¿Quién propuso los cuantos de energía?</p>
        <input type="radio" name="q2" value="1"> A. Max Planck<br>
        <input type="radio" name="q2" value="0"> B. Einstein<br>
        <input type="radio" name="q2" value="0"> C. Bohr<br>
        <input type="radio" name="q2" value="0"> D. Majorana<br>

        <p>3. La física cuántica se ocupa principalmente de…</p>
        <input type="radio" name="q3" value="1"> A. Escalas microscópicas<br>
        <input type="radio" name="q3" value="0"> B. Escalas planetarias<br>
        <input type="radio" name="q3" value="0"> C. Fenómenos cotidianos<br>
        <input type="radio" name="q3" value="0"> D. Movimientos de galaxias<br>

        <p>4. ¿Qué partícula es un ejemplo fundamental en física cuántica?</p>
        <input type="radio" name="q4" value="1"> A. Electrón<br>
        <input type="radio" name="q4" value="0"> B. Planeta<br>
        <input type="radio" name="q4" value="0"> C. Sol<br>
        <input type="radio" name="q4" value="0"> D. Agua<br>

        <p>5. ¿Qué característica tiene la energía en la física cuántica?</p>
        <input type="radio" name="q5" value="1"> A. Cuantizada<br>
        <input type="radio" name="q5" value="0"> B. Continua<br>
        <input type="radio" name="q5" value="0"> C. No existe<br>
        <input type="radio" name="q5" value="0"> D. Solo se mide en kilogramos<br>

        <button type="button" onclick="calcularScore('mod1', 5)">Ver puntaje</button>
        <div class="score" id="score-mod1"></div>
    </form>
</div>

<!-- Módulo 2 -->
<div class="quiz" id="mod2">
    <h2>Módulo 2: Principios fundamentales</h2>
    <form>
        <p>1. ¿Qué describe la dualidad onda-partícula?</p>
        <input type="radio" name="q1-2" value="1"> A. Comportamiento como onda y partícula<br>
        <input type="radio" name="q1-2" value="0"> B. Solo partículas<br>
        <input type="radio" name="q1-2" value="0"> C. Solo ondas<br>
        <input type="radio" name="q1-2" value="0"> D. Ninguna de las anteriores<br>

        <p>2. La función de onda representa…</p>
        <input type="radio" name="q2-2" value="1"> A. Probabilidades de posición y momento<br>
        <input type="radio" name="q2-2" value="0"> B. Trayectoria exacta<br>
        <input type="radio" name="q2-2" value="0"> C. Energía total<br>
        <input type="radio" name="q2-2" value="0"> D. Solo velocidad<br>

        <p>3. El principio de incertidumbre establece que…</p>
        <input type="radio" name="q3-2" value="1"> A. No se puede medir posición y momento exactos simultáneamente<br>
        <input type="radio" name="q3-2" value="0"> B. Todo se puede medir con precisión infinita<br>
        <input type="radio" name="q3-2" value="0"> C. Solo se puede medir energía<br>
        <input type="radio" name="q3-2" value="0"> D. Solo se puede medir tiempo<br>

        <p>4. ¿Qué es la superposición cuántica?</p>
        <input type="radio" name="q4-2" value="1"> A. Estado donde una partícula puede estar en varias posiciones a la vez<br>
        <input type="radio" name="q4-2" value="0"> B. Solo ocurre en planetas<br>
        <input type="radio" name="q4-2" value="0"> C. Movimiento de electrones en órbita fija<br>
        <input type="radio" name="q4-2" value="0"> D. Energía continua<br>

        <p>5. ¿Qué unidad se asocia a la mínima acción cuántica?</p>
        <input type="radio" name="q5-2" value="1"> A. Constante de Planck<br>
        <input type="radio" name="q5-2" value="0"> B. Newton<br>
        <input type="radio" name="q5-2" value="0"> C. Joule<br>
        <input type="radio" name="q5-2" value="0"> D. Tesla<br>

        <button type="button" onclick="calcularScore('mod2', 5)">Ver puntaje</button>
        <div class="score" id="score-mod2"></div>
    </form>
</div>

<!-- Módulo 3 -->
<div class="quiz" id="mod3">
    <h2>Módulo 3: Entrelazamiento cuántico</h2>
    <form>
        <p>1. El entrelazamiento cuántico significa…</p>
        <input type="radio" name="q1-3" value="1"> A. Dos partículas correlacionadas instantáneamente<br>
        <input type="radio" name="q1-3" value="0"> B. Interacción clásica a distancia<br>
        <input type="radio" name="q1-3" value="0"> C. Fenómeno de partículas grandes<br>
        <input type="radio" name="q1-3" value="0"> D. Movimiento orbital de electrones<br>

        <p>2. Experimentos que demostraron esto incluyen…</p>
        <input type="radio" name="q2-3" value="1"> A. EPR y desigualdades de Bell<br>
        <input type="radio" name="q2-3" value="0"> B. Ley de Newton<br>
        <input type="radio" name="q2-3" value="0"> C. Experimento de Galileo<br>
        <input type="radio" name="q2-3" value="0"> D. Experimento de Young<br>

        <p>3. Aplicaciones del entrelazamiento incluyen…</p>
        <input type="radio" name="q3-3" value="1"> A. Criptografía y teleportación cuántica<br>
        <input type="radio" name="q3-3" value="0"> B. Motores de combustión<br>
        <input type="radio" name="q3-3" value="0"> C. Gravedad cuántica<br>
        <input type="radio" name="q3-3" value="0"> D. Movimiento planetario<br>

        <p>4. El entrelazamiento es una consecuencia de…</p>
        <input type="radio" name="q4-3" value="1"> A. Principio de superposición<br>
        <input type="radio" name="q4-3" value="0"> B. Ley de Ohm<br>
        <input type="radio" name="q4-3" value="0"> C. Mecánica clásica<br>
        <input type="radio" name="q4-3" value="0"> D. Ley de gravitación<br>

        <p>5. ¿Qué caracteriza a las partículas entrelazadas? </p>
        <input type="radio" name="q5-3" value="1"> A. Estado compartido aunque estén separadas<br>
        <input type="radio" name="q5-3" value="0"> B. No tienen relación<br>
        <input type="radio" name="q5-3" value="0"> C. Solo afectan a su entorno inmediato<br>
        <input type="radio" name="q5-3" value="0"> D. Se mueven juntas físicamente<br>

        <button type="button" onclick="calcularScore('mod3', 5)">Ver puntaje</button>
        <div class="score" id="score-mod3"></div>
    </form>
</div>

<!-- Módulo 4 -->
<div class="quiz" id="mod4">
    <h2>Módulo 4: Majorana y Computación Cuántica</h2>
    <form>
        <p>1. Los fermiones de Majorana son…</p>
        <input type="radio" name="q1-4" value="1"> A. Partículas que son su propia antipartícula<br>
        <input type="radio" name="q1-4" value="0"> B. Fotones<br>
        <input type="radio" name="q1-4" value="0"> C. Electrones neutrinos<br>
        <input type="radio" name="q1-4" value="0"> D. Partículas de materia oscura<br>

        <p>2. ¿Qué buscan los científicos al usar fermiones de Majorana?</p>
        <input type="radio" name="q2-4" value="1"> A. Crear cúbits topológicos más estables<br>
        <input type="radio" name="q2-4" value="0"> B. Generar electricidad<br>
        <input type="radio" name="q2-4" value="0"> C. Mejorar paneles solares<br>
        <input type="radio" name="q2-4" value="0"> D. Detectar agujeros negros<br>

        <p>3. Los cúbits basados en Majorana son resistentes a…</p>
        <input type="radio" name="q3-4" value="1"> A. Errores y decoherencia<br>
        <input type="radio" name="q3-4" value="0"> B. Gravedad<br>
        <input type="radio" name="q3-4" value="0"> C. Luz<br>
        <input type="radio" name="q3-4" value="0"> D. Magnetismo<br>

        <p>4. ¿Cuál es la aplicación principal de Majorana?</p>
        <input type="radio" name="q4-4" value="1"> A. Computación cuántica<br>
        <input type="radio" name="q4-4" value="0"> B. Telecomunicaciones<br>
        <input type="radio" name="q4-4" value="0"> C. Aeronáutica<br>
        <input type="radio" name="q4-4" value="0"> D. Medicina<br>

        <p>5. ¿Quién propuso los fermiones de Majorana?</p>
        <input type="radio" name="q5-4" value="1"> A. Ettore Majorana<br>
        <input type="radio" name="q5-4" value="0"> B. Albert Einstein<br>
        <input type="radio" name="q5-4" value="0"> C. Niels Bohr<br>
        <input type="radio" name="q5-4" value="0"> D. Max Planck<br>

        <button type="button" onclick="calcularScore('mod4', 5)">Ver puntaje</button>
        <div class="score" id="score-mod4"></div>
    </form>
</div>

<!-- Módulo 5 -->
<div class="quiz" id="mod5">
    <h2>Módulo 5: Aplicaciones modernas y proyecto final</h2>
    <form>
        <p>1. Una aplicación de la computación cuántica es…</p>
        <input type="radio" name="q1-5" value="1"> A. Criptografía avanzada<br>
        <input type="radio" name="q1-5" value="0"> B. Motores de combustión<br>
        <input type="radio" name="q1-5" value="0"> C. Construcción de casas<br>
        <input type="radio" name="q1-5" value="0"> D. Agricultura<br>

        <p>2. Los cúbits permiten…</p>
        <input type="radio" name="q2-5" value="1"> A. Procesar muchas combinaciones simultáneamente<br>
        <input type="radio" name="q2-5" value="0"> B. Solo sumar números<br>
        <input type="radio" name="q2-5" value="0"> C. Detectar color<br>
        <input type="radio" name="q2-5" value="0"> D. Medir temperatura<br>

        <p>3. La simulación cuántica se usa para…</p>
        <input type="radio" name="q3-5" value="1"> A. Modelar moléculas y reacciones químicas<br>
        <input type="radio" name="q3-5" value="0"> B. Construir puentes<br>
        <input type="radio" name="q3-5" value="0"> C. Pintar cuadros<br>
        <input type="radio" name="q3-5" value="0"> D. Escribir textos<br>

        <p>4. El proyecto final de este curso podría incluir…</p>
        <input type="radio" name="q4-5" value="1"> A. Desarrollo de un mini-qubit o simulación<br>
        <input type="radio" name="q4-5" value="0"> B. Cocina<br>
        <input type="radio" name="q4-5" value="0"> C. Deportes<br>
        <input type="radio" name="q4-5" value="0"> D. Jardinería<br>

        <p>5. La ventaja de la computación cuántica sobre la clásica es…</p>
        <input type="radio" name="q5-5" value="1"> A. Velocidad y capacidad para resolver problemas complejos<br>
        <input type="radio" name="q5-5" value="0"> B. Menor velocidad<br>
        <input type="radio" name="q5-5" value="0"> C. Solo sirve para cálculos simples<br>
        <input type="radio" name="q5-5" value="0"> D. No tiene ventaja<br>

        <button type="button" onclick="calcularScore('mod5', 5)">Ver puntaje</button>
        <div class="score" id="score-mod5"></div>
    </form>
</div>

</body>
</html>
