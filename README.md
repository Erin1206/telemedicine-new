# Telemedicine project
This is a simple telemedicine project which helps doctor and patients to connect using video conferencing and chat. You can see the full demo of the same at https://www.youtube.com/watch?v=GslXbdrWbgk. The video is in Nepalese language but you should be able to follow it up.

Below  is the basic flow of the project.

1. Doctor logs in , Patient logs in by filling his issues.
2. Both go in to video conference call and discuss issues.
3. Doctor fills advice.
4. Patient can  print advice after the call.
5. Doctor and patients can also send chat messages to each other. 
6. Patients can also share documents with doctor.



Features :-

Application supports Multi doctor and Multihospital.

Medication can be filled by Doc

Patient can input problems

Chat message support between doctors and patients.

Patients can share document with doctors while conferencing.

Tracks time spent per call between doctor and patient.

Its created using Angular as front end and .NET core as back end and postgre database. Any further technical clarification send me mail at shiv_koirala@yahoo.com.

This complete initative is funded by https://danphehealth.com . 
--

#Telemedecine Installation
## "Step 1 copy the code to my local drive"
### "Step 1 Started cloning..."
git clone https://github.com/opensource-emr/Telemedicine --quiet
### "Cloning finished..."
## "Step 2 Installation of Angular"
### "Step 2 Change to Angular director..."
cd .\Telemedicine\FewaTelemedicine\ClientApp
### "Step 3 Start installing angular..."
npm install
### "Step Installation of Angular finished"
### "Step 4 Running ng Build..."
ng build --deploy-url=/ClientApp/
### "Step  ng Build finished..."

## "Step 3 Building Project"
### "Step 5 Go to the Dotnet CSPROJ..."
cd..
### "Step 6 Start building..."
dotnet build
### "Step Finish dotnet build..."

## "Step 4 Install dotnet tool"
### "Step 7 Install dotnet tool..."
dotnet tool install --global dotnet-ef
### "Step  Install dotnet tool finished..."

## "Step 5 Creating DB..."
& "D:\postgreinstallation\bin\psql.exe" -U postgres -w -d postgres -c " SELECT pg_terminate_backend(pid) FROM pg_stat_activity WHERE datname = 'fewatelemedicine'; " | Out-Null
& "D:\postgreinstallation\bin\psql.exe" -U postgres -w -d postgres -c "drop database IF EXISTS  fewatelemedicine;" | Out-Null
& "D:\postgreinstallation\bin\psql.exe" -U postgres -w -d postgres -c "create database fewatelemedicine;" | Out-Null
dotnet ef migrations remove 
dotnet ef migrations add v1 
dotnet ef database update
### "Step DB Creation finished..."

## "Step 6 Running the application..."
dotnet build 
dotnet run
start ‘https://localhost:5001’
