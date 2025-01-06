-- Creating the stdDetails table
CREATE TABLE stdDetails (
    rollno INT NOT NULL,
    stdname VARCHAR(30),
    email VARCHAR(34),
    PRIMARY KEY (rollno)
);

-- Inserting data into stdDetails table
INSERT INTO stdDetails (rollno, stdname, email) 
VALUES 
    (1, "ram", "r@gmail.com"),  
    (2, "shyam", "sm@gmail.com"),  
    (3, "sonam", "sonam@gmail.com"), 
    (4, "harish", "harsh2@gmail.com");

-- Creating the marksheet table
CREATE TABLE marksheet (
    mid INT NOT NULL,
    rollno INT,
    physics INT,
    biology INT,
    chemistry INT,
    PRIMARY KEY (mid),
    FOREIGN KEY (rollno) REFERENCES stdDetails (rollno)
);

-- Inserting data into marksheet table
INSERT INTO marksheet (mid, rollno, physics, biology, chemistry) 
VALUES 
    (101, 1, 56, 78, 58),
    (103, 3, 67, 45, 67);

-- Attempting to insert invalid data
-- Uncomment the line below only after fixing the data (e.g., rollno 6 does not exist in stdDetails)
-- INSERT INTO marksheet (mid, rollno, physics, biology, chemistry) VALUES (106, 6, 78, 45, 38);

-- Fix duplicate key error by using a unique mid value
INSERT INTO marksheet (mid, rollno, physics, biology, chemistry) 
VALUES (102, 2, 78, 45, 38);
