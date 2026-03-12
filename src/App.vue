<script setup>
import { onMounted } from "vue";
import { useDark, useToggle } from "@vueuse/core";

const isDark = useDark();
const toggleDark = useToggle(isDark);

onMounted(() => {
  const anio = document.getElementById("anio");
  if (anio) anio.textContent = new Date().getFullYear();

  const updated = document.getElementById("last-updated");
  if (updated) updated.textContent = new Date().toLocaleDateString();
});
</script>

<template>

<header class="site-header">
<a href="#inicio" class="logo-link">
<img src="./assets/logo.svg" alt="Logo JS Práctica" class="logo"/>
</a>

<div class="brand">
<h1>Práctica de JavaScript</h1>
<p class="subtitle">Programación Web · Guía con ejemplos</p>
</div>

<button class="dark-btn" @click="toggleDark()">
{{ isDark ? "☀️ Claro" : "🌙 Oscuro" }}
</button>
</header>

<nav class="topnav">
<ul>
<li><a href="#js">¿Qué es JS?</a></li>
<li><a href="#tipos">Tipos de datos</a></li>
<li><a href="#operadores">Operadores</a></li>
<li><a href="#funciones">Funciones</a></li>
<li><a href="#conversion">Conversión</a></li>
<li><a href="#variables">Variables</a></li>
<li><a href="#entrada">Entrada/Salida</a></li>
<li><a href="#control">Estructuras de control</a></li>
<li><a href="#objetos">Objetos</a></li>
<li><a href="#referencias">Referencias</a></li>
</ul>
</nav>

<main class="layout">

<section id="inicio" class="card">
<h2>Bienvenid@ a la Práctica de JavaScript</h2>
<p>
Este sitio fue creado para explicar los conceptos básicos de JavaScript
de forma sencilla para la materia de programación web.
</p>
</section>

<section id="js" class="card">
<h2>¿Qué es JavaScript?</h2>
<p>
JavaScript es un lenguaje de programación utilizado para crear páginas web
interactivas. Permite agregar botones dinámicos, animaciones,
validaciones de formularios y muchas funciones en los sitios web.
</p>
</section>

<section id="tipos" class="card">
<h2>Tipos de datos</h2>
<p>
Los tipos de datos más comunes en JavaScript son:
string (texto), number (números), boolean (verdadero o falso),
null, undefined y object.
</p>
</section>

<section id="operadores" class="card">
<h2>Operadores</h2>
<p>
Los operadores permiten realizar operaciones matemáticas o comparaciones
como suma (+), resta (-), multiplicación (*), división (/)
y comparaciones como == o ===.
</p>
</section>

<section id="funciones" class="card">
<h2>Funciones</h2>
<p>
Una función es un bloque de código que realiza una tarea específica
y puede reutilizarse varias veces dentro del programa.
</p>
</section>

<section id="conversion" class="card">
<h2>Conversión de datos</h2>
<p>
JavaScript permite convertir tipos de datos utilizando funciones como
Number(), String() o Boolean().
</p>
</section>

<section id="variables" class="card">
<h2>Variables</h2>
<p>
Las variables almacenan información. En JavaScript se pueden declarar
con let, const o var.
</p>
</section>

<section id="entrada" class="card">
<h2>Entrada y salida</h2>
<p>
JavaScript permite mostrar información con alert(), console.log()
o interactuar con el usuario mediante formularios.
</p>
</section>

<section id="control" class="card">
<h2>Estructuras de control</h2>
<p>
Las estructuras de control permiten tomar decisiones en el programa,
como if, else, switch o ciclos como for y while.
</p>
</section>

<section id="objetos" class="card">
<h2>Objetos</h2>
<p>
Un objeto es una colección de propiedades y valores que permiten
organizar información dentro del programa.
</p>
</section>

<section id="referencias" class="card">
<h2>Referencias</h2>
<p>
Puedes aprender más sobre JavaScript en la documentación oficial
de MDN y en la especificación de ECMAScript.
</p>
</section>

</main>

<footer class="site-footer">

<p><strong>Autores:</strong> ane y bry</p>

<p><strong>Contacto:</strong> anebry04@gmail.com</p>

<p>
<strong>Copyright:</strong> ©
<span id="anio"></span> Anebry.
</p>

<p>
<a href="https://developer.mozilla.org/es/docs/Web/JavaScript" target="_blank">
Documentación MDN
</a>
</p>

<p>Última actualización: <span id="last-updated"></span></p>

</footer>

</template>

<style>

@import "./styles.css";

.dark-btn{
margin-left:20px;
padding:8px 14px;
border-radius:8px;
border:none;
cursor:pointer;
background:#42b883;
color:white;
font-weight:bold;
}

.dark-btn:hover{
opacity:0.8;
}

.card{
padding:30px;
margin:20px;
border-radius:10px;
background:#1e1e1e;
color:white;
}

</style>