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
Ahora, ya podemos construir nuestras primeras rutas. Hay que utilizar el Router dentro del ```return``` de App.js (o dentro del componente donde estemos poniendo las rutas). Y, dentro de éste, irán todas las rutas utilizando ```Route```. Un ejemplo de implementación de la sintaxis es la siguiente:

```javascript
import React from 'react';
import Home from './Home
import About from './About';
import Contact from './Contact';
import Users from './Users';
import {BrowserRouter as Router, Route} from 'react-router-dom';
import './App.css';

function App() {
  return (
    <div className="App">
      <Router>
        <Route path="/" component={Home}/>
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

En el ejemplo de arriba, tenemos tres rutas que nos renderizan cuatro componentes distintos: ```Home```, que nos llevaría a nuestra página principal, y ```About```, ```Contact``` y ```Users```. Ahora ya tenemos acceso a todas estos componentes si vamos al enlace correspondiente. Si fuéramos a ```<nuestraPagina>/about```, veremos en la pantalla el componente ```About```. Pero, también veremos el contenido del componente ```Home```. ¿Por qué?

Cuando utilizamos el ```Router```, y vamos a un url específico (por ejemplo, '/about'), la página nos renderiza también el componente ```Home```. Esto es debido a que este método renderiza todos los componentes que contengan parte del nombre del url. Y, como '/about' contiene '/' en su nombre, este último también se va a mostrar.

Para evitar esto, podemos añadir el atributo ```exact``` al cualquier ```Route``` que queremos que exclusivamente se muestre cuando vamos al url exacto. De esta forma, podemos evitar que el componente ```Home``` se muestre en todas nuestras otras rutas.

Lo pondríamos de esta forma:

```javascript
<Route path="/" exact component={Home}/>
```

Ahora, cuando vayamos a ```<nuestraPagina>/about```, ya no se renderizará ```Home```.



## Crear un navbar
