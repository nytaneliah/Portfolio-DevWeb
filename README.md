# Portfolio Vue.js FRANCAIS

Un portfolio interactif et moderne réalisé avec Vue 3 utilisant la Composition API, destiné à présenter vos réalisations, vos compétences et à permettre aux visiteurs de vous contacter via un formulaire.

## Prérequis

Avant de commencer, assurez-vous que les outils suivants sont installés sur votre machine :

- [Node.js](https://nodejs.org/) (version 16 ou supérieure)
- [npm](https://www.npmjs.com/) (installé avec Node.js)

## Installation

Suivez les étapes ci-dessous pour installer et lancer le projet :

### 1. Cloner le dépôt

Clonez ce dépôt sur votre machine locale :

```bash
git clone https://github.com/nytaneliah/Portfolio-DevWeb
cd votre-repo
```

### 2. Initialiser le projet avec `create-vue`

Si ce n'est pas déjà fait, créez un projet Vue 3 avec la commande suivante :

```bash
npm create vue@latest
```

Lors de l'installation, choisissez les options suivantes :

- **Vue Router for Single Page Application** : `Yes`
- **Pinia for state management** : `No` (si non utilisé dans le projet)
- **TypeScript** : `No` (sauf si vous souhaitez utiliser TypeScript)
- **ESLint** : `Yes` (recommandé pour maintenir un code propre)

### 3. Installer les dépendances

Installez les dépendances nécessaires :

```bash
npm install
```

### 4. Configurer les variables d'environnement

Créez un fichier `.env` à la racine du projet pour définir les variables nécessaires (comme l'adresse e-mail pour le formulaire de contact) :

```env
VITE_CONTACT_EMAIL=votre.email@example.com
```

### 5. Lancer le projet en développement

Démarrez le serveur de développement avec :

```bash
npm run dev
```

Par défaut, l'application sera accessible sur [http://localhost:5173](http://localhost:5173).

### 6. Construire pour la production

Pour préparer une version de production, exécutez :

```bash
npm run build
```

Cela générera un dossier `dist` contenant les fichiers prêts pour le déploiement.

## Structure du Projet

Voici une brève explication de la structure du projet :

```
src/
├── assets/         # Fichiers statiques (images, vidéos, etc.)
├── components/     # Composants réutilisables
├── views/          # Pages principales (ex : HomeView, NotFoundView)
├── router/         # Configuration des routes Vue Router
├── App.vue         # Composant racine
├── main.js         # Point d'entrée de l'application
```

## Fonctionnalités

- **Header** : Menu de navigation avec ancres vers les sections principales.
- **Section Présentation** : Mettez en avant vos valeurs et votre approche.
- **Section Créations** : Affiche vos réalisations avec une modal détaillée.
- **Section Contact** : Formulaire permettant aux visiteurs de vous envoyer un message.
- **Page 404** : Redirige les visiteurs perdus sur une page dédiée.
- **Responsive Design** : Adapté pour mobile, tablette et bureau.

## Dépendances principales

- **Vue 3** : Framework JavaScript utilisé pour construire l'application.
- **Vue Router** : Gestion des routes et de la navigation.
- **Vite** : Outil pour le développement rapide et la construction.

## Contributions

Les contributions sont les bienvenues ! Si vous avez des suggestions ou des améliorations, n'hésitez pas à soumettre une issue ou une pull request.

## License

Ce projet est sous licence MIT. Consultez le fichier `LICENSE` pour plus d'informations.


# Portfolio Vue.js ENGLISH

An interactive and modern portfolio built with Vue 3 using the Composition API. This project showcases your work, highlights your skills, and allows visitors to contact you through a form.

## Prerequisites

Before starting, ensure the following tools are installed on your machine:

- [Node.js](https://nodejs.org/) (version 16 or higher)
- [npm](https://www.npmjs.com/) (included with Node.js)

## Installation

Follow these steps to set up and run the project:

### 1. Clone the Repository

Clone this repository to your local machine:

```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
```

### 2. Initialize the Project with `create-vue`

If not already done, create a Vue 3 project using the following command:

```bash
npm create vue@latest
```

During the setup, choose the following options:

- **Vue Router for Single Page Application**: `Yes`
- **Pinia for state management**: `No` (if not used in the project)
- **TypeScript**: `No` (unless you want to use TypeScript)
- **ESLint**: `Yes` (recommended for clean code)

### 3. Install Dependencies

Install the required dependencies:

```bash
npm install
```

### 4. Configure Environment Variables

Create a `.env` file at the root of the project to define necessary variables (e.g., contact email for the form):

```env
VITE_CONTACT_EMAIL=your.email@example.com
```

### 5. Run the Development Server

Start the development server with:

```bash
npm run dev
```

By default, the app will be accessible at [http://localhost:5173](http://localhost:5173).

### 6. Build for Production

To prepare a production-ready version, run:

```bash
npm run build
```

This will generate a `dist` folder containing the deployable files.

## Project Structure

Here’s a quick overview of the project structure:

```
src/
├── assets/         # Static files (images, videos, etc.)
├── components/     # Reusable components
├── views/          # Main pages (e.g., HomeView, NotFoundView)
├── router/         # Vue Router configuration
├── App.vue         # Root component
├── main.js         # Application entry point
```

## Features

- **Header**: Navigation menu with anchor links to main sections.
- **Presentation Section**: Showcase your values and approach.
- **Creations Section**: Display your projects with a detailed modal.
- **Contact Section**: A form allowing visitors to send you a message.
- **404 Page**: Redirect lost visitors to a dedicated page.
- **Responsive Design**: Optimized for mobile, tablet, and desktop.

## Key Dependencies

- **Vue 3**: The JavaScript framework used to build the app.
- **Vue Router**: Manages routes and navigation.
- **Vite**: Ensures fast development and builds.

## Contributions

Contributions are welcome! If you have suggestions or improvements, feel free to submit an issue or a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
