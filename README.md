# 📊 GitHub Footprint CLI

![Java](https://img.shields.io/badge/Java-17%2B-blue)
![CLI](https://img.shields.io/badge/CLI-Tool-orange)

A lightweight command-line tool to fetch and display GitHub user activity directly in your terminal.
GitHub Footprint CLI - A Java tool to fetch and display GitHub user activity (commits, PRs, stars) in terminal. Pure Java, no deps. java -jar footprint.jar &lt;username>.

---

## 📌 About

**GitHub Footprint CLI** is a Java-based command-line application that allows you to view public GitHub activity for any user, including:

- ✅ Commits
- ✅ Pull Requests
- ✅ Issues
- ✅ Stars

It utilizes **GitHub’s REST API v3** and is built with **pure Java** — no external HTTP libraries required.

---

## 📚 Table of Contents

- [About](#-about)
- [Tech Stack](#-tech-stack)
- [Quick Start](#-quick-start)
- [Project Structure](#-project-structure)
- [Features](#-features)
- [Configuration](#-configuration)
- [Examples](#-examples)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🛠️ Tech Stack

| Component        | Description               |
|------------------|---------------------------|
| Language         | Java 17+                  |
| HTTP Client      | `HttpURLConnection`       |
| JSON Parser      | `org.json` (minimal JAR)  |
| Output Format    | Plaintext (terminal)      |
| Packaging        | Executable `.jar` file    |

---

## 🚀 Quick Start

### ✅ Prerequisites

- Java 17 or higher
- (Optional) GitHub Personal Access Token for increased rate limits

### 📥 Installation & Usage

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/github-footprint-cli.git
   cd github-footprint-cli
   ```

2. **Build and Run**:
   ```bash
   # Compile
   javac -cp .:lib/org.json.jar src/*.java src/models/*.java -d out/

   # Run
   java -cp out/:lib/org.json.jar com.github.footprint.Main <github-username>
   ```

3. **Or use the JAR**:
   ```bash
   java -jar github-footprint.jar <github-username>
   ```

---

## 📂 Project Structure

```
github-footprint-cli/
├── src/
│   ├── Main.java                 # CLI entry point
│   ├── GitHubAPIClient.java     # GitHub API interaction
│   ├── models/
│   │   └── ActivityEvent.java   # Data model for events
├── lib/
│   └── org.json.jar             # Minimal JSON parser
├── out/                         # Compiled classes
├── .gitignore
└── README.md
```

---

## ✨ Features

- 🔍 Fetch recent GitHub activity for any public user
- 📦 Minimal dependencies (pure Java)
- ⚙️ Easy-to-run CLI interface
- 💡 Extensible codebase for new activity types

---

## ⚙️ Configuration

| Option                     | Description                           |
|----------------------------|---------------------------------------|
| `GITHUB_TOKEN` (optional)  | GitHub PAT for increased API limits   |

Set your token in the environment before running the CLI:
```bash
export GITHUB_TOKEN=your_token_here
```

---

## 📌 Examples

```bash
# View recent activity for torvalds
java -jar github-footprint.jar torvalds
```

```bash
# Using environment variable for GitHub token
export GITHUB_TOKEN=your_token
java -jar github-footprint.jar octocat
```

---

## 🗺️ Roadmap

- [x] Basic GitHub activity fetching
- [x] CLI interface
- [ ] Add GitHub authentication (via token)
- [ ] Enhanced output formatting (e.g., color, table)
- [ ] Support for more event types (forks, comments)
- [ ] Bundle into native executable using jpackage or GraalVM

---

## 🤝 Contributing

Contributions are welcome! Feel free to fork the repo, create a branch, and open a pull request.

> 📌 Please ensure your code is clean, documented, and tested before submitting a PR.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---
