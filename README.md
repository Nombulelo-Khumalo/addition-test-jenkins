

---

### 📄 `README.md`

```markdown
# 🧮 CalculatorFunc

A simple Node.js calculator app with unit tests written in Jest, designed to demonstrate continuous integration with Jenkins and Docker.

---

## 📦 Project Structure

```
addition-test-jenkins/
├── calculator.js          # Simple calculator logic
├── calculator.test.js     # Unit tests using Jest
├── package.json           # Project metadata and dependencies
├── Jenkinsfile            # Jenkins pipeline definition
└── .gitignore             # Ignore node_modules, etc.
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Nombulelo-Khumalo/addition-test-jenkins
cd addition-test-jenkins
```

### 2. Install dependencies

```bash
npm install
```

### 3. Run tests

```bash
npm test
```

---

## ⚙️ Jenkins Pipeline

This project uses a Jenkins pipeline that:

1. Runs inside a Docker container (`node:16-alpine`)
2. Installs dependencies (`npm install`)
3. Runs unit tests (`npm test`)

### Jenkinsfile Overview

```groovy
pipeline {
  agent {
    docker {
      image 'node:16-alpine'
      args '-e npm_config_cache=/tmp/.npm'
    }
  }

  stages {
    stage('Install') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      steps {
        sh 'npm test'
      }
    }
  }
}
```

---

## ✅ Requirements

- [Node.js](https://nodejs.org/) (for local testing)
- [Jenkins](https://www.jenkins.io/) with Docker support
- Git

---

## 🧪 Test Example

```js
test('adds 2 + 2 to equal 4', () => {
  expect(add(2, 2)).toBe(4);
});
```

---

## 📫 Author

**Nombulelo Khumalo**

---

## 📜 License

This project is open-source and free to use.
```

