# intercity-express-dbms
contribution

MOHIT MADAVI: ER DIAGRAM,RELATIONAL SCHEMA, INSERT DATA INTO TABLES


DHARMESH JAIN:ER DIAGRAM,RELATIONAL SCHEMA, INSERT DATA INTO TABLES


ASHWIN CHOUDHARY:COLLECTION OF DATA




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
