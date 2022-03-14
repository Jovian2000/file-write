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
## F1.09.02.O4 - Dynamic Logfile
Nu kan hij checken of het bestand al bestaat met os.path.exists(). Hij geeft uiteindelijk een True of False aan, als het True is dan bestaat het al, anders niet.
Met "file = open("C:/Users/Gebruiker/OneDrive/Bureaublad/ICT/file-write/action.log","w")" opent hij het bestand en kan je erin (her)schrijven
Met "file = open("C:/Users/Gebruiker/OneDrive/Bureaublad/ICT/file-write/action.log","x")" maakt hij het bestand aan
``` python
import os.path

if os.path.exists("C:/Users/Gebruiker/OneDrive/Bureaublad/ICT/file-write/action.log"):
    file = open("C:/Users/Gebruiker/OneDrive/Bureaublad/ICT/file-write/action.log","w")
    file.write("Logboek lightswitch\n")
else:
    file = open("C:/Users/Gebruiker/OneDrive/Bureaublad/ICT/file-write/action.log","x")
    file.write("Logboek lightswitch\n")
```
