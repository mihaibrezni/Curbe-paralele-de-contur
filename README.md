# Detalii implimentare
- Site folosit pentru vizualizarea imaginilor - foarte util :)
   [https://www.coolutils.com/online/PPM-to-PNG]

- Pentru paralelizarea algoritmului am mers la modificarea functiei de RESCALE_IMAGE pentru carea am podificat antetul pentru a o trimite ca parametru la functia de THREAD_CREATE  din main.
- Pentru a realzia un algoritm paralel am recurs la crearea unui vector de threaduri si a unei structuri THREADPARAMS care contine toate atributele necesare pentru a prelucra imaginea. Parametrii sunt: imaginea, imaginea finala, numarul de threaduri, dimensiunea imaginii, numarul de pixeli si numarul de pixeli pe thread.
- Paralelizarea a presupus impartirea liniei din GRID in ai multe bucati de memorie ce puteau fi prelucrate simultan si anume calcularea punctelor de presiune -> culorile de pe noua imagine
- In functia rescale dupa determinara paralelizarii, calculam fiecare pixel de rosu, galben si albastru. De asemena utilizam o BARIERA pentru a stii ca toate threadurile s-au terminat la iesirea din functia de scalare.
- Toata partea de paralelizare este in functia de rescale, unde se creeaza threadurile si se asteapta la finalizarea lor. De asemenea si alte functii pot fi paralelizate pentru a creste eficienta programului.

