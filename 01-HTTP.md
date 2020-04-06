# Chapitre 1. HTTP

## 1.1 Application client/serveur

HTTP est un protocole de couche application. Il permet la communication entre 2 systèmes informatiques à l'aide d'une connexion TCP. Le numéro de port du serveur est traditionnellement 80 mais il peut être, bien évidemment, modifié. Le service demandé est localisé par une *URL*.

Les requêtes et réponses utilisent le codage ASCII mais l'échange de contenu peut se faire selon un autre codage, voire en binaire. Les principales méthodes de requêtes sont:

- `GET`

- `POST`

- `HEAD`, `PUT`, `DELETE`, `OPTIONS`, `CONNECT`...

## 1.2. Méthode GET

La requête se trouve dans l'URL sous la forme d'une chaîne de caractères.

Exemple d'URL: `http://localhost:7001/index.html`

Exemple de requêtes:

- Première version de l'HTTP (rétrospectivement appelée 0.9):

```http
GET /index.html
```

- HTTP version 1.0:

```http
GET /index.html HTTP/1.0
```

- HTTP version 1.1:

```http
GET /index.html HTTP/1.1
Host: localhost:7001
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:21.0) Gecko/20100101 Firefox/21.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: fr,fr-fr;q=0.8,en-us;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
```

Le serveur répond ensuite par `200 OK` ou un code d'erreur (`400`, `404`, ...) puis, si c'est le cas, la ressource demandée:

```http
HTTP/1.1 200 OK
Date: Sun, 23 Jun 2013 20:07:53 GMT
Server: Apache/2.4.4 (Fedora) PHP/5.4.16
Last-Modified: Sun, 23 Jun 2013 15:30:08 GMT
ETag: "c7-4dfd3f8973872"
Accept-Ranges: bytes
Content-Length: 199
Content-Type: text/html; charset=UTF-8

<!DOCTYPE htm;>
<html>
...
```

Pour transmettre des paramètres à une servlet (script CGI, PHP...) avec la commande GET, il faut ajouter des couples `paramètre=valeur` à la fin de l'URL après le caractère `?`. Les différents couples sont séparés par un `&`:

```http
GET /index.php?param1=valeur1¶m2=valeur2 HTTP/1
```

Ces paramètres sont extraits par le serveur et transmis à la servlet appropriée via la variable d'environnement `QUERY_STRING` au moment de son lancement.

Propriétés des requêtes `GET`:

- elles peuvent être mises en cache,

- elles sont conservées dans l'historique du navigateur,

- elles peuvent être enregistrées en favoris,

- elles sont limitées en longueur (l'URL est limitée à 2048 caractères).

## 1.3. Méthode POST

```http
POST /test/index.php HTTP/1.1
Host: localhost
name1=value1&name2=value2
```
