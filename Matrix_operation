import tkinter as tk
from tkinter import messagebox
import numpy as np

def get_matrix(entry):
    try:
        return np.array([[float(num) for num in row.split()] for row in entry.get("1.0", tk.END).strip().split("\n")])
    except ValueError:
        messagebox.showerror("Input Error", "Please enter valid numerical values in matrix format.")
        return None

def display_result(result):
    result_text.delete("1.0", tk.END)
    result_text.insert(tk.END, str(result))

def add_matrices():
    matrix1 = get_matrix(matrix1_entry)
    matrix2 = get_matrix(matrix2_entry)
    if matrix1 is not None and matrix2 is not None:
        try:
            result = np.add(matrix1, matrix2)
            display_result(result)
        except ValueError:
            messagebox.showerror("Operation Error", "Matrices must have the same dimensions for addition.")

def subtract_matrices():
    matrix1 = get_matrix(matrix1_entry)
    matrix2 = get_matrix(matrix2_entry)
    if matrix1 is not None and matrix2 is not None:
        try:
            result = np.subtract(matrix1, matrix2)
            display_result(result)
        except ValueError:
            messagebox.showerror("Operation Error", "Matrices must have the same dimensions for subtraction.")

def multiply_matrices():
    matrix1 = get_matrix(matrix1_entry)
    matrix2 = get_matrix(matrix2_entry)
    if matrix1 is not None and matrix2 is not None:
        try:
            result = np.dot(matrix1, matrix2)
            display_result(result)
        except ValueError:
            messagebox.showerror("Operation Error", "Matrix multiplication requires valid dimensions.")

def transpose_matrix():
    matrix1 = get_matrix(matrix1_entry)
    if matrix1 is not None:
        result = np.transpose(matrix1)
        display_result(result)

def determinant_matrix():
    matrix1 = get_matrix(matrix1_entry)
    if matrix1 is not None:
        if matrix1.shape[0] == matrix1.shape[1]:
            result = np.linalg.det(matrix1)
            display_result(result)
        else:
            messagebox.showerror("Operation Error", "Determinant can only be calculated for square matrices.")

app = tk.Tk()
app.title("Matrix Operations Tool")

tk.Label(app, text="Matrix 1").pack()
matrix1_entry = tk.Text(app, height=5, width=30)
matrix1_entry.pack()

tk.Label(app, text="Matrix 2").pack()
matrix2_entry = tk.Text(app, height=5, width=30)
matrix2_entry.pack()

tk.Button(app, text="Add", command=add_matrices).pack()
tk.Button(app, text="Subtract", command=subtract_matrices).pack()
tk.Button(app, text="Multiply", command=multiply_matrices).pack()
tk.Button(app, text="Transpose Matrix 1", command=transpose_matrix).pack()
tk.Button(app, text="Determinant of Matrix 1", command=determinant_matrix).pack()

tk.Label(app, text="Result").pack()
result_text = tk.Text(app, height=5, width=30)
result_text.pack()

app.mainloop()
