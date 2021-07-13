# OTD_ReferentialIntegrity

MySQL Tables:
	Flight
	Booking
  passenger

CREATE TABLE `booking` (
  `idbooking` int NOT NULL AUTO_INCREMENT,
  `flightid` int DEFAULT NULL,
  `personid` int DEFAULT NULL,
  PRIMARY KEY (`idbooking`),
  KEY `flightid_idx` (`flightid`),
  KEY `passengerid_idx` (`personid`),
  CONSTRAINT `flightid` FOREIGN KEY (`flightid`) REFERENCES `flight` (`idflight`),
  CONSTRAINT `passengerid` FOREIGN KEY (`personid`) REFERENCES `passenger` (`idpassenger`)
) ENGINE=InnoDB AUTO_INCREMENT=9952 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

CREATE TABLE `flight` (
  `idflight` int NOT NULL,
  `code` varchar(45) DEFAULT NULL,
  `from` varchar(45) DEFAULT NULL,
  `to` varchar(45) DEFAULT NULL,
  `date` varchar(45) DEFAULT NULL,
  `price` varchar(45) DEFAULT NULL,
  PRIMARY KEY (`idflight`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

CREATE TABLE `passenger` (
  `idpassenger` int NOT NULL AUTO_INCREMENT,
  `firstname` varchar(45) DEFAULT NULL,
  `lastname` varchar(45) DEFAULT NULL,
  `dob` varchar(45) DEFAULT NULL,
  `address1` varchar(45) DEFAULT NULL,
  `address2` varchar(45) DEFAULT NULL,
  `city` varchar(45) DEFAULT NULL,
  `postcode` varchar(45) DEFAULT NULL,
  PRIMARY KEY (`idpassenger`)
) ENGINE=InnoDB AUTO_INCREMENT=9888 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
