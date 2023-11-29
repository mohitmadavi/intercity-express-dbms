# intercity-express-dbms
contribution

MOHIT MADAVI: ER DIAGRAM,RELATIONAL SCHEMA, INSERT DATA INTO TABLES


DHARMESH JAIN:ER DIAGRAM,RELATIONAL SCHEMA, INSERT DATA INTO TABLES


ASHWIN CHOUDHARY:COLLECTION OF DATA


ER DIAGRAM:-
relations:

stations(Station_code,Station_name,No_of_Platform,State)

Trains(Train_n,Train_name,Capacity,Route_n)

Coaches(coach_n,made_by,last_maintained,mileage)

Active_Coaches(Coach_n,Train_n,Date)

Standby_Coaches(Coach_n,Date)

Maintainance(Maintain_n,Maintain_date,Maintain_type,Coach_n)

Tickets(Ticket_n,Train_n,Status,passenger_name,Age,Board_stn,drop_stn,date_of_journey,booking_date,fare,discount, traveller_id,agent_comm)

Traveller(Traveller_Id,Traveller_Name,ADD,MOB,Email)

Staffs(Staff_n,Staff_name,Contact_n,residence_city)

Seats(Seat_n,Seat_type)

Staff_schedule(Route_n,Train_n,Driver_n,Remark,Time,Date,Accomodation)

Train_schedule(Route_n,Train_n,Station_code,Date,ETA,AAT,EDT,ADT)

Seat_allocated(Ticket_n,Coach_n,Seat_n,Seat_type,Date,Time)

Train_coaches(Train_n,Coach_n,Date_from)
Route(Route_n,Route_name,time_taken,total_dist,Start_Stn,Start_time,End_Stn,End_time)


CREATE DATABASE INTERCITY EXPRESS;

create table stations(station_code varchar(10) primary key,station_name varchar(30),no_of_platform int,state varchar(20));


create table tickets(ticket_n varchar(10) primary key,train_n int,status varchar(10),passenger_name varchar(30),age int,passenger_type enum("child","adult","senior-citizen"),boarding_stn varchar(10),dropping_stn varchar(10),date_of_journey date,booking_date date,fare float(2),discount float(2),traveller_id varchar(10),agent_comm float(2),foreign key(train_n) references trains(train_n),foreign key(boarding_stn) references stations(station_code), foreign key(dropping_stn) references stations(station_code),foreign key(traveller_id) references traveller(traveller_id));


create table train_coaches(train_n int,coach_n varchar(10),date_from date,date_to date,foreign key(train_n) references trains(train_n),foreign key(coach_n) references active_coaches(coach_n),primary key(train_n,coach_n,date_from,date_to));


create table train_schedule(route_n varchar(10),train_n int,station_code varchar(10),Date date,eat time,aat time,edt time,adt time,foreign key(route_n) references routes(route_n),foreign key(train_n) references trains(train_n),foreign key(station_code) references stations(station_code),primary key(route_n,train_n,station_code,Date));



create table trains(train_n int primary key,train_name varchar(30),capacity int,route_n varchar(10) not null,foreign key(route_n) references routes(route_n));


create table traveller(traveller_id varchar(10) primary key,traveller_name varchar(30),address varchar(50),contactno varchar(15),email varchar(30));


create table seats(seat_n int primary key,type varchar(20));

create table standby_coaches(coach_n varchar(10),Date date,primary key(coach_n,date),foreign key(coach_n) references coaches(coach_n));



create table staffs(staff_n varchar(10) primary key,staff_name varchar(20),contact_no varchar(15),residence_city varchar(20));

create table staff_schedule(route_n varchar(10),train_n int,staff_n varchar(10),remark varchar(20),date date,time time,accomodation varchar(10),foreign key(route_n) references routes(route_n),foreign key(train_n) references trains(train_n),foreign key(staff_n) references staffs(staff_n),primary key(route_n,train_n,staff_n,date));



create table seat_allocated(ticket_n varchar(10),coach_n varchar(10),seat_n int,seat_type varchar(10),Date date,Time time,foreign key(ticket_n) references tickets(ticket_n),foreign key(coach_n) references active_coaches(coach_n),foreign key(seat_n) references seats(seat_n),primary key(ticket_n,Date,Time));



create table routes(route_n varchar(10) primary key,route_name varchar(30),time_taken time,total_dist_km int,start_stn varchar(10),start_time time,end_stn varchar(10),end_time time,foreign key(start_stn) references stations(station_code),foreign key(end_stn) references stations(station_code));

create table maintainance(maintain_n varchar(10) primary key,maintain_type varchar(20),maintain_date date,coach_n varchar(10),foreign key(coach_no) references coaches(coach_n));

create table coaches(coach_n varchar(10) primary key,manufacturer varchar(50),last_maintained date,mileage int);


create table active_coaches(coach_n varchar(10) primary key,train_n int,foreign key(train_n) references trains(train_n));


insert statements:-

INSERT INTO active_coaches
(`coach_n`,
`train_n`)
VALUES

INSERT INTO coaches
(`coach_n`,
`manufacturer`,
`last_maintained`,
`mileage`) VALUES


INSERT INTo routes
(`route_n`,
`route_name`,
`time_taken`,
`total_dist_km`,
`start_stn`,
`start_time`,
`end_stn`,
`end_time`)
VALUES

INSERT INTO maintainance
(`maintain_n`,
`maintain_type`,
`maintain_date`,
`coach_n`)
VALUES


INSERT INTO seats
(`seat_no`,
`type`)
VALUES


INSERT INTO staff_schedule
(`route_n`,
`train_n`,
`staff_n`,
`remark`,
`date`,
`time`,
`accomodation`)
VALUES



INSERT INTO staffs
(`staff_n`,
`staff_name`,
`contact_n`,
`residence_city`)
VALUES



INSERT INTO standby_coaches
(`coach_n`,
`Date`)
VALUES



INSERT INTO stations
(`station_code`,
`station_name`,
`no_of_platform`,
`state`)
VALUES



INSERT INTO stations
(`station_code`,
`station_name`,
`no_of_platform`,
`state`)
VALUES



INSERT INTO stations
(`station_code`,
`station_name`,
`no_of_platform`,
`state`)
VALUES


INSERT INTO stations
(`station_code`,
`station_name`,
`no_of_platform`,
`state`)
VALUES


INSERT INTO stations
(`station_code`,
`station_name`,
`no_of_platform`,
`state`)
VALUES


