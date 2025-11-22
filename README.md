# Mental-stress-Detection-Fundamentals-of-AI-ML-
Mental-stress Detection is a simple python code that analyzes daily lifestyles habits to estimate a person's stress level. It calculates a stress score and classifies the person's mental stress as Low,Medium and High based on factors such as sleep duration, screen time , exercise routine and workload.

Problem statement-:
With increasing academic pressure,lifestyle imbalance and long screen usage, many of us experience mental stress without realzing it.This project is aims to estimate mental stress based on daily habits.

Objectives-:
1.To collect lifestyle related inputs from the user.
2.To classify the person's mental stress level.

Features-:
1.Takes four key inputs:sleep hours,screen time , exercise and workload
2.Calculates stress score using rule-based logic.
3.Predict stress category.

Flowchart-:
       ┌──────────────────────┐
       │   Start Program      │
       └──────────┬───────────┘
                  │
        ┌─────────▼─────────┐
        │  Take User Inputs │
        └─────────┬─────────┘
                  │
        ┌─────────▼─────────┐
        │  Calculate Score  │
        └─────────┬─────────┘
                  │
        ┌─────────▼─────────┐
        │ Classify Stress   │
        └─────────┬─────────┘
                  │
       ┌──────────▼───────────┐
       │ Display Final Result │
       └──────────┬───────────┘
                  │
             ┌────▼────┐
             │  End    │
             └─────────┘

Algorithm-:
1.Start the program.
2. Ask the user for the following inputs:
Sleep hours per day
Screen time per day
Daily exercise (minutes)
Workload level (low/medium/high)
3. Initialize a stress score to 0.
4. Add to the stress score based on habits:
Less sleep → higher score
More screen time → higher score
Less exercise → higher score
Heavy workload → higher score
5. If score ≤ 2 → Low Stress.
6. Elif score ≤ 4 → Moderate Stress.
7. Else → High Stress.
8. Display stress level.
9. End the program.

Python Code-:
# Mental Stress Detection Using Lifestyle Data
def predict_stress(sleep_hours, screen_time, exercise, workload):
    score = 0
    # Less sleep increases stress
    if sleep_hours < 6:
        score += 2
    elif sleep_hours < 8:
        score += 1
    # High screen time increases stress
    if screen_time > 6:
        score += 2
    elif screen_time > 3:
        score += 1
    # No exercise increases stress
    if exercise == 0:
        score += 2
    elif exercise < 30:
        score += 1
    # Heavy workload increases stress
    if workload == "high":
        score += 2
    elif workload == "medium":
        score += 1
    # Predict stress level
    if score <= 2:
        return "Low Stress"
    elif score <= 4:
        return "Moderate Stress"
    else:
        return "High Stress"
print(" Mental Stress Detection System")
sleep = float(input("Average sleep (hours per day): "))
screen_time = float(input("Average screen time (hours per day): "))
exercise = float(input("Daily exercise (minutes): "))
workload = input("Workload (low/medium/high): ").lower()
stress = predict_stress(sleep, screen_time, exercise, workload)
print("Predicted Stress Level:", stress)

Output-:
Mental Stress Detection System
Average sleep (hours per day): 7
Average screen time (hours per day): 2
Daily exercise (minutes): 60
Workload (low/medium/high): high
Predicted Stress Level: Moderate Stress
PS C:\Users\Hp\OneDrive\PYTHON> 


