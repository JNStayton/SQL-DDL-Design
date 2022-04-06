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

Appointments
-
id int PK
DoctorID int FK >- Doctor.DoctorID
PatientID int FK >- Patient.PatientID
AppointmentTime datetime 

Doctor
-
DoctorID PK int
Name string INDEX

Diseases
-
DiseaseID PK int
Disease string

Diagnoses
-
ID PK int
ApptID int FK >- Appointments.id
DiseaseID int FK >- Diseases.DiseaseID
Notes text

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
AssistantRef1 int FK >- Referees.RefereeID
AssistantRef2 int FK >- Referees.RefereeID
HomeTeam int FK >- Teams.TeamID
AwayTeam int FK >- Teams.TeamID
Season int FK >- Seasons.SeasonID

Seasons
-
SeasonID int PK
StartDate date
EndDate date

Results
-
ResultsId int PK
TeamID int FK >- Teams.TeamID
MatchID int FK >- Matches.MatchID
Result

Lineups
-
id int PK
PlayerID int FK >- Players.PlayerID
MatchID int FK >- Matches.MatchID
TeamID int FK >- Teams.TeamID