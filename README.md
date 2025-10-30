
# 🧑‍💼 Employee Details Form — Spring Boot + Thymeleaf

A simple web application built using **Spring Boot**, **Thymeleaf**, and **Hibernate Validator** to demonstrate **form validation** using `@PostMapping`.  
This project validates employee input fields such as First Name, Department, and Skills, and displays validation messages directly on the form.

---

## 🚀 Features
- Form submission using `@PostMapping`
- Server-side validation using **Hibernate Validator (Bean Validation)**
- Error messages shown dynamically in the Thymeleaf template
- Clean MVC structure (`Model`, `Controller`, `View`)
- Form data binding with `@ModelAttribute`
- Simple and educational example for beginners learning Spring MVC + Thymeleaf

---

## 🧠 Tech Stack
- **Language:** Java 17+
- **Framework:** Spring Boot
- **Template Engine:** Thymeleaf
- **Validation:** Hibernate Validator
- **IDE:** IntelliJ IDEA
- **Build Tool:** Maven

---

## 📂 Project Structure
src/
├─ main/
│ ├─ java/com/Employee/EmployeeInfo/
│ │ ├─ Model/
│ │ │ └─ Employee.java # Entity class with validation
│ │ └─ Controller/
│ │ └─ EmployeeController.java # Handles form & validation logic
│ ├─ resources/
│ │ ├─ templates/
│ │ │ ├─ Employee_Form.html # Form view
│ │ │ └─ Employee_Details.html # Display view
│ │ └─ application.properties # Config file

--

## ⚙️ How It Works

1. **`@RequestMapping("/ShowForm")`**  
   Displays the Employee form and loads available skills from application properties.

2. **`@PostMapping("/ProcessForm")`**  
   Receives submitted data, validates it, and:
   - If there are errors → redisplays the form with error messages.
   - If validation passes → shows the `Employee_Details` page.

3. **Validation Example**
```java
@NotNull(message = "The First_Name Is Empty")
@Size(min = 1, message = "The First_Name Is Empty")
private String FirstName;

--
🧩 Example Controller
@PostMapping("/ProcessForm")
public String process(@Valid @ModelAttribute("employee") Employee employee,
                      BindingResult bindingResult) {
    if (bindingResult.hasErrors()) {
        return "Employee_Form";
    } else {
        return "Employee_Details";
    }
}

🪄 How to Run

Clone the repository:

git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>


Open the project in IntelliJ IDEA or VS Code.

Run the Spring Boot application:

mvn spring-boot:run


Visit the form at:
👉 http://localhost:8080/ShowForm


👤 Author

Aravindhan K
💻 Java & Spring Boot Developer

🌐 GitHub: https://github.com/Aravindhan2212.

🔗 LinkedIn: https://www.linkedin.com/in/aravindhan-k-34b288228.

📞 +91-6380355497



## 📂 Project Structure
