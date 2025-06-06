# Student-management-system-
class Student:
    def __init__(self, roll, name, age, marks):
        self.roll = roll
        self.name = name
        self.age = age
        self.marks = marks

    def __str__(self):
        return f"Roll: {self.roll}, Name: {self.name}, Age: {self.age}, Marks: {self.marks}"


class StudentManagementSystem:
    def __init__(self):
        self.students = []

    def add_student(self):
        roll = input("Enter Roll Number: ")
        name = input("Enter Name: ")
        age = int(input("Enter Age: "))
        marks = float(input("Enter Marks: "))
        self.students.append(Student(roll, name, age, marks))
        print("Student added successfully!\n")

    def display_students(self):
        if not self.students:
            print("No students to display.")
        else:
            print("\nStudent List:")
            for student in self.students:
                print(student)
        print()

    def search_student(self):
        roll = input("Enter Roll Number to search: ")
        for student in self.students:
            if student.roll == roll:
                print("Student Found:\n", student)
                return
        print("Student not found.\n")

    def delete_student(self):
        roll = input("Enter Roll Number to delete: ")
        for student in self.students:
            if student.roll == roll:
                self.students.remove(student)
                print("Student deleted successfully!\n")
                return
        print("Student not found.\n")

    def update_student(self):
        roll = input("Enter Roll Number to update: ")
        for student in self.students:
            if student.roll == roll:
                student.name = input("Enter New Name: ")
                student.age = int(input("Enter New Age: "))
                student.marks = float(input("Enter New Marks: "))
                print("Student updated successfully!\n")
                return
        print("Student not found.\n")

    def run(self):
        while True:
            print("======= Student Management System =======")
            print("1. Add Student")
            print("2. View All Students")
            print("3. Search Student by Roll Number")
            print("4. Delete Student")
            print("5. Update Student")
            print("6. Exit")

            choice = input("Enter your choice (1-6): ")

            if choice == '1':
                self.add_student()
            elif choice == '2':
                self.display_students()
            elif choice == '3':
                self.search_student()
            elif choice == '4':
                self.delete_student()
            elif choice == '5':
                self.update_student()
            elif choice == '6':
                print("Exiting... Goodbye!")
                break
            else:
                print("Invalid choice! Please try again.\n")


if __name__ == "__main__":
    sms = StudentManagementSystem()
    sms.run()
