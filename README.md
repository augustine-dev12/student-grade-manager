print("=== Student Grade Manager ===")

students = []

num_students = int(input("How many students do you want to enter? "))

for i in range(num_students):
    print(f"\nStudent {i+1}")

    name = input("Enter student name: ")
    score = float(input("Enter score (0-100): "))

    students.append({
        "name": name,
        "score": score
    })

def get_grade(score):
    if score >= 70:
        return "A"
    elif score >= 60:
        return "B"
    elif score >= 50:
        return "C"
    elif score >= 45:
        return "D"
    else:
        return "F"

print("\n=== RESULTS ===")

total = 0

for student in students:
    grade = get_grade(student["score"])
    total += student["score"]

    print(f"{student['name']} - Score: {student['score']} - Grade: {grade}")

average = total / len(students)

print("\n=== SUMMARY ===")
print("Total Students:", len(students))
print("Class Average:", round(average, 2))
