INSTRUKCJA INSTALACJI NA AZ.PL (cPanel):

1. Wgraj całą zawartość tego folderu przez FTP na swój serwer (najlepiej do nowego folderu, np. /agency-app).
2. Zaloguj się do panelu az.pl i przejdź do "Setup Node.js App".
3. Kliknij "Create Application".
4. Wybierz:
   - Node.js version: 18 lub nowsza
   - Application mode: Production
   - Application root: /agency-app (lub nazwa Twojego folderu)
   - Application URL: Twoja domena
   - Application startup file: app.js
5. Po utworzeniu aplikacji, kliknij przycisk "Run NPM Install".
6. (WAŻNE) Aby utworzyć tabele w bazie danych:
   - W sekcji "Setup Node.js App" znajdź przycisk "Execute command" (lub użyj Terminala w cPanel).
   - Uruchom komendę: npm run db:push
   - Jeśli nie masz dostępu do komend, napisz do mnie - przygotuję Ci gotowy plik bazy.
7. W sekcji "Environment variables" dodaj:
   - ADMIN_PASSWORD_HASH: f1685ddac29207fdd460574fd43bb40a5b51c1e5f4873e739aab1857f5e85de0
   (To jest zakodowane hasło: YJwWnzEBnH1RYfW1umIf)
8. Kliknij "Restart".

Twoja strona powinna teraz działać pod Twoją domeną!
Logowanie do panelu administratora: TwojaDomena.pl/admin (domyślne hasło ustawiasz w ADMIN_PASSWORD_HASH).

UWAGA: Baza danych (sqlite.db) i przesłane pliki (folder storage) znajdują się w tym samym folderze. Pamiętaj o robieniu kopii zapasowej tego folderu!
