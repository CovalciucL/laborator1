# Laborator 1: Bazele HTTP

## Sarcina Nr.1 Analiza cererilor HTTP

### Ce metodă HTTP a fost utilizată pentru a trimite cererea?
* Pentru trimiterea cererei a fost utilizată metoda POST
### Ce anteturi au fost trimise în cerere?
* Anteturile trimise în răspuns:
![request_headers](.images/request_headers.png)
### Ce parametri au fost trimiși în cerere?
1. În primul caz cererea a fost transmis parametrul username cu valoarea student și parametrul password cu valoarea studentpass
2. În al doilea caz cererea a fost transmis parametrul username cu valoarea student și parametrul password cu valoarea studentpass
### Ce cod de stare a fost returnat de server?
1. În primul caz codul de stare returnat este 401 Unauthorized ce înseamnă că parametrii dați nu au trecut autentificarea
2. În al doilea caz codul de stare returnat este 200 OK ce înseamnă că requestul a fost primit, procesat și parametrii au trecut autentificarea
### Ce anteturi au fost trimise în răspuns?
* Anteturile trimise în răspuns:
  
![response_headers](.images/response_headers.png)

## Sarcina Nr.2 Crearea cererilor HTTP

### Cerere de tip GET:
`GET / HTTP/1.1
Host: sandbox.com
User-Agent: Covalciuc Laurențiu`
### Cerere de tip POST:
`POST /cars HTTP/1.1
Host: sandbox.com
Content-Type: application/x-www-form-urlencoded

make=Toyota&model=Corolla&year=2020`
### Cerere de tip PUT:
`PUT /cars/1 HTTP/1.1
Host: sandbox.com
Content-Type: application/json
User-Agent: Covalciuc Laurențiu

{
  "make": "Toyota",
  "model": "Corolla",
  "year": 2021
}`
### Posibil răspuns pentru cererea POST
`HTTP/1.1 201 Created
Content-Type: application/json

{
  "id": 123,
  "make": "Toyota",
  "model": "Corolla",
  "year": 2020,
  "status": "created"
}`
* Situații în care serverul poate returna alte coduri de stare HTTP:
    * 200 OK: Serverul a primit și a procesat cu succes cererea, dar nu a fost creată nicio resursă nouă. De exemplu, dacă cererea POST a fost procesată, dar resursa exista deja sau a fost actualizată fără crearea unei noi înregistrări.

    * 201 Created: Cererea POST a fost procesată cu succes și o nouă resursă a fost creată.

    * 400 Bad Request: Cererea nu este validă. Aceasta poate apărea dacă parametrii furnizați sunt incompleți sau incorecți. De exemplu, dacă nu s-a specificat modelul sau anul.

    * 401 Unauthorized: Clientul nu este autorizat să facă această cerere deoarece fie nu s-a autentificat, fie autentificarea a eșuat.

    * 403 Forbidden: Clientul este autentificat, dar nu are permisiuni pentru a crea o resursă pe server.

    * 404 Not Found: Endpoint-ul specificat nu a fost găsit pe server, ceea ce înseamnă că URL-ul /cars poate să nu existe sau să fie incorect.

    * 500 Internal Server Error: A apărut o eroare internă pe server în timpul procesării cererii. Aceasta poate fi cauzată de o problemă de configurare sau de un bug în aplicație.
### Cerere de tip DELETE:
`DELETE /cars/1 HTTP/1.1
Host: sandbox.com
`
Această cerere de tip DELETE trimite o solicitare pentru a șterge resursa cu ID-ul 1. Metoda DELETE este potrivită în acest caz pentru a elimina permanent o resursă de pe server.

# Sarcina Nr.3 HTTP_Quest
* Fraza secretă: /home/devrdn/www/quest/progress/