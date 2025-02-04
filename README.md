# 📑 Apache POI - Excel as a Simple Database

🚀 This project demonstrates how to use Apache POI to store, retrieve, and manipulate `Person` records in an Excel file, effectively treating it as a lightweight database.

## 📌 Features
- **Read & Write Excel (`.xlsx`)** using Apache POI.
- **Store Person Records** with attributes: `ID`, `First Name`, `Last Name`, `Phone Number`.
- **CRUD Operations**:
  - Save a list of persons to a new or existing file.
  - Retrieve all persons or fetch a person by ID.
- **Excel File Handling** with `WorkbookFactory`.

## 🛠 Prerequisites
Ensure you have the following installed:
- [Java 8+](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)
- [Maven](https://maven.apache.org/)
- Apache POI dependency in `pom.xml`

## 🚀 Getting Started
### 1️⃣ Clone the Repository
```sh
git clone https://github.com/your-username/poi-excel-person-db.git
cd poi-excel-person-db
```

### 2️⃣ Build & Run
Compile and execute the project using Maven:
```sh
mvn clean install
mvn exec:java -Dexec.mainClass="Application"
```

## 📜 Usage
Saving Data to Excel
You can store person records into an Excel file:
```java
List<Person> persons = List.of(
    new Person(1L, "Shervin", "Zadsorur", "09999999999"),
    new Person(2L, "Shahab", "Ranjbary", "09999999999"),
    new Person(3L, "Reza", "Dehghani", "09999999999")
);
PersonService personService = new PersonService();
personService.saveToNewFile(persons);
```

Loading Data from Excel
Retrieve all saved persons:

```java
List<Person> allPersons = personService.loadAll();
allPersons.forEach(System.out::println);
```

Fetch a specific person by ID:
```java
Person person = personService.loadById(2L);
System.out.println(person);
```

## 🏆 Why Apache POI?
Apache POI is a powerful Java library for reading and writing Microsoft Office documents. This project leverages POI for:

- Lightweight data storage without a database.
- Simple Excel-based data handling for small-scale applications.
