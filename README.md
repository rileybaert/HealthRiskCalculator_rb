# HealthRiskCalculator_rb

# Project Creator: Riley Baert
# Email: Rileyabaert@Lewisu.edu
# Credits: Amaan Marfatia (BMI related weights/calculations/formulas)
           Shannon Rothe (Functions relating to exiting the program)
# No files are required outside of the program itself, it is designed to run in Python 3
# Open the application in terminal anf follow the on-screen instructions to utilize the program

# Riley Baert
# Health Risk Calculator 1.0

#Constants
INTRODUCTION = '''
----------------------------------------
    Health Insurance Risk Calculator
            Riley A. Baert
            CPSC-20000-003
----------------------------------------
This program is designed to determine the risks
associated with new insurance patients based
on their health statuses and histories. Input 
patient data below and the risk associated 
with insuring them will be calculated.

'''
QUESTION = [
    'What is the height of the patient in inches?',
    'What is the weight of the patient in pounds?',
    'What is the age of the patient?',
    'What is the systolic blood pressure of the patient?',
    'What is the diastolic blood pressure of the patient?',
    'Does the patient have a family history of diabetes? (Enter 1 for no, 2 for yes)',
    'Does the patient have a family history of cancer? (Enter 1 for no, 2 for yes)',
    'Does the patient have a family history of Alzheimers (Enter 1 for no, 2 for yes)?',
]


print(INTRODUCTION)

response = []
score = []

#Lines 36-48 calculate the Body Mass Index of the patient
patientHeight = 0.0254 * int(input("What is the patient's height in inches?"))
patientWeight = 0.4536 * int(input("What is the patient's weight in pounds?"))

BMI = round(patientWeight/(patientHeight*patientHeight), 1)
if BMI <=18.5:
    score1 = 0
elif BMI <=24.9:
    score1 = 0 
elif BMI <=29.9:
    score1= 30
else:
    score2= 75
print("BMI risk out of a possible 75 points (with 75 being the highest risk): " +str(score1))

# Calculates the risks associated with patient age
userResponse3 = int(input(QUESTION[2]))
if userResponse3 in range (0,30):
    score2 = 0
if userResponse3 in range (30,45):
    score2 = 10
if userResponse3 in range (45, 66):
    score2 = 20
if userResponse3 >65:
    score2 = 30    
if userResponse3 in range (0, 150):
    pass
else:
    print("Sorry! Please pick an appropriate numerical value")
    userResponse3 = int(input(QUESTION[2]))
print("Age risk out of a possible 30 points (with 30 being the highest risk): " + str(score2))
print("")

# Calculates the risk associated with the patient's systolic blood pressure 
userResponse4 = int(input(QUESTION[3]))
if userResponse4 in range (0, 120):
    score3 = 0
if userResponse4 in range (120, 130):
    score3 = 7.5
if userResponse4 in range (130, 140):
    score3 = 15
if userResponse4 in range (140, 180):
    score3 = 37.5
if userResponse4 >180:
    score3 = 50
if userResponse4 in range (0, 180):
    pass
else:
    print("Sorry! Please pick an appropriate numerical value")
    userResponse4 = int(input(QUESTION[3]))
print("Systolic blood pressure risk out of a possible 50 points (with 50 being the highest risk): " + str(score3))
print("")

# Calculates the risk associated with the patient's diastolic blood pressure 
userResponse5 = int(input(QUESTION[4]))
if userResponse5 in range (0, 80):
    score4 = 0
if userResponse5 in range (80, 90):
    score4 = 15
if userResponse5 in range (90, 121):
    score4 = 37.5
if userResponse5 in range (121, 175):
    score4 = 50
if userResponse5 in range (0, 175):
    pass
else:
    print("Sorry! Please pick an appropriate numerical value")
    userResponse5 = int(input(QUESTION[4]))
print("Diastolic blood pressure risk out of a possible 50 points (with 50 being the highest risk): " + str(score4))
print("")

#Calculates family risk of diabetes
userResponse6 = int(input(QUESTION[5]))
if userResponse6 in range (1, 2):
    score5 = 0
if userResponse6 in range (2, 3):
    score5 = 10
if userResponse6 in range (1, 3):
    pass
else:
    print("Sorry! Please pick an appropriate numerical value")
    userResponse6 = int(input(QUESTION[5]))
print("Risk of diabetes -- based on family history -- out of a possible 10 points (with 10 being the highest risk): " + str(score5))
print("")

#Calculates family risk of cancer
userResponse7 = int(input(QUESTION[6]))
if userResponse7 in range (1, 2):
    score6 = 0
if userResponse7 in range (2, 3):
    score6 = 10
if userResponse7 in range (1, 3):
    pass
else:
    print("Sorry! Please pick an appropriate numerical value")
    userResponse7 = int(input(QUESTION[6]))
print("Risk of cancer -- based on family history -- out of a possible 10 points (with 10 being the highest risk): " + str(score6))
print("")

#Calculates family risk of Alzheimer's
userResponse8 = int(input(QUESTION[7]))
if userResponse8 in range (1, 2):
    score7 = 0
if userResponse8 in range (2, 3):
    score7 = 10
if userResponse8 in range (1, 3):
    pass
else:
    print("Sorry! Please pick an appropriate numerical value")
    userResponse8 = int(input(QUESTION[8]))
print("Risk of Alzheimer's -- based on family history -- out of a poissible 10 points (with 10 being the highest risk): " + str(score7))
print("")

#Calculates total score
totalScore = (score1 + score2 + score3 + score4 + score5 + score6+ score7)
print("Total Score: " + str(totalScore))
print("")

#Determines how insurable the patient is
if totalScore in range(0, 21):
    print("Low Risk")
if totalScore in range(21, 51):
    print("Moderate Risk")
if totalScore in range(51,76):
    print("High Risk")
if totalScore >75:
    print("Uninsurable")

#Closes the program
print("Type 'enter' to close the program")
user_input = input()
if user_input == "end":
    exit
