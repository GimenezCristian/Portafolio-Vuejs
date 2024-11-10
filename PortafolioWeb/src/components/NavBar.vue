<template>
  <nav>
    <div class="navbar">
      <div class="navbar-menu">
        <ul>
          <li v-for="nav in navegacion" :key="nav.id" class="nav-item" @click="scrollToSection(nav.enlace)">
            {{ nav.nombre }}
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue';

const navegacion = ref([
  { id: 1, nombre: 'Educación', enlace: '#educacion' },
  { id: 2, nombre: 'Experiencia', enlace: '#experiencia' },
  { id: 3, nombre: 'Proyectos', enlace: '#proyectos' },
  { id: 4, nombre: 'Habilidades', enlace: '#habilidades' }
]);

const scrollToSection = (enlace) => {
  const section = document.querySelector(enlace);
  if (section) {
    section.scrollIntoView({ behavior: 'smooth' });
  }
};
</script>

<style scoped>
/* Estilo general de la navbar */
.navbar {
  background-color: #1f2937; /* Gris oscuro */
  color: #ffffff;
  padding: 1rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
}

/* Lista de navegación */
.navbar-menu ul {
  display: flex;
  justify-content: flex-end;
  margin: 0;
  padding: 0;
  list-style: none;
}

.navbar-menu li {
  margin-left: 1.5rem;
}

/* Estilo de los enlaces de navegación */
.nav-item {
  position: relative;
  color: #ffffff;
  text-decoration: none;
  font-size: 1.1rem;
  font-weight: 600;
  padding: 8px 16px;
  cursor: pointer;
  display: inline-block;
  transition: color 0.3s ease;
}

/* Barra animada debajo del texto */
.nav-item::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0%;
  height: 3px;
  background-color: #3b82f6; /* Azul brillante */
  transition: width 0.3s ease;
}

/* Efecto hover */
.nav-item:hover {
  color: #3b82f6;
}

.nav-item:hover::after {
  width: 100%;
}

/* Estilos responsive */
@media (max-width: 768px) {
  .navbar {
    flex-direction: column;
    align-items: flex-start;
    padding: 1rem;
  }

  .navbar-menu ul {
    flex-direction: column;
    align-items: flex-start;
  }

  .navbar-menu li {
    margin-left: 0;
    margin-bottom: 1rem;
  }

  .nav-item {
    font-size: 1.2rem;
  }
}
</style>
