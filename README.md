# 🛍️ Projeto Web — Roupas & Interatividade com JS

Projeto educacional com dois módulos: um **site de moda** comparando HTML semântico vs não-semântico, e uma **página interativa** demonstrando manipulação do DOM e eventos JavaScript.

---

## 📁 Estrutura de Arquivos

```
projeto/
├── com-semantico.html      # Site de roupas com HTML semântico
├── sem-semantico.html      # Site de roupas sem HTML semântico
├── pagina-interativa.html  # Página de eventos e DOM com JS
└── README.md               # Este arquivo
```

---

## 🗂️ Módulo 1 — Site de Roupas (HTML Semântico)

### Sobre

Dois arquivos com **visual idêntico** mas estrutura de código completamente diferente. O objetivo é demonstrar na prática o impacto do uso correto das tags HTML.

### Comparativo

| Elemento | `com-semantico.html` | `sem-semantico.html` |
|---|---|---|
| Cabeçalho | `<header>` | `<div class="topo">` |
| Navegação | `<nav>` + `<ul>/<li>` | `<div>` com links soltos |
| Conteúdo principal | `<main>` | `<div class="conteudo">` |
| Seções | `<section aria-labelledby="...">` | `<div>` genérico |
| Título da página | `<h1>` | `<div class="titulo-grande">` |
| Subtítulos | `<h2>`, `<h3>` | `<div>`, `<span>` estilizados |
| Cada produto | `<article>` | `<div class="caixa-produto">` |
| Lista de produtos | `<ul>/<li>` | `<div>` na grade |
| Rodapé | `<footer>` + `<small>` | `<div class="rodape">` |

### Por que usar HTML semântico?

**Acessibilidade** — Leitores de tela (usados por pessoas cegas) navegam pela página usando atalhos como "ir para `<main>`" ou "listar todos os `<h2>`". Com `<div>`, esses atalhos não existem.

**SEO** — Mecanismos de busca entendem a hierarquia do conteúdo pelo HTML. Um `<h1>` tem peso diferente de um `<div>` com a mesma aparência visual.

**Manutenção** — O código comunica intenção. `<article>` diz "isso é um produto independente"; `<div>` não diz nada.

**Landmarks de navegação** — `<header>`, `<nav>`, `<main>` e `<footer>` criam pontos de navegação rápida para tecnologias assistivas.

---

## 🖱️ Módulo 2 — Página Interativa com JavaScript

### Sobre

Demonstração prática de manipulação do DOM e eventos JavaScript com design moderno (tema escuro, tipografia Syne + DM Mono).

### Funcionalidades implementadas

**Manipulação do DOM**
- Alteração de texto via `textContent`
- Troca de classes CSS via `classList.add()`, `classList.remove()`, `classList.toggle()`
- Mudança de estilos de fundo e cores dinamicamente
- Esconder e mostrar elementos com transição animada

**Eventos**

| Evento | Onde ocorre | O que faz |
|---|---|---|
| `click` | Botão principal | Muda texto e aplica destaque amarelo |
| `dblclick` | Botão dedicado | Incrementa contador, muda mensagem |
| `mouseover` | Botão principal | Muda mensagem ao passar o mouse |
| `keyup` | Campo de texto | Ecoa em tempo real o que é digitado |
| `keydown` | Campo de texto | Exibe a tecla pressionada (`key` e `code`) |
| `click` (reset) | Botão resetar | Restaura tudo ao estado inicial |

**Extras**
- Galeria de "imagens" com 5 temas (emoji + fundo colorido com transição suave)
- Esconder/mostrar elemento oculto com animação CSS via `max-height`
- Log de eventos em tempo real com timestamp e cor por tipo de evento

### Conceitos demonstrados

```javascript
// Seleção de elementos
const btn = document.getElementById('meuBotao');

// Adição de evento
btn.addEventListener('click', () => {
  elemento.textContent = 'Novo texto';
  elemento.classList.add('highlight');
});

// Evento de teclado
input.addEventListener('keydown', (e) => {
  console.log(e.key);   // tecla pressionada
  console.log(e.code);  // código físico da tecla
});

// Esconder / mostrar
elemento.classList.toggle('escondida');

// Reset de estado
btn.addEventListener('click', () => {
  input.value = '';
  saida.textContent = '';
  elemento.classList.remove('highlight');
});
```

---

## 🚀 Como executar

Nenhuma instalação necessária. Basta abrir os arquivos no navegador:

```bash
# Opção 1 — abrir diretamente
Clique duplo no arquivo .html

# Opção 2 — servidor local com Python
python -m http.server 3000
# Acesse: http://localhost:3000
```

---

## 📤 Como publicar no GitHub Pages

1. Crie um repositório no [github.com](https://github.com)
2. Faça upload dos arquivos em **Add file → Upload files**
3. Vá em **Settings → Pages**
4. Selecione a branch `main` e clique em **Save**
5. Acesse em: `https://seu-usuario.github.io/nome-do-repositorio/`

Ou pelo terminal:

```bash
git init
git add .
git commit -m "Primeiro commit — projeto web"
git remote add origin https://github.com/SEU_USUARIO/REPOSITORIO.git
git branch -M main
git push -u origin main
```

---

## 🛠️ Tecnologias utilizadas

- HTML5 semântico
- CSS3 (variáveis, transições, grid, flexbox)
- JavaScript puro (Vanilla JS) — sem frameworks
- Google Fonts: [Cormorant Garamond](https://fonts.google.com/specimen/Cormorant+Garamond), [DM Sans](https://fonts.google.com/specimen/DM+Sans), [Syne](https://fonts.google.com/specimen/Syne), [DM Mono](https://fonts.google.com/specimen/DM+Mono)

---

## 📚 Referências

- [MDN — HTML semântico](https://developer.mozilla.org/pt-BR/docs/Glossary/Semantics)
- [MDN — EventTarget.addEventListener](https://developer.mozilla.org/pt-BR/docs/Web/API/EventTarget/addEventListener)
- [MDN — Manipulação do DOM](https://developer.mozilla.org/pt-BR/docs/Web/API/Document_Object_Model)
- [WCAG — Diretrizes de acessibilidade](https://www.w3.org/WAI/standards-guidelines/wcag/)

---

*Projeto criado para fins educacionais — HTML semântico, eventos JavaScript e boas práticas de frontend.*
