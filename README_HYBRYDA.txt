INSTRUKCJA HYBRYDOWA (az.pl + Render.com)

Ten projekt jest teraz podzielony na dwie części, aby ominąć problemy z hostingiem az.pl.

KROK 1: URUCHOMIENIE BACKENDU (Render.com)
1. Zaloguj się na Render.com.
2. Kliknij "New" -> "Web Service".
3. Wybierz opcję "Build and deploy from a Git repository" (jeśli masz kod na GitHub) LUB użyj ich CLI, aby wysłać pliki:
   - Wgraj pliki z folderu dist-ftp (BEZ folderu public) na Render.
   - Settings na Renderze:
     - Runtime: Node
     - Build Command: npm install
     - Start Command: node server.mjs
4. W sekcji "Environment Variables" dodaj:
   - ADMIN_PASSWORD_HASH: f1685ddac29207fdd460574fd43bb40a5b51c1e5f4873e739aab1857f5e85de0
   - PORT: 10000 (Render zazwyczaj sam to ustawia)
5. Po uruchomieniu, Render poda Ci adres URL Twojego backendu (np. https://agency-backend.onrender.com). Skopiuj go!

KROK 2: AKTUALIZACJA FRONTENDU (az.pl)
1. Ponieważ adres na Renderze jest unikalny, musisz go wpisać w pliku na az.pl.
2. Otwórz plik: public/assets/index-XXXX.js (największy plik JS w folderze assets).
3. Znajdź w nim tekst: "https://twoja-aplikacja-backend.onrender.com" i zamień go na swój adres z Rendera.
4. Wgraj zawartość folderu 'public' przez FTP na az.pl do głównego katalogu strony.

KROK 3: BAZA DANYCH NA RENDERZE
1. Na Renderze, w sekcji "Shell" lub "Events", sprawdź czy aplikacja ruszyła.
2. Aby stworzyć tabele, w zakładce "Shell" na Renderze wpisz: npm run db:push

DZIĘKI TEMU:
- Strona będzie ładować się błyskawicznie z az.pl.
- Cała logika, panel admina i baza danych będą bezpiecznie działać na Render.com.
- Wszystko będzie połączone automatycznie.
