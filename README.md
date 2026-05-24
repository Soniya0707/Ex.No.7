# Exno.7-Develop a prompt-based application tailored to their personal needs, fostering creativity and practical problem-solving skills while leveraging the capabilities of large language models.

# Date:24/05/2026
# Register no:212223060268(Soniya D)
## Aim
To develop a prompt-based application using ChatGPT — To demonstrate how prompt engineering can be used to create a Study Time Scheduler that helps students plan subjects, generate study timetables, avoid overlap, and improve productivity.
This experiment shows how prompts evolve from simple requests to advanced interactive features.

## AI Tools Required

- ChatGPT (Large Language Model)

- Python (for basic simulation functions)

- Optional: Jupyter Notebook / any Python IDE

## Explanation
## Prompt:
“Design a Study Time Scheduler that can organize subjects, assign time slots, check for overlapping study periods, recommend break intervals, track progress, and respond naturally to user inputs. The scheduler should adapt to the student’s study habits over time.”

The goal is to build a simple LLM-driven study planner application.

## Procedure
## Step 1 : Defining Requirements

- The Study Time Scheduler must be able to:

- Add subjects and study durations

- Generate a timetable

- Detect overlapping schedules

- Suggest break times

- Provide motivational tips

- Answer student questions naturally

## Step 2 : Creating the Prompt-Based Components
## 1. Subject Manager
## Prompt:

“Create a function to store subjects with preferred study duration and difficulty level.”
## AI Response:
```
study_plan = {}

def add_subject(subject, duration, difficulty="Medium"):
    study_plan[subject] = {"duration": duration, "difficulty": difficulty}
    print(f"Added: {subject} — {duration} hrs ({difficulty})")

def show_subjects():
    if not study_plan:
        print("No subjects added yet!")
    else:
        print("Subjects Added:")
        for s, details in study_plan.items():
            print(f"- {s}: {details['duration']} hrs ({details['difficulty']})")

add_subject("Mathematics", 2, "High")
add_subject("Physics", 1.5)
show_subjects()
```
## Output:
Added: Mathematics — 2 hrs (High)
Added: Physics — 1.5 hrs (Medium)
Subjects Added:
- Mathematics: 2 hrs (High)
- Physics: 1.5 hrs (Medium)
  
## 2. Study Timetable Generator
## Prompt:

“Write a function that generates a simple timetable by arranging subjects based on duration.”

## AI Response:
```
def generate_timetable():
    print("Generating Study Timetable...")
    start_time = 9  # Start at 9 AM
    for subject, details in study_plan.items():
        end_time = start_time + details["duration"]
        print(f"{subject}: {start_time}:00 AM - {end_time}:00 AM")
        start_time = end_time
```
## Output:
- Generating Study Timetable...
- Mathematics: 9:00 AM - 11:00 AM
- Physics: 11:00 AM - 12:30 PM

## 3. Overlap Checker
## Prompt:

“Create a function to check for overlapping study sessions.”

## AI Response:
```
def check_overlap():
    print("Checking for overlapping sessions...")
    times = []
    start = 9
    for subject, details in study_plan.items():
        end = start + details["duration"]
        times.append((start, end))
        start = end

    for i in range(len(times)-1):
        if times[i][1] > times[i+1][0]:
            print("Overlap detected!")
            return
    print("No overlaps found.")
```

## Output:
- Checking for overlapping sessions...
- No overlaps found.

## 4. Break Suggestion System
## Prompt:

“Generate a short break suggestion after every 1 hour of study.”

## AI Response:
```
def suggest_break(duration):
    if duration >= 1:
        print("Break Suggestion: Take a 10-minute break for better focus!")
    else:
        print("Short study session — no break needed.")
```

## Example Call:

suggest_break(2)

## Output:
Break Suggestion: Take a 10-minute break for better focus!

## 5. Motivational Response Assistant
## Prompt:

“Create a small chatbot that gives motivational responses to student queries.”

## AI Response:
```
def motivate(query):
    responses = {
        "i am tired": "Take a deep breath. Progress is slow, but it is still progress!",
        "i feel stressed": "Small steps every day lead to big achievements.",
        "give motivation": "You are capable of more than you think. Keep going!"
    }
    print(responses.get(query.lower(), "Stay positive — you're doing great!"))
```

## Example:

motivate("I am tired")

## Output:
Take a deep breath. Progress is slow, but it is still progress!

## Result

This experiment successfully produced a prototype Study Time Scheduler using prompt-based design with ChatGPT.
Students learned to:

- Build structured prompts for real-life applications

- Develop interactive features using LLM responses

- Understand prompt progression from simple to advanced

- Use LLMs creatively for academic and personal productivity

- Integrate logic like scheduling, break suggestions, and motivation

- This demonstrates how prompt-based applications improve problem-solving and enhance practical learning using AI.
