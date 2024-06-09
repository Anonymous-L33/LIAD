# Mapping Generator

## Project Description
This Java application is designed to generate mappings between files and modules by reading specific data files within a project directory. It outputs a JSON file detailing these mappings, which can be used for further processing by GIAR or systems.

## Features
- Generates mappings between files and modules efficiently.
- Outputs the mappings in a JSON format, facilitating integration with other applications.

## Getting Started

### Prerequisites
- Java 8 or higher is required to run this application.
- Maven is needed for building and packaging the application.

### Setup and Installation
1. Clone the repository to your local machine:
   ```bash
   git clone [Repository URL]
   cd [Project Directory]

2. Build the project using Maven to create an executable JAR file: 

   ```bash
   mvn clean package
   ```

3. ### Running the Application

   Run the application using the command below, replacing `[jar-file-name]` with the name of your built JAR file, and providing appropriate arguments for `<project>` and `<projectFolder>`:

   ```bash
   java -jar Mapping-jar-with-dependencies.jar <project> <projectFolder> <The file name that contains the module information>
   ```

​	Command Line Arguments:

​		`project`: The name of the project for which file-module mappings are being generated.

​		`projectFolder`: The path to the project directory where the necessary data files are located.

​		`module`: The name of the file for which module information are recorded.

## Output

The application will create a `file-module_mapping.json` file in the specified project folder. This file contains the mappings between the files and their respective modules.