# MechanicAppointment
Database 
create database mechanicapp;

CREATE TABLE customer (
    customerid INT AUTO_INCREMENT PRIMARY KEY,
    firstName VARCHAR(255) NOT NULL,
    lastName VARCHAR(255) NOT NULL,
    address VARCHAR(255),
    emailid VARCHAR(255) UNIQUE NOT NULL,
    mobileNo INT
);

ALTER TABLE customer
MODIFY COLUMN mobileNo BIGINT;



CREATE TABLE Appointment (
    appointmentid INT AUTO_INCREMENT PRIMARY KEY,
    date DATETIME NOT NULL,
    location VARCHAR(255),
    vehiclename VARCHAR(255),
    vehiclenumber VARCHAR(255),
    customername VARCHAR(255),
    servicetype VARCHAR(255),
    additionalinfo TEXT,
    customerid INT, 
    CONSTRAINT FK_Customerid FOREIGN KEY (customerid) REFERENCES Customer(cutomerid)
);
