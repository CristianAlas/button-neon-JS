Button Neon JS

Este proyecto implementa botones con un efecto de neón dinámico utilizando HTML, CSS y JavaScript. Además, el efecto de iluminación varía en función de la posición del cursor del usuario.

Características

Efecto de neón dinámico: Los botones presentan un resplandor animado.

Interactividad con el cursor: La iluminación cambia en función de la posición del cursor.

Diseño responsivo y moderno: Compatible con diferentes tamaños de pantalla.

Tecnologías utilizadas

HTML5 para la estructura.

CSS3 para los estilos y efectos visuales.

JavaScript (ES6) para capturar y sincronizar la posición del cursor.

Instalación y uso

Clona este repositorio:

git clone https://github.com/tu_usuario/tu_repositorio.git

Accede al directorio del proyecto:

cd tu_repositorio

Abre el archivo index.html en tu navegador web.

Archivos principales

index.html → Contiene la estructura básica de la página.

style.css → Define los estilos y efectos visuales.

script.js → Maneja la detección del movimiento del cursor y actualiza los efectos dinámicamente.

Funcionalidad del código

script.js

Captura la posición del cursor en la pantalla.

Calcula la posición relativa y actualiza variables CSS dinámicamente.

const syncPointer = ({ x: pointerX, y: pointerY }) => {
    const x = pointerX.toFixed(2);
    const y = pointerY.toFixed(2);
    const xp = (pointerX / window.innerWidth).toFixed(2);
    const yp = (pointerY / window.innerHeight).toFixed(2);
    document.documentElement.style.setProperty('--x', x);
    document.documentElement.style.setProperty('--xp', xp);
    document.documentElement.style.setProperty('--y', y);
    document.documentElement.style.setProperty('--yp', yp);
}
document.body.addEventListener('pointermove', syncPointer);

style.css

Define los estilos de los botones.

Implementa efectos de resplandor dinámicos con gradientes y sombras.

button {
    border-radius: 1rem;
    text-transform: uppercase;
    font-weight: bold;
    letter-spacing: 0.1ch;
    background: var(--bg);
    border: 4px solid transparent;
    box-shadow: 0 1px hsl(0 0% 100% / 0.15) inset;
    cursor: pointer;
    background: linear-gradient(var(--bg), var(--bg)) padding-box,
                var(--glow),
                linear-gradient(black, black) border-box;
    transition: background-size 0.24s;
    touch-action: none;
    position: relative;
    padding: 1rem 2rem;
}

Autor

Proyecto desarrollado por Cristian Alas.

Licencia

Este proyecto se distribuye bajo la licencia MIT. ¡Siéntete libre de modificarlo y mejorarlo! 🚀

https://cristianalas.github.io/button-neon-JS/
