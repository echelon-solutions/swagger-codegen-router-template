# swagger-codegen-router-template

A template for swagger-codegen that generates a Node.js project 
that validates and routes requests to a url.

## Environment

- Install [Vagrant](https://www.vagrantup.com/)

## Development Workflow

### 1. Clone the repository

```bash
git clone https://github.com/echelon-solutions/swagger-codegen-router-template.git
```

### 2. Add an Open API (Swagger) specification file

```bash
# Change into the repository directory
cd swagger-codegen-router-template

# Add the swagger specification file
cp <some-directory>/swagger.yaml ./src/main/resources/swagger.yaml
```

### 3. Generate the Node.js router API project

```bash
# Bring up the Vagrant build environment
vagrant up

# Login to the environment
vagrant ssh 

# Change into the project directory
# Vagrant syncs the /project directory with your host machine
cd /project

# Run Maven to build and output the project
# Output can be found in /project/target/generated-sources/swagger/
mvn clean package
```

## Support

Please reach out to [support@echelon.solutions](mailto:support@echelon.solutions) 
with any questions, concerns, or suggestions.

Also, feel free to clone/fork this project and suggest changes and 
updates via a "Pull Request".
