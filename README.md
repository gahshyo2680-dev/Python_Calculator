# Calculator # 
from tkinter import Tk, Entry, Button, Label, messagebox

def process():
    try:
        op = process_button.get().strip()
        
        num1 = float(n1.get())
        num2 = float(n2.get())
        
        if op == "+":
            final = num1 + num2
            empty_label3.config(text=f"Your Answer is: {final}")
        elif op == "-":
            final = num1 - num2
            empty_label3.config(text=f"Your Answer is: {final}")
        elif op == "*":
            final = num1 * num2
            empty_label3.config(text=f"Your Answer is: {final}")
        elif op == "/":
            if num2 == 0:
                messagebox.showerror("Error", "Cannot divide by zero!")
                return
            final = num1 / num2
            empty_label3.config(text=f"Your Answer is: {final}")
        else:
            messagebox.showerror("Error", "Please enter a valid operator (+, -, *, /)")
            
    except ValueError:
        messagebox.showerror("Error", "Please enter valid numbers in the entry fields!")


window = Tk()
window.title("Smart Calculator")
window.geometry("280x350")
window.config(bg="#1E1E2E") 


bg_color = "#1E1E2E"
fg_color = "#FFFFFF"
entry_bg = "#313244"
button_bg = "#89B4FA"
text_color = "#CDD6F4"


label = Label(window, text="Smart Calculator", font=("Arial", 14, "bold"), bg=bg_color, fg=fg_color)
label.pack(pady=5)

n1 = Entry(window, width=20, font=("Arial", 11), bg=entry_bg, fg=fg_color, insertbackground="white", justify="center")
n1.pack(pady=5)

n2 = Entry(window, width=20, font=("Arial", 11), bg=entry_bg, fg=fg_color, insertbackground="white", justify="center")
n2.pack(pady=5)

empty_label1 = Label(window, text=" ", font=("Arial", 6), bg=bg_color)
empty_label1.pack()

process_Label = Label(window, text="Choose a Process (+, -, *, /)", font=("Arial", 11), bg=bg_color, fg=text_color)
process_Label.pack()

process_button = Entry(window, width=10, font=("bold", 12), bg=entry_bg, fg=fg_color, insertbackground="white", justify="center")
process_button.pack(pady=5)

empty_label2 = Label(window, text=" ", font=("Arial", 6), bg=bg_color)
empty_label2.pack()

button = Button(window, text="Get Answer", font=("Arial", 12, "bold"), command=process, bg=button_bg, fg="#11111B", relief="flat", padx=10, cursor="hand2")
button.pack(pady=5)

empty_label3 = Label(window, text="Your Answer is: ", font=("Arial", 12, "bold"), bg=bg_color, fg="#A6E3A1")
empty_label3.pack(pady=10)

window.mainloop()
