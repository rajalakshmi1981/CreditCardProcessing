# Credit Card Processing Demo Project 

Demo Project for Credit Card Processing

### Project Details

Technologies used: Java 8, SpringBoot
Database: In memory H2 database

Since we have not used the file persistence in application.properties for the H2 database the data is cleaned when application is restarted 

For Demo purposes we have used the H2 database and we can plugin any other database by including the appropriate drivers and providing the database details

### Build

Run mvn clean install

### Testing

Run mvn test

### Runnning

using Maven 

mvn spring-boot:run

Using java -jar command 

java -jar target/CreditCardProcessing-0.0.1-SNAPSHOT.jar

### API's

If running locally then 

#### Add Credit Card API 

URL is http://localhost:<port>/creditcards/add and the method used is POST

Request and Response in JSON format 

Sample Input JSON 

{
  "name": "Tester nam21",
  "cardLimit":"1000",
  "cardNumber" : "1111222233334444"
}

Related Output

{
    "statusCode": "202 ACCEPTED",
    "message": "Card Details saved successfully"
}

For Error Condition 


{
  "name": "Tester nam21",
  "cardLimit":"ACBD",
  "cardNumber" : "1111222233334444"
}


Related Output

{
    "statusCode": "400 BAD_REQUEST",
    "message": "No valid Limit given"
}


Get All Cards API 

#### Get All Cards API 

URL is http://localhost:<port>/creditcards/getall and the method used is GET

Sample Output

[
    {
        "id": 1,
        "name": "Tester name1",
        "cardNumber": "1111222233334444",
        "cardLimit": "1000",
        "cardBalance": "0"
    }
]


