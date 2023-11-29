 
# GITHUB PAGES Y VITE

Instalar React con Vite

Ctrl+C para cortar y volver a tener a terminal

INSTALAR gh-pages: Permite automatizar la publicacion de archivos en la rama gh-pages

1.**npm i gh-pages -D**  

2.Crear repo de github  

3.Inicializar repo local  

4.Vincular repo remoto  

5.Despues ir a vite.config.js y agregar base con el nombre del repo remoto (deben estar las barras), no olvidar todas las comas  

6.Para que tome esa carpeta y tome esos archivos hay que agregar en el script del package.json el deploy (no olvidar comas) y guardar  

7.Hacer **npm run build**, que creara la carpeta dist y guardar

8.Luego ejecutar **npm run deploy** (si vamos al repo aparecera la rama gh-pages), eso activa github pages  

9.Cuando se actualiza no se ve el logo entonces vamos app.js y donde esta la imagen del logo se saca la barra al inicio  

10.Despues volver a correr npm run build y npm run deploy que lleva a la rama nueva, hacemos git push y actualiza  


**VITE.CONFIG.JS**  

import { defineConfig } from "vite";  

import react from "@vitejs/plugin-react";  


// https://vitejs.dev/config/  

export default defineConfig({  

    plugins: [react()],  
    
base: "/el-nombre-de-tu-repositorio/", (sin .git)  

});

![image](https://github.com/verobaires/react-vite-githubpages/assets/34665102/59451af0-17af-488d-8fbc-460ce25a2837)


**PACKAGE.JSON**  

"deploy": "gh-pages -d dist"  

"scripts": {  

    "dev": "vite",  
    
    "build": "vite build",  
    
    "preview": "vite preview",  
    
    "deploy": "gh-pages -d dist"
}

![image](https://github.com/verobaires/react-vite-githubpages/assets/34665102/90c5f710-d6e9-43c6-beae-772155cbd471)
