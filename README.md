# Embedded-Systems-Lab-4
A program to measure the voltage values of an analog input pin using a potentiometer and an ADC; watchdog timer reset included


Lab Document below:

ECE 487/587 Spring 2020
Laboratory 4 – Introduction to Analog-to-Digital Converters

1.	Introduction
This particular laboratory exercise is designed to introduce you to the use of analog-to-digital converters.  

2.	Requirements
In addition to your Arduino platform and computer, you will also need the following for this lab:
•	Solderless breadboard
•	10k ohm potentiometer (other values can also work)
•	Wires for use with breadboard

3.	Laboratory Tasks
You are to create a new application that will execute on your Arduino platform.  Your application will repeatedly convert an analog voltage connected to analog pin A0 to its corresponding digital value.  Your code is required to perform the conversion using the analogRead function, and the time required for each conversion and the resulting digital value from the conversion must be displayed to the screen using the serial monitor.  

The analog signal to be converted is a voltage from 0 to +5V that is adjustable via the potentiometer.  Be careful with analog values > 5.0 V as they can damage the ADC.  

Upon power up or reset, your code will start by displaying a reset message.  Then, it will display a prompt to the screen asking the user for a ‘c’ to start a set of conversions.  When the user enters a ‘c’, your program should display a message to the screen that a series of 30 measurements is about to begin.  Your code should then convert the analog input 30 times (make sure you are waiting long enough between conversions).  For each conversion, your code should display the number of the conversion, the resulting digital value (in hexadecimal), and the required conversion time.  After the 30th conversion is complete, the average time required for the 30 conversions should be displayed and the program should prompt the user to begin another set of conversions.  

The only valid user input at the prompt is ‘c’.  All other user inputs are considered erroneous and should be accounted for appropriately.  All user inputs entered during a set of conversions should be ignored.  

All user inputs (valid and invalid) should reset a watchdog timer.  If the user does not provide any inputs within 4 seconds, the watchdog timer should expire and the board should reset.  The timeout period should begin upon prompt to the user for input.  Students are required to use the hardware watchdog timer for this assignment. 

Sample program output:
Board was reset
Enter ‘c’ to start a set of conversions > (user enters ‘c’)
Starting a set of conversions:
#1:  	digital value = 3FF   	Time = 120 usecs	(all user inputs during 
#2:  	digital value = 3A0  	Time = 118 usecs	conversions are ignored)
…
#30: 	digital value = 000	Time = 120 usecs

avg conversion time = 120.00 usecs

Enter ‘c’ to start a set of conversions > (user enters ‘x’)
Error: invalid user input – the only valid user input is ‘c’
Enter ‘c’ to start a set of conversions > (user enters nothing for > 4 seconds)

Board was reset

Enter ‘c’ to start a set of conversions > 

4.	Grading
Due Date:  02/28/2020
No late assignments will be accepted.  This is an individual assignment.

All students must demo/explain their project in the lab (SERC 2005) to the TA, Ben Sawyer, by the deadline.  The assignment will be graded at the time of the demo.  There will be no re-submissions (for each lab attempt), so all debugging is the responsibility of the student (the TA doesn’t have time to help you debug your code!).  Each student will have to sign up for a grading/demo time, and the assigned time is the grading/demo time! No exceptions. Arrive a few minutes early to get set up and get ready for your demo time to begin. We want to stay on schedule, so be ready to go when your time starts. If you miss your demo time, you will receive a grade of zero for the lab attempt, and you will have to resubmit. The signup sheet will be posted in SERC 2005 the week before the lab is due. The TA will schedule all grading activities according to the signup sheet. The TA is not able to schedule independent times outside of those posted on the signup sheet. 

You must turn in a hardcopy of your program during your demo with the grading sheet attached as page 1.  The hardcopy of your code should match the code that is being executed!  If it does not match, your grade for the lab will be zero.  Your code should have a header comment indicating your name, CWID, lab assignment, and other pertinent info. I encourage you to print your code so as to preserve your formatting, which will be considered as part of the “programming practices” grade.  

I encourage all students to PLAN AHEAD regarding deadlines.  Deadlines are LIMITS not GOALS! All students should plan to get their assignments done with time to spare to avoid missing the deadline and to get a demo time.  You may need to be flexible when trying to get a demo time. Deadlines are judged based upon when the assignment is demoed (i.e. graded), not when a student says he/she is finished.  If the assignment is not graded by the deadline, it will not be accepted and the student will receive a zero for that lab attempt.  

Grading Guidelines that will be used for Lab #4:

Good Programming Practices:
1)	Comments
2)	Indentation
3)	Good/meaningful variable names
4)	Minimum/wise usage of global variables; unnecessary use of variables
5)	Inefficient code

Grade Breakdown:
30 pts – Good programming practices
70 pts – Functionality/Oral description of hardware and code
