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
    <a href="#" class="logo-link" aria-label="Inicio">
      <img src="./assets/logo.svg" alt="Logo JS Práctica" class="logo" />
    </a>

    <div class="brand">
      <h1>Práctica de JavaScript</h1>
      <p class="subtitle">Programación Web · Guía con ejemplos ejecutables</p>
    </div>

    <form class="search" role="search" @submit.prevent>
      <label for="q" class="sr-only">Buscar</label>
      <input
        id="q"
        type="search"
        placeholder="Buscar en esta página..."
        autocomplete="off"
      />
    </form>

    <!-- BOTÓN MODO OSCURO -->
    <button class="dark-btn" @click="toggleDark()">
      {{ isDark ? "☀️ Claro" : "🌙 Oscuro" }}
    </button>
  </header>

  <nav class="topnav" aria-label="Navegación principal">
    <ul>
      <li><a href="#">¿Qué es JS?</a></li>
      <li><a href="#">Tipos de datos</a></li>
      <li><a href="#">Operadores</a></li>
      <li><a href="#">Funciones</a></li>
      <li><a href="#">Conversión</a></li>
      <li><a href="#">Variables</a></li>
      <li><a href="#">Entrada/Salida</a></li>
      <li><a href="#">Estructuras de control</a></li>
      <li><a href="#">Objetos</a></li>
      <li><a href="#">Referencias</a></li>
    </ul>
  </nav>

  <main class="layout">
    <section class="content" style="grid-column: 1/-1">
      <article class="card" style="text-align: center; padding: 32px 24px">
        <h2 style="margin-top: 0; font-size: clamp(24px, 3vw, 34px)">
          Bienvenid@ a la
          <span style="color: var(--accent)">Práctica de JavaScript</span>
        </h2>

        <p style="max-width: 740px; margin: 10px auto 0; color: var(--muted)">
          Sitio oficial de la práctica de <strong>Programación Web</strong>.
          Aquí encontrarás definiciones claras, ejemplos ejecutables en modal y
          una navegación por pestañas a cada tema.
        </p>

        <p style="margin-top: 18px">
          <a class="button" href="#">¿Qué es JS?</a>
          <a class="button" href="#">Tipos de datos</a>
          <a class="button" href="#">Operadores</a>
          <a class="button" href="#">Funciones</a>
          <a class="button" href="#">Referencias</a>
        </p>
      </article>
    </section>
  </main>

  <div id="modal" class="modal">
    <div class="modal-content">
      <button class="modal-close">×</button>
      <h3>Resultado</h3>
      <div id="modal-body" class="modal-body"></div>
    </div>
  </div>

  <footer class="site-footer">
    <p><strong>Autores:</strong> ane y bry</p>

    <p><strong>Contacto:</strong> anebry04@gmail.com</p>

    <p>
      <strong>Copyright:</strong> ©
      <span id="anio"></span> Anebry. Todos los derechos reservados.
    </p>

    <p>
      <strong>Políticas y legales:</strong>
      <a href="#">Aviso de privacidad</a> ·
      <a href="#">Licencias/Créditos</a>
    </p>

    <p>
      <strong>Enlaces relacionados:</strong>
      <a
        href="https://developer.mozilla.org/es/docs/Web/JavaScript"
        target="_blank"
        rel="noopener"
        >MDN JavaScript</a
      >
      ·
      <a href="https://tc39.es/ecma262/" target="_blank" rel="noopener"
        >Especificación ECMAScript</a
      >
    </p>

    <p>
      <strong>Enlaces internos:</strong>
      <a href="#">Inicio</a> ·
      <a href="#">Referencias</a>
    </p>

    <p>Última actualización: <span id="last-updated"></span></p>
  </footer>
</template>

<style>
@import "./styles.css";

/* botón modo oscuro */

.dark-btn {
  margin-left: 20px;
  padding: 8px 14px;
  border-radius: 8px;
  border: none;
  cursor: pointer;
  background: #42b883;
  color: white;
  font-weight: bold;
}

.dark-btn:hover {
  opacity: 0.8;
}
</style>