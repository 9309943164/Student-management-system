# Student-management-system
from flask import Flask, render_template, request, redirect, url_for

app = Flask(__name__)

# In-memory database for demonstration purposes
students = []

def index():
    return render_template('index.html')
    ('/add_student', methods=['GET', 'POST'])
def add_student():
    if request.method == 'POST':
        name = request.form.get('name')
        age = request.form.get('age')
        student_id = len(students) + 1
        students.append({'id': student_id, 'name': name, 'age': age})
        return redirect(url_for('view_students'))
    return render_template('add_student.html')

('/view_students')
def view_students():
    return render_template('view_students.html', students=students)

if __name__ == '__main__':
    app.run(debug=True)
