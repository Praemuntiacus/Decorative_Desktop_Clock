# Decorative_Desktop_Clock
A decorative desktop clock .exe application created with Python programming language

This Python code utilizes the libraries **tkinter**, **PIL** (Pillow), and **datetime** to create a graphical window containing a decorated clock with a background image. Here's a detailed description of the code:

- The necessary libraries are imported: **tkinter** for creating the graphical interface, **PIL** for loading and manipulating images, and datetime for getting the current time.

- A class named **DecoratedClock** is defined as a subclass of **tk.Frame**. This class represents the decorated clock.

- In the __init__ constructor of the **DecoratedClock** class, some attributes are initialized. **master** is the parent widget, usually the main window. **image_path** is the path to the image used as the clock's background. Other parameters (**kwargs) are passed to the superclass constructor.

- The **load_image** method is defined to load the image from the specified path. It uses the **PIL** library to open the image, resizes it if necessary, and creates an instance of **ImageTk.PhotoImage**, which is a tkinter class for representing an image. Then, a **Label** widget is created with the image as the background and placed in the main window.

- The **create_clock_label** method is defined to create a Label widget that will display the clock's time. This widget is placed in the center of the main window with specified font and color.

- The **update_clock** method is defined to update the time displayed by the clock. It uses **datetime.now().strftime("%H:%M:%S")** to get the current time in the *hours:minutes:seconds* format. Then, it updates the text of the clock's Label widget with this time. Finally, it schedules the next clock update after 1 second using tkinter's **after** method.

- The main window (root) is created using **tk.Tk()**. Its title is set as *"Decorated Clock"*.

- The image path is specified in *image_path*.

- An instance of the **DecoratedClock** class is created by passing the main window and the image path as arguments. This instance is then packed into the main window.

- Finally, the main loop (**mainloop()**) is launched to display the graphical window and wait for user interactions.

- So, this code creates a graphical window with a decorated clock displaying the current time. The clock uses a background image specified by the **image_path**. The time is updated every second. Finally, I created the desktop clock **.exe** file with the following code:

'''
!pyinstaller --onefile --noconsole --add-binary "C:/path/to/file/arnouveau_frame.png;." --icon=2_clock_icon_bright.ico Desktop_ArtNouveau_Clock.py

'''

**Note**: Due to the presence of an embedded image, the generated desktop clock .exe file may trigger security measures on other PCs where I attempted to run the application.





