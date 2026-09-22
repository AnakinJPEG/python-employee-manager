import json

def add_employee(employees, name, dpt, salary):
    """Adds an employee to the list"""
    employee = {"name":name,
                "dpt": dpt,
                "salary": salary
                }
    employees.append(employee)




def view_employees(employees):
    """Prints all employees"""
    print(employees)


def find_employee(employees, name):
    """Returns employee dict or None"""
    found = False
    for employee in employees:
        if name == employee["name"]:
            found = True
            print(f"Your employee: {employee}")
    if not found:
        print("Employee was unfound!")


def update_salary(employees, name, new_salary):
    """Updates an employee's salary"""
    found = False
    for employee in employees:
        if employee["name"] == name:
            found = True
            employee["salary"] = new_salary
            print(f"Your new employee stats: {employee}")
    if not found:
        print("Employee was unfound!")


def delete_employee(employees, name):
    """Removes an employee"""
    found = False
    for employee in employees:
        if name == employee["name"]:
            employees.remove(employee)
            found = True
            print(f"Employee {employee['name']} was removed")
            break
    if not found:
        print("Employee was unfound!")


def department_summary(employees, dpt):
    """Shows count and total salary per department"""
    emp_count = 0
    total_salary = 0

    for employee in employees:
        if employee["dpt"] == dpt:
            emp_count += 1
            total_salary += employee["salary"]
    print(f"The employee count is {emp_count}")
    print(f"The total salary of this department is {total_salary}")


def save_employees(employees, filename):
    """Saves to JSON"""
    with open(filename, "w") as f:
        json.dump(employees, f, indent= 6)


def load_employees(filename):
    """Loads from JSON"""
    try:
        with open(filename, "r") as f:
            return json.load(f)
    except FileNotFoundError:
        return []


def main():

    filename = "employee-data.json"
    employees = load_employees(filename)

    print("""=== EMPLOYEE MANAGEMENT SYSTEM ===
    1. Add Employee
    2. View All Employees
    3. Find Employee
    4. Update Salary
    5. Delete Employee
    6. Department Summary
    7. Load Employees From .json
    8. Exit""")

    while True:

        path = int(input("Choose a path"))

        if path == 8:
            save_employees(employees, filename)
            print("bye")
            break

        if path == 1:
            name = input("Enter a name: ")
            dpt = input("Enter a department: ")
            salary = float(input("Desired salary: "))
            add_employee(employees, name, dpt, salary)

        elif path == 2:
            view_employees(employees)

        elif path == 3:
            name = input("Enter a name: ")
            find_employee(employees, name)

        elif path == 4:
            name = input("Enter a name: ")
            new_salary = float(input("New salary: "))
            update_salary(employees, name, new_salary)

        elif path == 5:
            name = input("Enter a name: ")
            delete_employee(employees, name)

        elif path == 6:
            dpt = input("Select a department for analysis: ")
            department_summary(employees, dpt)

        elif path == 7:
            print(load_employees(filename))

main()
