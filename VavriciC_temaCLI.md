1. Modificați valoarea constantei  `MatrixMode.Projection `. Ce observați?
Schimbarea proiecției afectează modul în care obiectele sunt randate pe ecran. 


3. Răspundeți la următoarele întrebări:


 1. Ce este un viewport?
Un viewport este o zonă dreptunghiulară a ferestrei în care OpenGL desenează conținutul grafic.
Dimensiunea și poziția acestuia sunt setate cu funcția `GL.Viewport()`. 
Este esențial pentru a adapta imaginea randată la dimensiunea ferestrei sau a ecranului.

 2. Ce reprezintă conceptul de frames per second (FPS) din punctul de vedere al bibliotecii OpenGL?
Frames per second (FPS) reprezintă numărul de cadre pe care OpenGL le poate randata pe secundă.
Este o măsură importantă a performanței aplicației grafice. 
Cu cât FPS-ul este mai mare, cu atât animațiile și interacțiunile grafice sunt mai fluide.

 3. Când este rulată metoda `OnUpdateFrame()`?
Metoda `OnUpdateFrame()` este rulată înainte de fiecare cadru randat pentru a actualiza logica
aplicației, precum mișcarea obiectelor, stările input-ului și alte acțiuni care influențează randarea.

 4. Ce este modul imediat de randare?
Modul imediat de randare este o tehnică veche folosită în OpenGL pentru a trimite comenzi individuale 
către GPU pentru fiecare vertex sau obiect. 
Deși a fost popular în versiunile mai vechi de OpenGL, acesta este ineficient comparativ cu tehnicile
moderne (VBO, VAO), deoarece nu optimizează procesul de trimitere a datelor către GPU.

 5. Care este ultima versiune de OpenGL care acceptă modul imediat?
Ultima versiune de OpenGL care suportă modul imediat este OpenGL 3.0. 
Începând cu versiunea 3.1, acest mod a fost depreciat în favoarea unor tehnici mai eficiente de randare.

 6. Când este rulată metoda `OnRenderFrame()`?
Metoda `OnRenderFrame()` este rulată de fiecare dată când trebuie să fie randat un nou cadru.
În această metodă se definesc toate operațiunile de randare necesare pentru afișarea obiectelor pe ecran.

 7. De ce este nevoie ca metoda `OnResize()` să fie executată cel puțin o dată?
Metoda `OnResize()` trebuie executată cel puțin o dată pentru a seta corect viewport-ul și proiecția 
atunci când fereastra este redimensionată. Fără această ajustare, conținutul grafic ar putea fi 
afișat incorect sau distorsionat.

 8. Ce reprezintă parametrii metodei `CreatePerspectiveFieldOfView()` și care este domeniul de valori?
Metoda `CreatePerspectiveFieldOfView()` creează o matrice de proiecție de perspectivă. Parametrii săi sunt:
- fov: Unghiul câmpului vizual, măsurat în radiani. Valorile uzuale sunt între 45 și 60 de grade.
- aspectRatio: Raportul de aspect (lățime/înălțime) al ferestrei. Acesta asigură că imaginea randată nu este distorsionată.
- nearPlane: Distanța până la planul apropiat de tăiere (valori tipice între 0.1 și 1.0).
- farPlane: Distanța până la planul îndepărtat de tăiere (de obicei 100.0 sau mai mare).
