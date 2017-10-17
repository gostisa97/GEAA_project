# GEAA_project
uporabniška_imena = []
gesla = []
#novo uporabniško ime
novo_ime = input('Vpišite novo uporabniško ime: \n')
novo_geslo = input('Vpišite novo geslo: \n')
novo_geslo_2 = input('Ponovno vpišite geslo: \n')
if novo_geslo == novo_geslo_2:
    uporabniška_imena.append(novo_ime)
    gesla.append(novo_geslo)
    print('Nov uporabnik je dodan.')
elif novo_geslo != novo_geslo_2:
    poskus_2 = input('Gesli se ne ujemata poskusi ponovno: \n')
    if novo_geslo == poskus_2:
        uporabniška_imena.append(novo_ime)
        gesla.append(novo_geslo)
        print('Nov uporabnik je dodan.')
    elif novo_geslo != poskus_2:
        print('Prijava ni uspela. Poskusi ponovno!')
else:
    print('Prijava ni uspela. Poskusi ponovno!')
kompleti = dict(list(zip(uporabniška_imena, gesla)))
print(kompleti)
#prijava, ko že imaš uporabniško ime
user = input('Vpišite uporabniško ime: \n')
pasword = input('Vpišite vaše geslo: \n')
if kompleti[user] == pasword:
    print('Dobrodošli!')
    prijava = True
elif kompleti[user] != pasword:
    print('Nepravilno geslo!')
    prijava = False
else:
    print('Uporabniško ime ne obstaja')
    prijava = False
if prijava is True:
    from tkinter import *
    import webbrowser
    
    def pushTheButton():
        webbrowser.open('https://www.youtube.com/watch?v=Gvchbkh4jQY')
    
    root = Tk()

    button = Button(root, text = "Pritisni, če želite slišati Severino!", command = pushTheButton)
    button.pack()
    
    text = Text(root)
    text.insert(INSERT, "Zgoraj se nahaja gumb, ki vas bo popeljal do YT posnetka.\n")
    text.insert(END, "Lep pozdrav, Andraž Gostiša")
    text.pack()

    text.tag_add("here", "10.0", "1.4")
    text.tag_add("start", "10.0", "1.13")
    root.mainloop()

    root.mainloop()
else:
    print('Prijava ni uspela')
    
