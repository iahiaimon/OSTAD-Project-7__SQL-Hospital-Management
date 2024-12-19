CREATE TABLE Department (
    Department_ID INT PRIMARY KEY,
    Name VARCHAR(100),
    Location VARCHAR(100)
);



INSERT INTO Department (Department_ID, Name, Location) VALUES
(1, 'Cardiology', 'Building A, Floor 2'),
(2, 'Neurology', 'Building B, Floor 3'),
(3, 'Orthopedics', 'Building C, Floor 1'),
(4, 'Pediatrics', 'Building D, Floor 4'),
(5, 'Dermatology', 'Building A, Floor 1'),
(6, 'Gastroenterology', 'Building B, Floor 2'),
(7, 'Endocrinology', 'Building C, Floor 3'),
(8, 'Psychiatry', 'Building D, Floor 2'),
(9, 'Ophthalmology', 'Building A, Floor 3'),
(10, 'General Medicine', 'Building B, Floor 4');



CREATE TABLE Doctor (
    Doctor_ID INT PRIMARY KEY,
    Name VARCHAR(100),
    Specialization VARCHAR(100),
    Phone VARCHAR(15),
    Department_ID INT,
    FOREIGN KEY (Department_ID) REFERENCES Department(Department_ID)
);



INSERT INTO Doctor (Doctor_ID, Name, Specialization, Phone, Department_ID) VALUES
(1, 'Dr. Olivia Martinez', 'Cardiologist', '123-456-7890', 1),
(2, 'Dr. Liam Patel', 'Neurologist', '234-567-8901', 2),
(3, 'Dr. Sophia Wang', 'Orthopedic Surgeon', '345-678-9012', 3),
(4, 'Dr. Mason Lee', 'Pediatrician', '456-789-0123', 4),
(5, 'Dr. Ava Kim', 'Dermatologist', '567-890-1234', 1),
(6, 'Dr. James Rodriguez', 'Gastroenterologist', '678-901-2345', 2),
(7, 'Dr. Mia Garcia', 'Endocrinologist', '789-012-3456', 3),
(8, 'Dr. Noah Singh', 'Psychiatrist', '890-123-4567', 4),
(9, 'Dr. Isabella Gonzalez', 'Ophthalmologist', '901-234-5678', 1),
(10, 'Dr. Lucas Hernandez', 'General Practitioner', '012-345-6789', 2);



CREATE TABLE Patient (
    Patient_ID INT PRIMARY KEY,
    Name VARCHAR(100),
    Age INT,
    Gender VARCHAR(20),
    Phone VARCHAR(30)
);


INSERT INTO Patient (Patient_ID, Name, Age, Gender, Phone) VALUES
(21, 'Ethan Walker', 34, 'Male', '123-456-7890'),
(22, 'Ava Johnson', 28, 'Female', '234-567-8901'),
(23, 'Mason Lee', 45, 'Male', '345-678-9012'),
(24, 'Isabella Harris', 39, 'Female', '456-789-0123'),
(25, 'Logan Clark', 56, 'Male', '567-890-1234'),
(26, 'Chloe Martinez', 63, 'Female', '678-901-2345'),
(27, 'Lucas Scott', 29, 'Male', '789-012-3456'),
(28, 'Zoe Anderson', 40, 'Female', '890-123-4567'),
(29, 'James Taylor', 52, 'Male', '901-234-5678'),
(30, 'Madison Moore', 38, 'Female', '012-345-6789');




CREATE TABLE Appointment (
    Appointment_ID INT PRIMARY KEY,
    Date DATE,
    Time TIME,
    Status VARCHAR(50),
    Doctor_ID INT,
    Patient_ID INT,
    FOREIGN KEY (Doctor_ID) REFERENCES Doctor(Doctor_ID),
    FOREIGN KEY (Patient_ID) REFERENCES Patient(Patient_ID)
);



INSERT INTO Appointment (Appointment_ID, Date, Time, Status, Doctor_ID, Patient_ID) VALUES
(1, '2024-12-20', '09:00:00', 'Scheduled', 1, 21),
(2, '2024-12-20', '10:30:00', 'Scheduled', 2, 21),
(3, '2024-12-20', '11:00:00', 'Completed', 3, 21),
(4, '2024-12-21', '14:00:00', 'Scheduled', 1, 21),
(5, '2024-12-21', '15:30:00', 'Completed', 4, 21),
(6, '2024-12-22', '08:30:00', 'Scheduled', 2, 21),
(7, '2024-12-22', '13:00:00', 'Canceled', 5, 21),
(8, '2024-12-23', '11:30:00', 'Scheduled', 3, 21),
(9, '2024-12-23', '16:00:00', 'Completed', 4, 21),
(10, '2024-12-24', '09:30:00', 'Scheduled', 5, 30);



SELECT * FROM `hospital management`.Department;
SELECT * FROM doctor;