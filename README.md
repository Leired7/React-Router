# React Router

React Router es un paquete que nos facilita la conexión de rutas dentro de React.

## Pasos para tener acceso al Router

1. Instalar la dependencia desde nuestra terminal, dentro de la carpeta donde tenemos instalado nuestro proyecto con React:

```$ npm install react-router-dom```

2. Importar ```BrowserRouter``` desde la dependencia que acabamos de descargar en App.js:

```javascript
import {BrowserRouter as Router} from 'react-router-dom';
```
:warning: El archivo original se llama ```BrowserRouter```, pero es bastante común importarlo solo como ```Router``` ya que es más legible y se entiende mejor.

###

3. Importar ```Route``` desde la dependencia que acabamos de descargar en App.js:
```javascript
import {BrowserRouter as Router, Route} from 'react-router-dom';
```
Ahora, ya podemos construir nuestras primeras rutas. Hay que utilizar el Router dentro del ```return``` de App.js. Y, dentro de éste, irán todas las rutas utilizando ```Route```. Un ejemplo de implementación de la sintaxis es la siguiente:

```javascript
import React from 'react';
import About from './About';
import Contact from './Contact';
import Users from './Users';
import {BrowserRouter as Router, Route} from 'react-router-dom';
import './App.css';

function App() {
  return (
    <div className="App">
      <Router>
        <Route path="/about" component={About}/>
        <Route path="/contact" component={Contact}/>
        <Route path="/users" component={Users}/>
      </Router>
    </div>
  );
}

export default App;
```

En cada ```Route``` pondremos dos atributos: el ```path```, que nos indica la ruta que tenemos que escribir en el URL del navegador, y el ```component```, que nos indica el componente que queremos renderizar cuando accedamos a la ruta mencionada en ```path```. 

En el ejemplo de arriba, tenemos tres rutas que nos renderizan tres componentes distintos. Por ejemplo, si fueramos a ```<nuestra web>/about``` nos aparecería en la pantalla el componente ```About.js```.


## Crear un navbar
