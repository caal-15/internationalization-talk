class: introOutro

.introOutroText[
  # Internacionalización
  ## Usando .green[__i18n__] en .green[__React__]
]

---
class: blueBg1, middle, center

# Contenido

.contentTable[
  |||
  |---|---|
  |.green[__1. __]|Internacionalización y Lenguaje|
  |.green[__2. __]|I18n - Filosofía|
  |.green[__3. __]|I18next - Configuración|
  |.green[__4. __]|Demo|
]

.footnote[Sigue esta presentación en: [caal-15.github.io/internationalization-talk](https://caal-15.github.io/internationalization-talk/).]

---
class: blueBg1, middle, center

# Internacionalización

Es el _arte_ de adaptar software al .green[__lenguaje__] y .green[__particularidades__] de una región en _específico_.

.footnote[Si quieres estas diapositivas para tu presentación puedes encotnrarlas [aquí](https://github.com/caal-15/team-intl-remark-slideshow).]

---
class: whiteBg1

# Hablemos del lenguaje

El _lenguaje_ es lo primero que viene a la mente cuando pensamos en __internacionalizar__ una aplicación, y a su vez, la parte más __difícil__, debido a sus .green[__particularidades__]:

* _Géneros:_ puede haber más de 2, pueden cambiar de singular a plural.
* _Plurales:_ puede haber distintas formas para distintos números de objetos.
* _Fraseo:_ cómo se debe expresar una idea para que suene adecuada en el contexto puede cambiar dramáticamente.
* _Excepciones:_ todos los lenguajes contienen excepciones a sus propias reglas que pueden parecer totalmente arbitrarias.

---
class: whiteBg1

# Software Automatizado

Para traducciones _básicas_, podemos usar __software automatizado__ para ahorrarnos trabajo, sin embargo, tiene .green[__grandes desventajas__] si queremos precisión:

* En el peor caso la traducción puede ser __incorrecta__.
* En el mejor de los casos la traducción puede sonar __incómoda__.
* No puede tener en cuenta aspectos como el __fraseo__ y el __tono__ que quiere transmitir la aplicación.

Por estos motivos debemos asegurarnos que al menos las partes _importantes_ de nuestra aplicación estén __bien__ traducidas.

---
class: blueBg1, middle, center

# I18n

No es más que una serie de .green[__estándares__] que describen el proceso de __internacionalización__, y ha generado a su vez numerosas _librerías_ en diferentes lenguajes para este propósito.

.footnote[__Internacionalización__ se acorta .green[_i18n_] debido a las __18__ letras entre la __i__ y la __n__.]

---
class: whiteBg1

# Filosofía

.green[__I18n__] pretende precisamente que las traducciones sean lo más __precisas__ posible, teniendo en cuenta __conceptos de la gramática__ como tal (_géneros_, _plurales_, _excepciones_, etc.) y también __conceptos abstractos__ tales como la _intención_, el _tono_ o el _fraseo_.

Debido a ello no es suficiente con traducción __palabra a palabra__, se requiere una traducción .green[__frase a frase__] que garantice que las mismas conserven __todo__ el significado que quieren transmitir.

---
class: blueBg1, middle, center

# I18next

.green[`i18next`] es una librería hecha en .green[_JavaScript_] que nos ayuda a cumplir el propósito de _inteniacionalizar_ nuestra app.

Cuenta con herramientas que facilitan su integración con muchos __frameworks__ y __librerías__, en nuestro caso utilizaremos .green[`react-i18next`].

.footnote[[Página oficial de i18next](https://www.i18next.com/), [Página oficial de react-i18next](https://react.i18next.com/)]

---
class: whiteBg1, middle

# Instalando todo

```bash
npm i \
  i18next \
  react-i18next \
  i18next-xhr-backend \
  i18next-browser-languagedetector
```

---
class: whiteBg1, middle

# Configuración

```javascript
import i18n from 'i18next';
import { initReactI18next } from 'react-i18next';
import Backend from 'i18next-xhr-backend';
import LanguageDetector from 'i18next-browser-languagedetector';

i18n
  .use(Backend)
  .use(LanguageDetector)
  .use(initReactI18next)
  .init({
    fallbackLng: 'en',
    debug: process.env.NODE_ENV === 'development',
    load: 'currentOnly',
    interpolation: {
      escapeValue: false
    }
  });
```

---
class: blueBg1, middle, center

.green[
  # Hora del Demo!
]

.footnote[El repositorio del demo lo pueden encontrar [aquí](https://github.com/caal-15/internationalization-example).]

---
class: introOutro

.introOutroText[
  # Muchas Gracias!
]
