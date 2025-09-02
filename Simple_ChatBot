import tkinter as tk
from PIL import Image, ImageTk
import time
import random
import datetime

def get_bot_response(msg):
    msg = msg.lower()

    if "hello" in msg or "hi" in msg or "hey" in msg:
        return random.choice(["Hey there! 👋", "Hi! How’s it going?", "Hello! 😃"])
    
    elif "how are you" in msg:
        return random.choice(["I'm doing great, thanks for asking! How about you? 🙂",
                                "Pretty good today! What about you?",
                                "All good here, hope you're doing well too!"])
    
    elif "wassup" in msg or "wsg" in msg or "sup" in msg:
        return random.choice(["Not much, just chilling 🤙", 
                                "All good here, what about you?", 
                                "Just hanging out 😁"])
    
    elif "i am fine" in msg or "i'm fine" in msg or "good" in msg:
        return random.choice(["Glad to hear that! 😄", 
                                "Nicee! Keep it up ✨", 
                                "Awesome! 👍"])
    
    elif "name" in msg or "who are you" in msg:
        return random.choice(["I'm your friendly chatbot 🤖", 
                                "Just a simple chatbot created to chat with you 💬",
                                "They call me… ChatBot 2.0 😎"])
    
    elif "made" in msg or "created" in msg:
        return "I was created by DARSHAN. 🔥"
    
    elif "what are you doing" in msg or "wyd" in msg:
        return random.choice(["Just chatting with you! 🗨️", 
                                "Waiting for your next message 👀",
                                "Talking to my favorite human 😁"])
    
    elif "where are you from" in msg:
        return "I live inside this computer 💻 What about you?"
    
    elif "thank" in msg:
        return random.choice(["You're most welcome! 😊", 
                                "Anytime! 🙌", 
                                "No problem at all 😃"])
    
    elif "bye" in msg or "goodbye" in msg or "gn" in msg or "good night" in msg:
        return random.choice(["See you soon! 👋 Take care.", 
                                "Goodbye! Have a nice day 🌸", 
                                "Bye bye! ✌️"])
    
    elif "joke" in msg:
        return random.choice([
            "😂 Why don’t scientists trust atoms? Because they make up everything!",
            "🤣 Why did the scarecrow win an award? Because he was outstanding in his field!",
            "😅 Why was the math book sad? Because it had too many problems."
        ])
    
    elif "haha" in msg:
        return "Glad you enjoyed the joke! 😂"
    
    elif "time" in msg:
        return f"It's {time.strftime('%I:%M %p')} right now ⏰"
    
    elif "day" in msg:
        return f"Today is {datetime.datetime.now().strftime('%A')}."
    
    elif "date" in msg:
        return f"The date is {datetime.datetime.now().strftime('%B %d, %Y')}."
    
    elif "love" in msg:
        return random.choice(["Aww ❤️ love is a beautiful thing!", 
                                "Love makes the world go round 💕", 
                                "Sending you virtual love 💖"])
    
    elif "bored" in msg:
        return random.choice(["Let’s fix that! Tell me something fun you like to do 😃", 
                                "Bored? Maybe listen to music or play a game 🎶🎮", 
                                "How about a joke to cheer you up? 😂"])
    
    elif "food" in msg or "eat" in msg or "hungry" in msg:
        return random.choice(["Yum! 🍕🍔🍩 What's your favorite food?", 
                                "I wish I could eat too 😅", 
                                "Food is life! ❤️ What do you like the most?"])
    
    elif "lol" in msg or "lmao" in msg:
        return "😂 Glad you found that funny!"
    
    elif "hobby" in msg or "hobbies" in msg:
        return "I like chatting with you! What's your hobby? 🎨⚽🎶"
    
    elif "yes" in msg:
        return random.choice(["Great! 👍", "Awesome 😃", "Cool, got it ✅"])
    
    elif "no" in msg:
        return random.choice(["Ohh okay 😅", "Alright, no worries!", "Got it, thanks for telling me 🙌"])
    
    elif "ok" in msg or "okay" in msg or "k" in msg:
        return random.choice(["Okay 👍", "Cool 😎", "Alright then!"])
    
    else:
        return random.choice([
            "Hmm 🤔 I didn’t quite get that.",
            "Can you say it another way?",
            "Interesting... tell me more!",
            "Ohh, that's cool! 😃"
        ])


def show_message(text, sender):
    time_now = time.strftime("%H:%M")

    outer_frame = tk.Frame(messages_frame, bg="lightblue")
    
    bubble_color = "#e1ffc7" if sender == "user" else "#f1f0f0"
    
    if sender == "bot":
        outer_frame.pack(fill="x", pady=(5, 0), anchor="w")
        container = tk.Frame(outer_frame, bg="lightblue")
        container.pack(anchor="w", padx=10)

        logo_label = tk.Label(container, image=bot_logo_photo, bg="lightblue")
        logo_label.pack(side="left", padx=(0, 5))

        bubble = tk.Frame(container, bg=bubble_color, padx=10, pady=5)
        bubble.pack(side="left")
    else:  
        sender == "user"
        outer_frame.pack(anchor="e", pady=(5, 0), padx=(50, 10))
        
        bubble = tk.Frame(outer_frame, bg=bubble_color, padx=10, pady=5)
        bubble.pack()

    msg_label = tk.Label(bubble, text=text, bg=bubble_color, font=("Segoe UI", 11), wraplength=250)
    time_label = tk.Label(bubble, text=time_now, font=("Segoe UI", 8), bg=bubble_color, fg="gray")

    if sender == "user":
        msg_label.config(justify="right")
        msg_label.pack(anchor="e")
        time_label.pack(anchor="e")
    else:
        msg_label.config(justify="left")
        msg_label.pack(anchor="w")
        time_label.pack(anchor="e")

    canvas.update_idletasks()
    canvas.yview_moveto(1.0)


def handle_user_input(event=None):
    msg = active_input.get().strip()
    if msg == "" or msg == "Type your message here..":
        return
    show_message(msg, "user")
    active_input.delete(0, tk.END)
    input_frame.destroy()

    window.after(500, lambda: show_message(get_bot_response(msg), "bot"))
    window.after(600, create_input_box)

def create_input_box():
    global input_frame, active_input

    input_frame = tk.Frame(messages_frame, bg="lightblue")
    
    input_frame.pack(pady=(5, 10), padx=10, anchor="e")

    active_input = tk.Entry(input_frame, font=("Segoe UI", 12), fg="gray")
    active_input.insert(0, "Type your message here..")
    active_input.pack(side="left", fill="x", expand=True, padx=(0,5))

    def on_focus_in(event):
        if active_input.get() == "Type your message here..":
            active_input.delete(0, tk.END)
            active_input.config(fg="black")

    def on_focus_out(event):
        if active_input.get().strip() == "":
            active_input.insert(0, "Type your message here..")
            active_input.config(fg="gray")

    active_input.bind("<FocusIn>", on_focus_in)
    active_input.bind("<FocusOut>", on_focus_out)
    active_input.bind("<Return>", handle_user_input)

    send_button = tk.Button(input_frame, text="Send", font=("Segoe UI", 10, "bold"),
                            bg="#4CAF50", fg="white", relief="flat", padx=12, pady=5,
                            command=handle_user_input)
    send_button.pack(side="right")

    canvas.update_idletasks()
    canvas.yview_moveto(1.0)


window = tk.Tk()
window.title("ChatBot")
window.geometry("350x500")
window.configure(bg="white")

try:
    icon = tk.PhotoImage(file='main_logo.png')
    window.iconphoto(True, icon)
    bot_logo_img = Image.open("chat_logo.png").resize((30, 30))
    bot_logo_photo = ImageTk.PhotoImage(bot_logo_img)
except Exception as e:
    print(f"Error loading images: {e}")
    print("Make sure 'main_logo.png' and 'chat_logo.png' are in the same directory.")
    bot_logo_img = Image.new('RGB', (30, 30), color = 'grey')
    bot_logo_photo = ImageTk.PhotoImage(bot_logo_img)


canvas_frame = tk.Frame(window)
canvas_frame.pack(fill="both", expand=True)

canvas = tk.Canvas(canvas_frame, bg="lightblue", highlightthickness=0)
scrollbar = tk.Scrollbar(canvas_frame, orient="vertical", command=canvas.yview)
canvas.configure(yscrollcommand=scrollbar.set)

scrollbar.pack(side="right", fill="y")
canvas.pack(side="left", fill="both", expand=True)

messages_frame = tk.Frame(canvas, bg="lightblue")
canvas.create_window((0, 0), window=messages_frame, anchor="nw")

def on_frame_configure(event):
    canvas.configure(scrollregion=canvas.bbox("all"))

messages_frame.bind("<Configure>", on_frame_configure)

def init_chat():
    show_message("Hello! Welcome to Darshan's Chatbot.", "bot")
    create_input_box()

window.after(300, init_chat)
window.mainloop()
