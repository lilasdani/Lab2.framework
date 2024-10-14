# Lab2.framework

## Nr. 1 Ce vedeți în browser când deschideți pagina http://localhost:8000?
Laravel v10.48.22 (PHP v8.3.11) informatii laravel

## Nr. 2 Ce s-ar întâmpla dacă această cheie ar ajunge pe mâna unui răufăcător?
Consecinte grave. Se va avea acces la toate datele criptate confidentiale ale utilizatorilor.

## Nr. 3 Explicați diferența între crearea manuală a rutelor și utilizarea unui controller de resurse. Ce rute și ce nume de rute vor fi create automat?

 Manual: va trebui sa se scrie rutele explicit pentru fiecare actiune dintr-un controler, pe tipul CRUD (Create, Read, Update, Delete), trebuie să defineasca manual metodele HTTP (GET, POST, PUT, DELETE) și URL-urile corespunzătoare.

```
 Route::get('/tasks', [TaskController::class, 'index'])->name('tasks.index');
 Route::get('/tasks/create', [TaskController::class, 'create'])->name('tasks.create');
```

Automat: in loc sa se foloseasa definirea fiecarei rute manual, se foloseste metoda "Route::resource()", care va crea automat toate rutele dupa tipul CRUD. Un dezavantaj, nu sunt adresele url 
 
```
  GET|HEAD        tasks/create ........ tasks.create › TaskController@create  
  GET|HEAD        tasks/create ........ tasks.create › TaskController@create  
  GET|HEAD        tasks/{task} ............ tasks.show › TaskController@show  
  PUT|PATCH       tasks/{task} ........ tasks.update › TaskController@update  
  DELETE          tasks/{task} ...... tasks.destroy › TaskController@destroy  
  GET|HEAD        tasks/{task}/edit ....... tasks.edit › TaskController@edit  
  GET|HEAD        tasks/{task}/edit ....... tasks.edit › TaskController@edit 
```

## Întrebări de control:
### 1.Ce este un controller de resurse în Laravel și ce rute creează?
controller de resurse în Laravel este un tip special de controller care simplifică gestionarea operațiunilor de tip CRUD (Create, Read, Update, Delete) pentru o resursă specifică. 

### 3.Ce avantaje oferă utilizarea componentelor anonime Blade?
Componenta poate fi folosită în mai multe locuri din aplicație fără a repeta codul.Logica și stilurile pentru un anumit element sunt centralizate în componentă, făcând codul mai ușor de întreținut.Codul din blade devine mai curat, deoarece logica este separată de markup.

### 4.Ce metode de cereri HTTP sunt folosite pentru a executa operațiunile CRUD?
Create - POST,
Read - GET, 
Update - PUT/PATCH, 
Delete - DELETE