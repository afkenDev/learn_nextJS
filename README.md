# Learn 

In den ersten drei Kapiteln des Tutorials habe ich die Grundlagen der Frontend-Entwicklung erlernt, die ich nun für mein nächstes Projekt im 241-Modul, das **„Healthy Food Box“-Projekt**, anwenden kann. Dabei konnte ich CSS und HTML in TypeScript integrieren sowie ein Projekt mit **Next.js** aufsetzen.

## Benötigte Technologien:
- **Next.js**: Ein Framework, das auf React aufbaut und serverseitiges Rendering sowie statische Webseiten-Generierung unterstützt.
- **TypeScript**: Eine typisierte Version von JavaScript, die insbesondere in größeren Projekten die Fehleranfälligkeit reduziert.
- **HTML & CSS**: Um die Benutzeroberfläche zu strukturieren und zu gestalten.

### Einbindung von HTML und CSS in TypeScript

Um HTML und CSS in ein **Next.js**-Projekt zu integrieren, werden funktionale Komponenten in React verwendet, die HTML-Strukturen enthalten. CSS kann auf zwei Arten eingebunden werden: 
1. Global mit einer `styles.css` Datei oder 
2. Modular, um spezifische Stile für bestimmte Komponenten zu definieren.

#### 1. HTML in einer React-Komponente:

```tsx
const Home: React.FC = () => {
  return (
    <div>
      <h1>Welcome to Healthy Food Box</h1>
      <p>Order your fresh ingredients today!</p>
    </div>
  );
};

export default Home;
```
## 2. Einbindung von CSS in eine Komponente (modular):

Zuerst erstellst du eine CSS-Datei namens `Home.module.css`.

```css
/* Home.module.css */
.container {
  text-align: center;
  padding: 20px;
}

.title {
  color: green;
  font-size: 2em;
}
```
Dann bindest du sie in deine Komponente ein:
```tsx
import styles from './Home.module.css';

const Home: React.FC = () => {
  return (
    <div className={styles.container}>
      <h1 className={styles.title}>Welcome to Healthy Food Box</h1>
      <p>Order your fresh ingredients today!</p>
    </div
  );
};

export default Home;
```
#### 3. Verwendung von globalem CSS:

Erstelle eine globale CSS-Datei, z.B. `styles/globals.css`, die in `_app.tsx` eingebunden wird:
```css
/* globals.css */
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
}
```
In der `_app.tsx` Datei wird die globale CSS-Datei eingebunden:
```tsx
import '../styles/globals.css';
import type { AppProps } from 'next/app';

function MyApp({ Component, pageProps }: AppProps) {
  return <Component {...pageProps} />;
}

export default MyApp;
```
Mit diesen Grundlagen kannst ich nun ein voll funktionsfähiges Frontend für dein "Healthy Food Box"-Projekt entwickeln.
