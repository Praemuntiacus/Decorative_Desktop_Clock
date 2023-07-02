# Decorative_Desktop_Clock
A decorative desktop clock .exe application created with Python programming language

The code:

```
import tkinter as tk
from PIL import ImageTk, Image
from datetime import datetime

class DecoratedClock(tk.Frame):
    def __init__(self, master=None, image_path=None, **kwargs):
        super().__init__(master, **kwargs)
        self.image_path = image_path
        self.load_image()
        self.create_clock_label()
        self.update_clock()

    def load_image(self):
        try:
            # Load the image file
            image = Image.open(self.image_path)
            image = image.resize((400, 400))  # Resize the image if necessary
            self.photo = ImageTk.PhotoImage(image)

            # Create a label with the image as the background
            self.image_label = tk.Label(self, image=self.photo)
            self.image_label.pack()

        except Exception as e:
            print("Error loading image:", str(e))

    def create_clock_label(self):
        self.clock_label = tk.Label(self, font=("Arial", 42), bg="#b0ae85", foreground="maroon")
        self.clock_label.place(relx=0.5, rely=0.51, anchor="center")
     
        
    def update_clock(self):
        current_time = datetime.now().strftime("%H:%M:%S")  # Get current time
        self.clock_label.config(text=current_time)  # Update the clock label
        self.after(1000, self.update_clock)  # Schedule the next update after 1 second (1000 milliseconds)

root = tk.Tk()
root.title("Decorated Clock")

image_path = "C:/Users/syriu/arnouveau_frame.png"
clock = DecoratedClock(root, image_path=image_path)
clock.pack()

root.mainloop()
```


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

```

!pyinstaller --onefile --noconsole --add-binary "C:/path/to/file/arnouveau_frame.png;." --icon=2_clock_icon_bright.ico Desktop_ArtNouveau_Clock.py

```


This code is a command-line instruction using the **PyInstaller** tool to create a standalone executable file for a Python program called **"Desktop_ArtNouveau_Clock.py"**.

- **!pyinstaller**: This is the command to invoke **PyInstaller**, which is a tool used to package Python programs into standalone executables. **"!"** is necessary if you work in Jupyter Notebook.
- **--onefile**: This option specifies that the output should be a single executable file (**.exe**), as opposed to a collection of separate files.
- **--noconsole**: This option indicates that the resulting executable should not open a console or command prompt window when executed.
- **--add-binary "C:/path/to/file/arnouveau_frame.png;."**: This option specifies that an additional binary file should be included in the executable. In this case, it adds the image file *"arnouveau_frame.png"* located at *"C:/path/to/file/"* to the executable. The semicolon (;) separates the source and destination paths, and the dot (.) indicates that the file should be placed in the same directory as the executable.
- **--icon=2_clock_icon_bright.ico**: This option sets the icon for the resulting executable. It specifies the file *"2_clock_icon_bright.ico"* as the icon file to be used. You can convert  any image file to **.ico** format online
- **Desktop_ArtNouveau_Clock.py**: This is the Python script file that I packaged into the executable. The name of your file may be different.

So, running this command with **PyInstaller** will create a single standalone executable **.exe** file for the specified Python script, including an additional image file and an icon file if provided. The resulting **.exe** file can be run on a compatible system without the need for Python or any external dependencies.

<div align="center">
  <img src="https://github.com/Praemuntiacus/Decorative_Desktop_Clock/raw/main/desktop%20clock%20view.png" alt="Desktop Clock View" width="300px">
</div>


**Note**: Due to the presence of an embedded image, the generated desktop clock **.exe** file may trigger security measures on other PCs where I attempted to run the application.





