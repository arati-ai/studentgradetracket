def get_letter_grade(average):
    """Convert numeric average to a letter grade."""
    if average >= 90:
        return 'A'
    elif average >= 80:
        return 'B'
    elif average >= 70:
        return 'C'
    elif average >= 60:
        return 'D'
    else:
        return 'F'

def get_gpa(average):
    """Convert numeric average to a GPA (on a 4.0 scale)."""
    if average >= 90:
        return 4.0
    elif average >= 80:
        return 3.0
    elif average >= 70:
        return 2.0
    elif average >= 60:
        return 1.0
    else:
        return 0.0

def main():
    grades = {}  # Dictionary to store grades for each subject
    print("Student Grades Tracker\n")
    while True:
        subject = input("Enter the subject or assignment name (or 'done' to finish): ")
        if subject.lower() == 'done':
            break
        try:
            grade = float(input(f"Enter the grade for {subject}: "))
            grades[subject] = grade
        except ValueError:
            print("Invalid input! Please enter a numeric grade.")
            continue
    if grades:
        average_grade = sum(grades.values()) / len(grades)
        letter_grade = get_letter_grade(average_grade)
        gpa = get_gpa(average_grade)
        print("\nGrades Summary:")
        for subject, grade in grades.items():
            print(f"{subject}: {grade}")
        print(f"\nAverage Grade: {average_grade:.2f}")
        print(f"Letter Grade: {letter_grade}")
        print(f"GPA: {gpa:.1f}")
    else:
        print("No grades were entered.")

# Run the program
main()
