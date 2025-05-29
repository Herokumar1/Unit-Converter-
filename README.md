import tkinter as tk

def convert():
    choice = var.get()
    value = float(entry.get())
    result = ""
    
    if choice == "Km to Miles":
        result = f"{value} km = {round(value * 0.621371, 2)} miles"
    elif choice == "Celsius to Fahrenheit":
        result = f"{value}°C = {round((value * 9/5) + 32, 2)}°F"
    elif choice == "Kg to Pounds":
        result = f"{value} kg = {round(value * 2.20462, 2)} lbs"

    output.config(text=result)

# GUI App
root = tk.Tk()
root.title("Simple Unit Converter")
root.geometry("300x200")

tk.Label(root, text="Enter value:").pack()
entry = tk.Entry(root)
entry.pack()

var = tk.StringVar(root)
var.set("Km to Miles")
options = ["Km to Miles", "Celsius to Fahrenheit", "Kg to Pounds"]
tk.OptionMenu(root, var, *options).pack()

tk.Button(root, text="Convert", command=convert).pack()
output = tk.Label(root, text="")
output.pack()

root.mainloop()