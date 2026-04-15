# Bahmni-Insurance-Connect 
A java application/service for integration with OpenIMIS (Insurance Management System)
 - Gateway for communication between OpenIMIS system and Bahmni components like openmrs, odoo
 - FHIR Client for handling FHIR resources communication between OpenIMIS and Bahmni
 - FHIR resources construction for insurance related stuffs like claim, eligibility coverage etc.

## Build
 - ``mvn clean package``
 - Generates rpm and packaged jar
 
## Deployment 
 - Install the generated rpm on top of existing Bahmni installed platform (works only from Bahmni 0.92 )
 - Configure the application.properties file: add necessary credentials and urls (`/etc/insurance-integration/insurance-integration.properties`)

## Fix

### RPM Build
Run the following command to build the project and generate the `.rpm` file.
```bash
mvn clean package rpm:attached-rpm
```
**Path** `./target/rpm/insurance-integration/RPMS/noarch/insurance-integration-0.0.1-1.noarch.rpm`

### Notes
- **Comment out** `org.bahmni.insurance.test` This package (or module) uses data from existing servers and should be commented out during the process.