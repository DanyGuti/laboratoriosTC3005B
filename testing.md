# Laboratorio de Testing

---

## Objetivo

* Realizar conexión de testing local en emulador.
* Realizar tests con chai, mocha y handler estándar.

---
## Prerequisitos

* Conocimiento manejo de versiones
* [TENER PROYECTO DE FIREBASE PREVIAMENTE CREADO EN LABORATORIO DE BACKEND](https://firebase.google.com/docs/functions/get-started?hl=es-419&gen=2nd)
* Tener docker desktop instalado

En este laboratorio de Testing, estaremos dando seguimiento al laboratorio de Backend, por lo que utilizaremos el mismo proyecto de Firebase, por cuestion de simplicidad y tiempos.

---

Las tecnologías a utilizar son las siguientes:

* NodeJS
* JS y Express
* Docker
* Firebase
* Firestore
* JSDoc
* ESLint plugin de AirBnB
* Mocha
* Chai
---

## Checklist
- [ ] Realizar testing CRUD `messages`

## Instrucciones

Seguir los pasos descritos para llevar a cabo la práctica de la misma y llegar a cierto nivel de dominio de las tecnologías descritas anteriormente.

---

## Paso 1 Creación de archivos a utilizar

Comenzaremos por crear el archivo `messages.spec.js` dentro del directorio `test`.

Dentro del file `messages.spec.js`, copia, analiza y pega lo siguiente:

``` 
import { describe } from "mocha";
import "chai-http";
import chai from "chai";
import chaiExclude from "chai-exclude";
import chaiHttp from "chai-http";

import Message from "../src/models/message.model.js";
import { getMessage, addMessage } from "../src/controllers/message.controller.js";

const { expect } = chai;

chai.use(chaiExclude);
chai.use(chaiHttp);
```
Lo único que estamos haciendo, es hacer el setup de nuestro testing. Importando todo lo necesario, modelos, librerías e inicializando estas.

> ### ¿Cómo conseguiremos CI?

En el proyecto Housse of Valkyr, se automatizará el proceso de revisión de tests de backend (tipo de tests realizados como en este laboratorio) con el fin de obtener CI (Continuous Integration) de DevOps, en este caso, no cubriremos esa parte, pero es importante que sepamos el proceso llevado a cabo.

Dichos tests correrán cuando haya un Pull Request dirigido a ramas base: main y develop.

>### ¿Cómo funcionará el testing?

Tendremos `3 environments` dentro del proyecto Housse of Valkyr. Un environment de `"development"` local con el emulador cada persona con su base de datos del emulador, uno de `"testing"` que será una cuenta compartida en la cual tendremos acceso todos los miembros del equipo Housse of Valkyr a una base de datos "integral" y otro de `"production"` en el cual, una vez que tengamos todo integrado en `"development"`, pasará al ambiente de `"production"` con cuenta del socio formador. 

En este laboratorio, dejaremos el acceso como si fuera `development`, al emulador de firestore, al cual haremos las pruebas.

No importa mucho lo que insertemos a la base de datos, pues tenemos 4 métodos importantes (`hooks`), que nos ofrece mocha: `beforeAll`, `afterAll`, `beforeEach` y `afterEach`.






