

## JUIT WebKiosk API - Spring Boot (Unofficial)

<img alt="Spring" src="https://img.shields.io/badge/spring-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white"/> <img alt="Java" src="https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=java&logoColor=white"/>

A __working api__ for accessing JUIT WebKiosk Data. Created using Java Spring Boot.        


**(Source Code will be made public later)**       


BASE URL: http://172.105.35.94/    

### Required request body
```
{
    "enrollmentNumber": "XXXXXX",
    "password": "XXXXXXXX"
}
```

### Endpoints

* ```/api/login```    
  Login into the JUIT WebKiosk portal.
  

* ```/api/attendance```    
  Get attendance details for a given semester.
  

* ```/api/detailedAttendance```   
  Get detailed attendance records.
  

* ```/api/cgpa```   
  Get the CGPA report for all semesters.
  

* ```/api/examGrade```    
  Get the Exam Grades for a given semesters.
  

* ```/api/semesters```    
  Get the list of valid Semester Codes.
  

* ```/api/subjectFaculty```   
  Get the list of registered subject faculty.
  
  
* ```/api/subjects```   
  Get the list of registered subjects for a given semester


## Examples

- ### Subject Faculty
**Endpoint:**      
```http://172.105.35.94/api/subjectFaculty```      
**Request:**     
 ```curl -X POST "https://webkiosk-juit.herokuapp.com/api/subjectFaculty" -H "accept: */*" -H "Content-Type: application/json" -d "{ \"enrollmentNumber\": \"191306\", \"password\": \"XXXXXXXX\"}"```           
**Response:**
  ```
  [
  {
    "subjectName": "MODELING AND SIMULATION TECHNIQUES",
    "lectureFaculty": "RAJINDER SANDHU",
    "tutorialFaculty": null,
    "practicalFaculty": null,
    "subjectCode": "18B11CI413"
  },
  {
    "subjectName": "WEB TECH LAB",
    "lectureFaculty": null,
    "tutorialFaculty": null,
    "practicalFaculty": "HEMRAJ SAINI",
    "subjectCode": "18B17CI474"
  },
  {
    "subjectName": "FINANCE AND ACCOUNTS",
    "lectureFaculty": "AMIT SRIVASTAVA",
    "tutorialFaculty": null,
    "practicalFaculty": null,
    "subjectCode": "18B11HS411"
  },
  {
    "subjectName": "DESIGN & ANALYSIS OF ALGORITHMS",
    "lectureFaculty": "AMIT KUMAR",
    "tutorialFaculty": null,
    "practicalFaculty": null,
    "subjectCode": "18B11CI412"
  },
  {
    "subjectName": "DATA SIMULATION LAB",
    "lectureFaculty": null,
    "tutorialFaculty": null,
    "practicalFaculty": "PRADEEP KUMAR GUPTA",
    "subjectCode": "18B17CI473"
  },
  {
    "subjectName": "OPERATING SYSTEM LAB",
    "lectureFaculty": null,
    "tutorialFaculty": null,
    "practicalFaculty": "SURJEET SINGH",
    "subjectCode": "18B17CI471"
  },
  {
    "subjectName": "ENVIRONMENTAL STUDIES",
    "lectureFaculty": "POONAM SHARMA",
    "tutorialFaculty": null,
    "practicalFaculty": null,
    "subjectCode": "18B11GE411"
  },
  {
    "subjectName": "DESIGN AND ANALYSIS OF ALGORITHMS LAB",
    "lectureFaculty": null,
    "tutorialFaculty": null,
    "practicalFaculty": "MRITYUNJAY SINGH",
    "subjectCode": "18B17CI472"
  },
  {
    "subjectName": "OPERATING SYSTEMS",
    "lectureFaculty": "SURJEET SINGH",
    "tutorialFaculty": null,
    "practicalFaculty": null,
    "subjectCode": "18B11CI411"
  }
]
  ```

- ### Attendance
**Endpoint:**      
```http://172.105.35.94/api/attendance```  
**Request:**       
 ```curl -X POST "https://webkiosk-juit.herokuapp.com/api/attendance" -H "accept: */*" -H "Content-Type: application/json" -d "{ \"enrollmentNumber\": \"191306\", \"password\": \"XXXXXXXX\"}"```       
**Response:**       
  ```
  [
  {
    "subjectName": "DATA SIMULATION LAB",
    "subjectCode": "18B17CI473",
    "overallAttendance": 100,
    "lectureAttendance": null,
    "tutorialAttendance": null,
    "practicalAttendance": 100,
    "detailAttendanceUrl": "https://webkiosk.juit.ac.in:9443/StudentFiles/Academic/ViewDatewiseLecAttendance.jsp?EXAM=2021EVESEM&CTYPE=R&SC=190174&LTP=P&&mRegConfirmDate=12-01-2021&prevPFSTID=&mPFSTID=JUIT2100753"
  },
  {
    "subjectName": "DESIGN & ANALYSIS OF ALGORITHMS",
    "subjectCode": "18B11CI412",
    "overallAttendance": 76,
    "lectureAttendance": 76,
    "tutorialAttendance": null,
    "practicalAttendance": null,
    "detailAttendanceUrl": "https://webkiosk.juit.ac.in:9443/StudentFiles/Academic/ViewDatewiseLecAttendance.jsp?EXAM=2021EVESEM&CTYPE=R&SC=190173&LTP=LT&mRegConfirmDate=12-01-2021&prevTFSTID=&prevLFSTID=&mLFSTID=JUIT2002561&mTFSTID="
  },
  {
    "subjectName": "DESIGN AND ANALYSIS OF ALGORITHMS LAB",
    "subjectCode": "18B17CI472",
    "overallAttendance": 70,
    "lectureAttendance": null,
    "tutorialAttendance": null,
    "practicalAttendance": 70,
    "detailAttendanceUrl": "https://webkiosk.juit.ac.in:9443/StudentFiles/Academic/ViewDatewiseLecAttendance.jsp?EXAM=2021EVESEM&CTYPE=R&SC=190176&LTP=P&&mRegConfirmDate=12-01-2021&prevPFSTID=&mPFSTID=JUIT2002581"
  },
  {
    "subjectName": "ENVIRONMENTAL STUDIES",
    "subjectCode": "18B11GE411",
    "overallAttendance": 92,
    "lectureAttendance": 92,
    "tutorialAttendance": null,
    "practicalAttendance": null,
    "detailAttendanceUrl": "https://webkiosk.juit.ac.in:9443/StudentFiles/Academic/ViewDatewiseLecAttendance.jsp?EXAM=2021EVESEM&CTYPE=R&SC=190130&LTP=LT&mRegConfirmDate=12-01-2021&prevTFSTID=&prevLFSTID=&mLFSTID=JUIT2100018&mTFSTID="
  },
  {
    "subjectName": "FINANCE AND ACCOUNTS",
    "subjectCode": "18B11HS411",
    "overallAttendance": 71,
    "lectureAttendance": 71,
    "tutorialAttendance": null,
    "practicalAttendance": null,
    "detailAttendanceUrl": "https://webkiosk.juit.ac.in:9443/StudentFiles/Academic/ViewDatewiseLecAttendance.jsp?EXAM=2021EVESEM&CTYPE=R&SC=190129&LTP=LT&mRegConfirmDate=12-01-2021&prevTFSTID=&prevLFSTID=&mLFSTID=JUIT2002176&mTFSTID="
  },
  {
    "subjectName": "MODELING AND SIMULATION TECHNIQUES",
    "subjectCode": "18B11CI413",
    "overallAttendance": 100,
    "lectureAttendance": 100,
    "tutorialAttendance": null,
    "practicalAttendance": null,
    "detailAttendanceUrl": "https://webkiosk.juit.ac.in:9443/StudentFiles/Academic/ViewDatewiseLecAttendance.jsp?EXAM=2021EVESEM&CTYPE=R&SC=190171&LTP=LT&mRegConfirmDate=12-01-2021&prevTFSTID=&prevLFSTID=&mLFSTID=JUIT2100738&mTFSTID="
  },
  {
    "subjectName": "OPERATING SYSTEM LAB",
    "subjectCode": "18B17CI471",
    "overallAttendance": 87,
    "lectureAttendance": null,
    "tutorialAttendance": null,
    "practicalAttendance": 87,
    "detailAttendanceUrl": "https://webkiosk.juit.ac.in:9443/StudentFiles/Academic/ViewDatewiseLecAttendance.jsp?EXAM=2021EVESEM&CTYPE=R&SC=190175&LTP=P&&mRegConfirmDate=12-01-2021&prevPFSTID=&mPFSTID=JUIT2002612"
  },
  {
    "subjectName": "OPERATING SYSTEMS",
    "subjectCode": "18B11CI411",
    "overallAttendance": 86,
    "lectureAttendance": 86,
    "tutorialAttendance": null,
    "practicalAttendance": null,
    "detailAttendanceUrl": "https://webkiosk.juit.ac.in:9443/StudentFiles/Academic/ViewDatewiseLecAttendance.jsp?EXAM=2021EVESEM&CTYPE=R&SC=190172&LTP=LT&mRegConfirmDate=12-01-2021&prevTFSTID=&prevLFSTID=&mLFSTID=JUIT2002632&mTFSTID="
  },
  {
    "subjectName": "WEB TECH LAB",
    "subjectCode": "18B17CI474",
    "overallAttendance": null,
    "lectureAttendance": null,
    "tutorialAttendance": null,
    "practicalAttendance": null,
    "detailAttendanceUrl": null
  }
]
  ```

## Full Documentation

Read the full documentation [here.](http://172.105.35.94/)  

