# Quick Database Diagrams
## This is the text for Quick Database Diagrams used to get the diagram schemas for each exercise. 

## Medical Center Schema

Patient
-
PatientID PK int
Name string INDEX
Address string
Phone Int
EmergencyContact string

MedicalCenter
-
CenterID PK int
Name string INDEX
Address string
Phone int

Doctor
-
DoctorID PK int
Name string INDEX
MedicalOffice int FK >- MedicalCenter.CenterID 

Diseases
-
DiseaseID PK int
Disease string

Diagnoses
-
ID PK int
DoctorID int FK >- Doctor.DoctorID
PatientID int FK >- Patient.PatientID
DiseaseID int FK >- Diseases.DiseaseID

## Craigslist Schema

Regions
-
RegionID PK int
Name string Index

Posts
-
PostID PK int
Title string Index
Text string
Location string
CategoryID int FK >- Categories.CatID
UserID int FK >- Users.UserID
RegionID int FK >- Regions.RegionID

Users
-
UserID PK int
Username string Index
Password varchar 
RegionID int FK >- Regions.RegionID

Categories
-
CatID PK int
Name string Index

## Sports League Schema

Teams
-
TeamID PK int
Name string Index

Goals
-
GoalID PK int
ScoredBy int FK >- Players.PlayerID
Game int FK >- Matches.MatchID

Players
-
PlayerID PK int
Name string Index
TeamID int FK >- Teams.TeamID

Referees
-
RefereeID int PK
Name string Index

Matches
-
MatchID int PK
RefereeID int FK >- Referees.RefereeID
HomeTeam int FK >- Teams.TeamID
AwayTeam int FK >- Teams.TeamID
Season int FK >- Seasons.SeasonID

Seasons
-
SeasonID int PK
StartDate date
EndDate date