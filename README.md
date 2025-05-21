Este documento explica passo a passo como criar uma barra de navegação moderna usando HTML, CSS e JavaScript.

1. Estrutura HTML
Criação da estrutura base da navbar com logo, botão hambúrguer e links.
index.html:

<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Navbar Responsiva</title>
  <link rel="stylesheet" href="style.css">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
</head>
<body>

  <!-- ===== NAVBAR ===== -->
  <header>
    <nav class="nav" id="navbar">

      <!-- Logo principal (desktop) -->
      <div class="logo">
        <a href="index.html" id="logo">
          <h1>coding sumit</h1>
        </a>
      </div>

      <!-- Botão hambúrguer (mobile) -->
      <button class="nav-toggle" aria-label="Abrir menu">
        <span class="hamburger"></span>
      </button>

      <!-- Logo pequeno (mobile) -->
      <div class="smalllogo">
        <a href="#home-section" class="logolink">
          <h2><i class="fas fa-code"></i> coding sumit</h2>
        </a>
      </div>

      <!-- Lista de navegação -->
      <ul class="nav__list" id="navlinkitems">
        <li class="nav__item"><a href="#home-section" class="nav__link" id="home">Home</a></li>
        <li class="nav__item"><a href="#about-section" class="nav__link" id="about">Sobre</a></li>
        <li class="nav__item"><a href="#skills-section" class="nav__link" id="service">Habilidades</a></li>
        <li class="nav__item"><a href="#projects-section" class="nav__link" id="work">Projetos</a></li>
        <li class="nav__item"><a href="#contacts-section" class="nav__link" id="contact">Contato</a></li>
      </ul>

    </nav>
  </header>

  <!-- ===== SEÇÕES DA PÁGINA ===== -->
  <section class="section one" id="home-section"></section>
  <section class="section two" id="about-section"></section>
  <section class="section three" id="skills-section"></section>
  <section class="section four" id="projects-section"></section>
  <section class="section five" id="contacts-section"></section>

  <!-- ===== SCRIPTS ===== -->
  <script src="index.js"></script>

</body>
</html>

2. Estilização da Página
Reset de estilos e configuração do layout da navbar.
style.css (parte 1):

html {
  scroll-behavior: smooth;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: "Source Sans Pro", sans-serif;
  line-height: 1.6;
  overflow-x: hidden;
  background: #fff;
}
a {
  text-decoration: none;
  color: #111;
}
.nav {
  height: 5rem;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 4vw;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 10;
  background: #fff;
}
.nav__list {
  list-style: none;
  display: flex;
  justify-content: flex-end;
  gap: 20px;
}
.nav__link {
  position: relative;
  font-family: "Raleway", sans-serif;
  font-weight: 700;
  padding: 16px 12px;
  letter-spacing: 1px;
  color: #111;
  transition: 0.3s;
}
.nav__link::before {
  content: "";
  position: absolute;
  bottom: 3px;
  left: 0;
  height: 3px;
  width: 100%;
  background-color: #000;
  transform-origin: right top;
  transform: scale(0, 1);
  transition: transform 0.2s ease-out;
}
.nav__link:hover::before {
  transform-origin: left top;
  transform: scale(1, 1);
}
.logo {
  font-family: "Raleway", sans-serif;
  font-weight: 800;
  text-transform: uppercase;
  color: #160808;
  display: flex;
  align-items: center;
  padding: 0 1rem;
}
.nav-toggle {
  display: none;
  padding: 2.3em;
  background: transparent;
  border: 0;
  cursor: pointer;
  position: absolute;
  right: 0.5rem;
  top: 1.1rem;
  z-index: 1000;
}
.hamburger {
  display: block;
  position: relative;
  background-color: #11
3. Estilo Avançado da Navbar
Estilos para hover, sublinhado animado e comportamento responsivo.
style.css (parte 2):

1;
  width: 2em;
  height: 3px;
  border-radius: 1em;
  transition: transform 250ms ease-in-out;
}
.hamburger::before,
.hamburger::after {
  content: "";
  position: absolute;
  left: 0;
  right: 0;
  background-color: #111;
  width: 2em;
  height: 3px;
  border-radius: 1em;
  transition: transform 250ms ease-in-out;
}
.hamburger::before { top: 6px; }
.hamburger::after { bottom: 6px; }
.nav-open .hamburger {
  transform: rotate(0.625turn);
}
.nav-open .hamburger::before {
  transform: rotate(90deg) translateX(-6px);
}
.nav-open .hamburger::after {
  opacity: 0;
}
.smalllogo {
  display: none;
  padding: 4.7vh 8vw;
  text-align: center;
  align-items: center;
  color: #111;
  text-transform: uppercase;
  font-family: "Raleway", sans-serif;
  font-weight: 800;
}
section {
  width: 100%;
  display: flex;
  margin: auto;
  align-items: center;
  min-height: 110vh;
}
.one { background-color: #fff; }
.two { background-color: rgb(190, 183, 170); }
.three { background-color: rgb(63, 118, 238); }
.four { background-color: rgb(221, 22, 88); }
.five { background-color: rgb(163, 114, 8); }

@media (max-width: 800px) {
  .logo {
    display: none;
  }
  .nav__link::before {
    background-color: #fff;
  }
  .smalllogo {
    display: flex;
  }
  .nav-toggle {
    display: block;
  }
  .nav {
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    transform: translateX(100%);
    transition: transform 0.4s ease;
    height: 100vh;
    background-color: #111;
    padding-top: 5rem;
  }
  .nav-open .nav {
    transform: translateX(0);
    width: 100vw;
  }
  .nav__list {
    flex-direction: column;
    justify-content: space-evenly;
    text-align: center;
    padding: 135px 0;
    width: 100%;
  }
  .nav__link {
    color: #fff;
    margin: 0;
  }
  .nav-open .hamburger,
  .nav-open .hamburger::before {
    background-color: #fff;
  }
}

4. Lógica do Menu com JavaScript
Script para abrir e fechar o menu ao clicar no botão ou nos links.
index.js:

const navToggle = document.querySelector(".nav-toggle");
const navLinks = document.querySelectorAll(".nav__link");

navToggle.addEventListener("click", () => {
  document.body.classList.toggle("nav-open");
});

navLinks.forEach((link) => {
  link.addEventListener("click", () => {
    document.body.classList.remove("nav-open");
  });
});

5. Script Adicional
Arquivo reservado para funcionalidades futuras.
script.js:

// script.js
// Você pode adicionar funcionalidades adicionais aqui, como animações ou scroll suave personalizado.

6. Explicação Geral
# Projeto: Navbar Responsiva, Fixa e Animada

Este projeto ensina como criar uma barra de navegação moderna usando **HTML, CSS e JavaScript**. A navbar é **fixa no topo**, possui um **efeito de sublinhado animado nos links** e é **totalmente responsiva**, adaptando-se para celulares com um menu tipo **hambúrguer**.

---

## ✅ Funcionalidades

- ✅ Navegação fixa no topo da tela (sticky)
- ✅ Scroll suave para seções da página
- ✅ Efeito hover animado nos links
- ✅ Responsividade com botão hambúrguer no mobile
- ✅ Menu lateral deslizante
- ✅ Fechamento automático do menu ao clicar

---

## 📁 Estrutura de Arquivos

```
/navbar_responsiva_completa/
│
├── index.html       # Estrutura HTML da página
├── style.css        # Estilização completa da navbar e das seções
├── index.js         # Controle da abertura/fechamento do menu mobile
└── script.js        # Arquivo adicional para futuras funcionalidades
```

---

## 🧱 Etapas do Projeto

### 1. Estrutura HTML (`index.html`)

- Criação de um `<nav>` com:
  - Um logotipo principal (`.logo`)
  - Um logotipo pequeno (`.smalllogo`) para o mobile
  - Um botão hambúrguer (`.nav-toggle`)
  - Uma lista com links de navegação (`<ul class="nav__list">`)

### 2. Estilo Base (`style.css`)

- Reset de margens e paddings
- Fonte padrão e rolagem suave
- Remoção do sublinhado padrão de links

### 3. Estilização da Navbar

- Alinhamento horizontal com `flexbox`
- Espaçamento e cores ajustados
- Logo com texto em caixa alta

### 4. Efeito de Hover

- Implementado com `::before` nos links
- Linha animada aparece ao passar o mouse

### 5. Criação das Seções

- 5 seções (`#home-section`, `#about-section`, etc.)
- Cada uma com altura mínima de `110vh` para testar rolagem

### 6. Navbar Fixa

- Com `position: fixed` para manter no topo
- Mudança de cor ao rolar (opcional)

### 7. Botão Hambúrguer

- Criado com `<button>` + `<span class="hamburger">`
- Linhas com `::before` e `::after`
- Animação para virar “X” ao abrir menu

### 8. JavaScript (`index.js`)

- Toggle da classe `nav-open` ao clicar no botão
- Fechamento automático ao clicar em um link

### 9. Media Query

- A partir de `max-width: 800px`:
  - Logo grande some
  - Menu vira painel lateral escuro
  - Links ficam empilhados verticalmente

### 10. Arquivo `script.js`

- Arquivo separado para adicionar futuras interações, animações ou integrações JS.

---

## 🚀 Como Usar

1. Abra o `index.html` em seu navegador
2. Reduza a largura da janela para testar a versão mobile
3. Clique no botão hambúrguer para abrir o menu lateral
4. Clique nos links para rolar até as seções

---

## 📌 Requisitos

Nenhuma dependência externa obrigatória.

- Apenas **Font Awesome** é utilizado opcionalmente para o ícone do logotipo mobile:
```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
```

---

## 📚 Créditos

Desenvolvido por Claudio Torres para fins educativos.

---


