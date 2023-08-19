import tkinter as tk

calculation = ''

def add_calculation(symbol):
    global calculation
    calculation += str(symbol)
    result_text.delete(1.0 , "end")
    result_text.insert(1.0 , calculation)

def evaluate_calculation():
    global calculation
    print(calculation)
    try: 
       result = str(eval(calculation))
       calculation = ''
       result_text.delete(1.0 , "end")
       result_text.insert(1.0 , result)
    except:
        clar_field()
        result_text.insert(1.0 , "Error")

def clear_field():
    global calculation
    calculation = ""
    result_text.delete(1.0 , "end")

root = tk.Tk()
root.geometry("230x200")
root.config(bg = 'gray')
result_text = tk.Text(root, height = 1, width = 20, font=('cambia',15))
result_text.grid(columnspan=5)

button_1 = tk.Button(root , text = "1", command = lambda: add_calculation(1), width = 5 , font = ('cambia',10))
button_1.grid(row = 2, column = 1, pady = 2)
button_2 = tk.Button(root , text = "2", command = lambda: add_calculation(2), width = 5 , font = ('cambia',10))
button_2.grid(row = 2, column = 2, pady = 2)
button_3 = tk.Button(root , text = "3", command = lambda: add_calculation(3), width = 5 , font = ('cambia',10))
button_3.grid(row = 2, column = 3, pady = 2)
button_4 = tk.Button(root , text = "4", command = lambda: add_calculation(4), width = 5 , font = ('cambia',10))
button_4.grid(row = 3, column = 1, pady = 2)
button_5 = tk.Button(root , text = "5", command = lambda: add_calculation(5), width = 5 , font = ('cambia',10))
button_5.grid(row = 3, column = 2, pady = 2)
button_6 = tk.Button(root , text = "6", command = lambda: add_calculation(6), width = 5 , font = ('cambia',10))
button_6.grid(row = 3, column = 3, pady = 2)
button_7 = tk.Button(root , text = "7", command = lambda: add_calculation(7), width = 5 , font = ('cambia',10))
button_7.grid(row = 4, column = 1, pady = 2)
button_8 = tk.Button(root , text = "8", command = lambda: add_calculation(8), width = 5 , font = ('cambia',10))
button_8.grid(row = 4, column = 2, pady = 2)
button_9 = tk.Button(root , text = "9", command = lambda: add_calculation(9), width = 5 , font = ('cambia',10))
button_9.grid(row = 4, column = 3, pady = 2)
button_0 = tk.Button(root , text = "0", command = lambda: add_calculation(0), width = 5 , font = ('cambia',10))
button_0.grid(row = 5, column = 2, pady = 2)
button_plus = tk.Button(root , text = "+", command = lambda: add_calculation("+"), width = 3 , font = ('cambia',10))
button_plus.grid(row = 2, column = 4, pady = 2)
button_minus = tk.Button(root , text = "-", command = lambda: add_calculation("-"), width = 3 , font = ('cambia',10))
button_minus.grid(row = 3, column = 4, pady = 2)
button_multi = tk.Button(root , text = "*", command = lambda: add_calculation("*"), width = 3 , font = ('cambia',10))
button_multi.grid(row = 4, column = 4, pady = 2)
button_divide = tk.Button(root , text = "/", command = lambda: add_calculation("/"), width = 3 , font = ('cambia',10))
button_divide.grid(row = 5, column = 4, pady = 2)
button_clear = tk.Button(root , text = "C", command = clear_field, width = 5 , font = ('cambia',10))
button_clear.grid(row = 5, column = 1, pady = 2)
button_equalsto = tk.Button(root , text = "=", command = evaluate_calculation, width = 5 , font = ('cambia',10))
button_equalsto.grid(row = 5, column = 3, pady = 2)

root.mainloop()
