#GITHUB PAGES Y VITE

Instalar React con Vite

Ctrl+C para cortar y volver a tener a terminal

INSTALAR gh-pages: Permite automatizar la publicacion de archivos en la rama gh-pages

1.**npm i gh-pages -D**  
2.Crear repo de github
3.Inicializar repo local
4.Vincular repo remoto
5.Despues ir a \_vite.config.js\_ y agregar base con el nombre del repo remoto (deben estar las barras), no olvidar todas las comas
6.Hacer **npm run build**, que creara la carpeta dist y guardar
7.Para que tome esa carpeta y tome esos archivos hay que agregar en el script del \_package.json\_ el deploy (no olvidar comas) y guardar
8.Luego ejecutar **npm run deploy** (si vamos al repo aparecera la rama gh-pages), eso activa github pages
9.Cuando se actualiza no se ve el logo entonces vamos app.js y donde esta la imagen del logo se saca la barra al inicio
10.Despues volver a correr **npm run build** y **npm run deploy** que lleva a la rama nueva, hacemos **git push** y actualiza

vite.config.js  

import { defineConfig } from "vite";  

import react from "@vitejs/plugin-react";  


// https://vitejs.dev/config/  


export default defineConfig({  

    plugins: [react()],  
    
base: "/el-nombre-de-tu-repositorio/", (sin .git)  

});

![image](https://github.com/verobaires/react-vite-githubpages/assets/34665102/0346268e-f54d-4d97-965a-d78f6f00f5f5)

package.json  

"deploy": "gh-pages -d dist"  

"scripts": {  

    "dev": "vite",  
    
    "build": "vite build",  
    
    "preview": "vite preview",  
    
    "deploy": "gh-pages -d dist"  
    
}  

![image](https://github.com/verobaires/react-vite-githubpages/assets/34665102/bb59722f-5204-47df-90d0-6368762dd94d)
