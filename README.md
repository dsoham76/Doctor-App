# Doctor App

## Framework and Language

> Framework: SpringBoot Language: Java 8

## Data flow

1.  Controller

        1.1  Appointment Controller
                - @GetMapping("appointments")
        1.2 Doctor Controller
                - @PostMapping("doctor")
                - @GetMapping("doctors")
        1.3 Patient Controller
                - @PostMapping("patient/signup"): To sign up a user
                - @PostMapping("patient/signIn"): To sign in a user
                - @DeleteMapping("patient/signOut"): To sign out a user
                - @GetMapping("patients")
                - @PostMapping("appointment/schedule")
                - @DeleteMapping("appointment/cancel") 

2.  Services

        2.1 Appointment Service
                - getAllAppointments()
                - saveAppointment(Appointment appointment)
                - getAppointmentForPatient(Patient patient)
                - cancelAppointment(Appointment appointment)

        2.2 Authentication Service
                - authenticate(String email, String authTokenValue)
                
        2.3 Doctor Service
                - addDoctor(Doctor doc)
                - getAllDoctors()
    
        2.4 PatientService
                - signUpPatient(Patient patient)
                - signInPatient(SignInInput signInInput)
                - sigOutPatient(String email)
                - scheduleAppointment(Appointment appointment)
                - cancelAppointment(String email)
                
        
3.  Repository

        3.1 Patient Repo
        3.2 Autentication Repo
        3.3 Doctor Repo
        3.4 Appointment Repo

4.  Database Design
        4.1 Admin Model
                - Long adminId;
                - String adminName;
                - String adminEmail;
                - String adminPassword;
    
        4.2 Appointment Model
                - Long appointmentId;
                - String appointmentDesc;
                - LocalDateTime appointmentScheduleTime;
                - LocalDateTime appointmentCreationTime;
                - Patient patient;    
                - Doctor doctor;
    
        4.3 AuthenticationToken Model
                - Long tokenId;
                - String tokenValue;
                - LocalDateTime tokenCreationDateTime;
                - Patient patient;

        4.4 Doctor Model
                - Long doctorId;
                - String doctorName;  
                - Specialization specialization;
                - String doctorContactNumber;
                - Qualification qualification;
                - Double doctorConsultationFee;
                - List<Appointment> appointments;
    
        4.5 Patent Model:
                - Long patientId;
                - String patientName;
                - String patientEmail;
                - String patientPassword;
                - Integer patientAge;
                - String patientAddress;
                - private Gender gender;
                - Appointment appointment;
    
## Data Structure Used in Project

     JPARepository has been used as primay datastructure

## Project Summary

    The  Doctor  is a comprehensive software solution designed to keep track of orders . The system provides a centralized platform that enables  user to create, read, edit, and delete appointment.
