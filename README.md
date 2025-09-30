# Dec2024POMFramework

A robust and scalable Page Object Model (POM) framework for Selenium-based test automation, designed for maintainability, reusability, and ease of integration. This framework streamlines automated UI testing, enabling efficient test development for modern web applications.

---

## 🚀 Features

- **Page Object Model Architecture:** Clean separation of page logic and test code.
- **Modular Design:** Reusable components for faster test creation.
- **Scalable Structure:** Easily add and manage new pages and tests.
- **Robust Reporting:** Integrated Allure reporting for clear and detailed test results.
- **Flexible Configuration:** Supports multiple environments and browsers.
- **Data-Driven Testing:** Utilizes Data Providers for comprehensive test coverage.

---

## 📦 Tech Stack

- **Language:** Java
- **Testing Framework:** TestNG
- **Automation Tool:** Selenium WebDriver
- **Build Tool:** Maven
- **Reporting:** Allure
- **Others:** Data Provider for parameterized testing

---

## 🏗️ Project Structure

<details>
<summary>Click to expand</summary>

```
Dec2024POMFramework/
├── src/
│   ├── main/
│   │   └── java/           # Core framework code & page objects
│   └── test/
│       └── java/           # Test cases
├── resources/              # Test data, config files
├── reports/                # Test execution reports
├── pom.xml                 # Maven build configuration
└── README.md
```
</details>

---

## ⚡ Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/sudeeppanshikar/Dec2024POMFramework.git
   ```
2. **Install dependencies**
   ```bash
   mvn clean install
   ```
3. **Configure settings**
   - Update configuration files in `/resources` as needed.
4. **Run tests**
   ```bash
   mvn test
   ```

---

## 📄 Usage

- Define page objects in the `pageobjects` package.
- Write test cases in the `tests` package.
- Configure browsers and environments in the config files.
- Review Allure reports in the `/reports` directory after test execution.

---

## 📝 Contribution

Contributions are welcome! Please open issues or submit pull requests for improvements, bug fixes, or new features.

---

## 💬 Support

For questions, suggestions, or collaborations, please open an issue on GitHub or contact [@sudeeppanshikar](https://github.com/sudeeppanshikar).

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

> **Built with ❤️ by [sudeeppanshikar](https://github.com/sudeeppanshikar)**
