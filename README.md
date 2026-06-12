# React + Vite

# Portfolio Update Project

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.
This project is a web application designed to manage and update a personal portfolio. It provides functionalities to add, edit, and delete projects and certifications, as well as upload images, all through a user-friendly interface. The data is stored and managed via a GitHub repository acting as a simple backend.

Currently, two official plugins are available:

## Features

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh
- **Project Management**: Add new projects with details like name, description, links (project and GitHub), and image paths.
- **Certification Management**: Add new certifications with details like name, category, and link.
- **Edit & Delete**: Modify or remove existing projects and certifications.
- **Image Upload**: Upload images directly to a designated GitHub repository, with automatic naming and tracking.
- **GitHub API Integration**: Utilizes the GitHub API for data persistence, treating JSON files in a repository as a simple database.
- **User Authentication (via Token)**: Secure operations using a GitHub Personal Access Token.
- **Modern UI**: Built with React and styled using Tailwind CSS and Material-UI (MUI) Joy.

## Technologies Used

- **Frontend**: React.js, Vite
- **State Management**: Zustand (for global state)
- **Data Fetching**: React Query (for caching and synchronization)
- **Styling**: Tailwind CSS, Material-UI (MUI) Joy
- **Form Handling**: Formik
- **HTTP Client**: Axios
- **Unique IDs**: `uuid`
- **Version Control**: Git, GitHub API

## Setup and Installation

1.  **Clone the repository**:
    ```bash
    git clone <repository-url>
    cd portfolio_update
    ```
2.  **Install dependencies**:
    ```bash
    npm install
    # or
    yarn install
    ```
3.  **Environment Variables**:
    Create a `.env` file in the root directory and add your GitHub API base URLs:

    ```
    VITE_API_URL_BASE=https://api.github.com/repos/<YOUR_GITHUB_USERNAME>/<YOUR_REPO_NAME>/contents/
    VITE_API_URL_BASE_IMG=https://api.github.com/repos/<YOUR_GITHUB_USERNAME>/<YOUR_IMAGE_REPO_NAME>/contents/images/
    ```

    Replace `<YOUR_GITHUB_USERNAME>`, `<YOUR_REPO_NAME>`, and `<YOUR_IMAGE_REPO_NAME>` with your actual GitHub username and repository names. These repositories will store your `projetos.json`, `certificate.json`, `objImagens.json`, and the actual image files.

4.  **Run the development server**:
    ```bash
    npm run dev
    # or
    yarn dev
    ```
    The application will be accessible at `http://localhost:5173` (or another port if 5173 is in use).

## Usage

1.  **Generate a GitHub Personal Access Token**:
    - Go to GitHub -> Settings -> Developer settings -> Personal access tokens -> Tokens (classic) -> Generate new token.
    - Grant `repo` scope permissions.
    - **Important**: Keep your token secure and do not expose it publicly.
2.  **Access the Application**:
    - Navigate to the running application in your browser.
    - Use the provided forms to add, edit, or delete portfolio items.
    - When prompted, enter your GitHub Personal Access Token to authorize operations.

## Project Structure

```
src/
├── components/         # Reusable UI components
├── pages/
│   ├── FormCertification/ # Page for adding certifications
│   ├── FormProject/       # Page for adding projects
│   ├── Lista/             # Page for listing, editing, and deleting items
│   │   ├── components/
│   │   └── services/
│   ├── UploadImg/         # Page for uploading images
│   │   └── utils/
│   └── ...
├── store/              # Zustand global state management
├── main.tsx            # Entry point
└── ...
```
