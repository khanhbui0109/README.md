# README.md
StudentId1_StudentId2_2200008348_buiquockhanh

CREATE TABLE Tour (
    TourId INT PRIMARY KEY IDENTITY(1,1),
    TourName NVARCHAR(100) NOT NULL,
    Duration INT,
    Price DECIMAL(18, 2)
);
GO

CREATE TABLE Destination (
    DestinationId INT PRIMARY KEY IDENTITY(1,1),
    DestinationName NVARCHAR(100) NOT NULL,
    City NVARCHAR(100),
    PhotoPath NVARCHAR(200),
    TourId INT FOREIGN KEY REFERENCES Tour(TourId)
);
GO

INSERT INTO Tour (TourName, Duration, Price) VALUES
    (N'Khám phá miền Bắc', 5, 5500000),
    (N'Hành trình miền Trung', 4, 4600000),
    (N'Du ngoạn miền Tây', 3, 3900000);
GO

INSERT INTO Destination (DestinationName, City, TourId, PhotoPath) VALUES
    (N'Vịnh Hạ Long', N'Quảng Ninh', 1, 'halong.png'),
    (N'Tam Cốc – Bích Động', N'Ninh Bình', 1, 'ninhbinh.png'),
    (N'Phố cổ Hội An', N'Quảng Nam', 2, 'hoian.png'),
    (N'Thánh địa Mỹ Sơn', N'Quảng Nam', 2, 'myson.png'),
    (N'Chợ nổi Cái Răng', N'Cần Thơ', 3, 'cantho.png'),
    (N'Rừng Tràm Trà Sư', N'An Giang', 3, 'trasu.png');
GO
