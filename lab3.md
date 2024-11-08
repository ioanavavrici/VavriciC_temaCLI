1. Ordinea de desenare a vertexurilor și desenarea axelor de coordonate
Ordinea de desenare a vertexurilor
În OpenGL, ordinea de desenare a vertexurilor determină orientarea fațetelor și influențează modul în care acestea sunt cull-uite (ascunse) prin culling backface.

Ordinea de desenare este anti-orară (counter-clockwise) pentru ca fațetele să fie considerate orientate în față (front-facing) în mod implicit. Vertexurile sunt desenate în sens invers acelor de ceasornic pentru ca fața să fie vizibilă.
2. Ce este anti-aliasing?
Anti-aliasing este o tehnică utilizată pentru a reduce "aliasing-ul", adică efectul de margini zimțate și pixeli distorsionați care apar atunci când desenăm forme grafice cu margini înclinate sau curbate. În esență, anti-aliasingul face tranzițiile dintre marginile obiectelor și fundal mai puțin ascuțite, oferind o grafică mai netedă și mai naturală. În OpenGL, anti-aliasingul poate fi activat folosind funcții precum GL.Enable(EnableCap.LineSmooth) sau GL.Enable(EnableCap.PolygonSmooth).

3. Efectul GL.LineWidth(float) și GL.PointSize(float)
GL.LineWidth(float) - Ajustează grosimea liniilor desenate. De exemplu, GL.LineWidth(2.0f); va face liniile de două ori mai groase decât valoarea implicită. Această comandă nu funcționează în interiorul unei zone GL.Begin().

GL.PointSize(float) - Ajustează dimensiunea punctelor desenate. De exemplu, GL.PointSize(5.0f); va face ca punctele să fie de cinci ori mai mari decât dimensiunea implicită. La fel ca în cazul GL.LineWidth, această comandă trebuie apelată în afara unei secțiuni GL.Begin().

4. Diferite directive de desenare în OpenGL 

LineLoop: Desenează o linie continuă care conectează primul și ultimul vertex, formând o buclă închisă.

LineStrip: Desenează o linie continuă care conectează toate punctele, dar nu închide forma. Utilă pentru crearea liniilor curbe sau a segmentelor multiple.

TriangleFan: Desenează un set de triunghiuri care au un vertex comun și care se extind în formă de evantai. Ideal pentru crearea poligoanelor circulare.

TriangleStrip: Desenează o serie de triunghiuri conectate prin laturi comune. Fiecare nou vertex, după primii doi, formează un nou triunghi împreună cu cei doi vertexuri precedenți.

5. Crearea unui proiect elementar
Viewport-ul este configurat astfel:
GL.Viewport(0, 0, width, height);
6. Importanța culorilor diferite în desenarea obiectelor 3D
Utilizarea culorilor diferite, fie în gradient, fie selectate individual pentru fiecare suprafață, este importantă pentru a evidenția profunzimea și structura obiectelor 3D. Aplicarea unui gradient de culori poate adăuga realism, deoarece simulează efecte de lumină și umbră. De asemenea, ajută la diferențierea diferitelor fețe ale obiectului, făcând mai ușoară perceperea formei și orientării acestuia.
7. Un gradient de culoare reprezintă o tranziție lină între două sau mai multe culori. În OpenGL, un gradient se obține setând culori diferite pentru fiecare vertex al unei forme, iar OpenGL va interpola aceste culori pentru a crea o tranziție lină între ele.

Pentru a desena un triunghi cu un gradient, putem seta culori diferite pentru fiecare vertex:
GL.Begin(PrimitiveType.Triangles);
GL.Color3(1.0f, 0.0f, 0.0f); GL.Vertex3(-0.5f, -0.5f, 0.0f); // Vertex roșu
GL.Color3(0.0f, 1.0f, 0.0f); GL.Vertex3(0.5f, -0.5f, 0.0f);  // Vertex verde
GL.Color3(0.0f, 0.0f, 1.0f); GL.Vertex3(0.0f, 0.5f, 0.0f);   // Vertex albastru
GL.End();
10. Atunci când fiecare vertex al unei linii sau al unui triunghi are o culoare diferită, OpenGL va interpola culorile între vertexuri, generând astfel un gradient de culoare. Acest efect poate fi folosit pentru a simula iluminarea și pentru a crea o iluzie de profunzime pe obiecte simple.