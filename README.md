# python-project- 
# Student Performance Analyzer without OOP

# Function to calculate total and average marks
def calculate_total_and_average(marks):
    total = sum(marks)
    average = total / len(marks)
    return total, average

# Function to calculate grade based on average marks
def calculate_grade(average):
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

# Function to input student data and analyze performance
def input_student_data():
    students = []
    num_students = int(input("Enter the number of students: "))

    for i in range(num_students):
        student = {}
        student['name'] = input(f"Enter name of student {i + 1}: ")
        num_subjects = int(input(f"Enter number of subjects for {student['name']}: "))
        
        marks = []
        for j in range(num_subjects):
            mark = float(input(f"Enter marks for subject {j + 1}: "))
            marks.append(mark)
        
        student['marks'] = marks
        total, average = calculate_total_and_average(marks)
        student['total'] = total
        student['average'] = average
        student['grade'] = calculate_grade(average)

        students.append(student)
    
    return students

# Function to display student performance
def display_student_performance(students):
    print("\n--- Student Performance Report ---")
    for student in students:
        print(f"\nName: {student['name']}")
        print(f"Total Marks: {student['total']}")
        print(f"Average Marks: {student['average']:.2f}")
        print(f"Grade: {student['grade']}")

# Main function to run the Student Performance Analyzer
def main():
    students = input_student_data()
    display_student_performance(students)

if __name__ == "__main__":
    main()
