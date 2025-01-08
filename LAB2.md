import tkinter as tk
from tkinter import messagebox

def calculate():
    try:
        n = int(entry_number.get())
        nn = int(f"{n}{n}")
        nnn = int(f"{n}{n}{n}")
        result = n + nn + nnn
        result_label.config(text=f"Result: {result}")
    except ValueError:
        messagebox.showerror("Input Error", "Please enter a valid integer.")
root = tk.Tk()
root.title("N + NN + NNN Calculator")
root.attributes('-fullscreen', True)
root.configure(bg="lightgray")
header_label = tk.Label(root, text="N + NN + NNN Calculator", font=("Helvetica", 24, "bold"), bg="darkblue", fg="white")
header_label.pack(fill=tk.X, pady=10)
label_number = tk.Label(root, text="Enter an integer:", font=("Helvetica", 16), bg="lightgray")
label_number.pack(pady=20)
entry_number = tk.Entry(root, font=("Helvetica", 14))
entry_number.pack(pady=10)
calculate_button = tk.Button(root, text="Calculate", font=("Helvetica", 14), command=calculate, bg="darkblue", fg="white")
calculate_button.pack(pady=20)
result_label = tk.Label(root, text="Result: ", font=("Helvetica", 16), bg="lightblue", borderwidth=2, relief="solid")
result_label.place(relx=0.5, rely=0.6, anchor="center")
exit_button = tk.Button(root, text="Exit", font=("Helvetica", 14), command=root.destroy, bg="red", fg="white")
exit_button.pack(side=tk.BOTTOM, pady=20)
root.mainloop()
