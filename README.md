# file-write
## F1.09.02.O2 - Logfile
met de file.write() gaat hij nu steeds een regel plaatsen in de action.log
``` python
def buttonPress(event):
    if button.config('text')[-1] == 'Switch light on':
        button.config(text='Switch light off',bg="white",fg="black")
        window.config(bg="black")  
        print("\nlight is off")    
        file.write("\nLight is off")
    else:
        randomColor = random.choice(COLORS)
        button.config(text='Switch light on',bg="white",fg=randomColor)
        window.config(bg=randomColor)      
        print("\nlight is on \nColor: " + randomColor)
        file.write("\nlight is on \nColor: " + randomColor)
button.bind('<Button>', buttonPress)
```
