<style scoped>
h1 {
  font-size: 3rem;
  color: #fff;
  font-weight: bold;
  margin-bottom: 10px;
}

h2 {
  font-size: 1.5rem;
  color: #a1a1a1;
  font-weight: 500;
  margin-bottom: 10px;
}

p {
  font-size: 1.1rem;
  font-weight: 400;
  color: #dcdcdc;
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.card {
  background-color: #0d1424;
  border-radius: 12px;
  padding: 20px;
  margin: 20px;
  text-align: center;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4);
}

.container-lista {
  display: flex;
  justify-content: center;
  gap: 15px;
  margin: 0;
  padding: 0;
}

.icon-redsocial {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 50px;
  height: 50px;
  background-color: #f4f4f4;
  border-radius: 50%;
  padding: 5px;
  transition: background-color 0.3s, transform 0.3s ease;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
}

.icon-redsocial:hover {
  background-color: #0044cc;
  transform: scale(1.1);
}

.icon-redsocial img {
  width: 25px;
  height: 25px;
  transition: filter 0.3s ease;
}

.icon-redsocial:hover img {
  filter: brightness(0) saturate(100%) invert(100%);
}

h3 {
  font-size: 1.2rem;
  font-weight: 600;
  color: #e6e6e6;
  margin-top: 20px;
}

h4 {
  font-size: 1rem;
  color: #888;
  font-weight: 500;
}
</style>

<script setup>
import linkedin from '/src/assets/linkedin_icon.svg';
import instagram from '/src/assets/instagram_icon.svg';
import github from '/src/assets/github_icon.svg';
import curriculum from '/src/assets/cv_resume_icon.svg';

const title = 'Gimenez Cristian';
const descripcion = 'Estudiante de la Técnicatura Universitaria en Programación - UTN';
const residencia = 'Parana, Entre Ríos, Argentina';
const presentacion = '¡Bienvenido a mi portafolio de proyectos! Soy estudiante de desarrollo web y aplicaciones digitales. Me apasiona el aprendizaje continuo y explorar los diversos lenguajes de programación para crear soluciones innovadoras. Te invito a descubrir mi trabajo y los proyectos en los que he estado trabajando.';
const redesSociales = [
  { id: 1, name: 'linkedin', src: linkedin , url: 'https://www.linkedin.com/in/gimenezcristian/' },
  { id: 2, name: 'Instagram', src: instagram , url: 'https://www.instagram.com/gimenezcristian/' },
  { id: 3, name: 'github', src: github, url: 'https://github.com/GimenezCristian' },
  { id: 4, name: 'curriculum', src: curriculum, url: '' },
];
const telefono = '343-4523081';
</script>

<template>
  <section class="datos-personales">
    <div class="card">
      <h1>{{ title }}</h1>
      <h2>{{ descripcion }}</h2>
      <p>{{ presentacion }}</p>
      <ul class="container-lista">
        <li v-for="red in redesSociales" :key="red.id">
          <a :href="red.url" target="_blank" rel="noopener noreferrer">
            <img class="icon-redsocial" :src="red.src" :alt="red.name" />
          </a>
        </li>
      </ul>
      <h3>☎ Teléfono personal: {{ telefono }}</h3>
      <h4>{{ residencia }}</h4>
    </div>
  </section>
</template>
