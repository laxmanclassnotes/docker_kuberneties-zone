### Create a postgress container and Lgin DataBase services

* Let's create an postgres container with user panoramic and password as trekking
* Take a EC2 Machine
* Install Docker (or) using Docker playdround
    * Follow the below commands
 `docker container run -d -P --name pasqldb -e POSTGRES_USER=panoramic -e POSTGRES_PASSWORD=trekking -e POSTGRES_DB=psqldata postgres`
  ![Preview](./Images/docker17.png)

`docker container ls`
![Preview](./Images/docker18.png)

`docker exec -it pasqldb /bin/bash`
![Preview](./Images/docker19.png)

```
psqldata=#  use employees;

psqldata=#  CREATE TABLE Persons (
              PersonID int,
              LastName varchar(255),
              FirstName varchar(255),
              Address varchar(255),
              City varchar(255)
            );

psqldata=#  Insert into Persons Values (1,'Gottipati','laxman', 'Ongole', 'AndhraPradesh');

psqldata=#   select * from Persons;

```
![Preview](./Images/docker20.png)

