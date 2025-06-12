WebChatApp

Jednoduchá ASP.NET Core chatovací aplikace využívající SignalR

Popis

WebChatApp je realtime chatovací aplikace postavená na ASP.NET Core a SignalR. Klienti se připojí přes webový prohlížeč, zadají uživatelské jméno a mohou okamžitě odesílat a přijímat zprávy v reálném čase.

Obsah repozitáře

Program.cs – hlavní konfigurace serveru

Hubs/ChatHub.cs – definice SignalR hubu pro odesílání zpráv

wwwroot/index.html – frontend (HTML + JavaScript)

wwwroot/css/site.css – moderní minimalistické styly

README.md – tento soubor s dokumentací

1. Požadavky

.NET SDK 7.0 nebo novější

Webový prohlížeč s podporou JavaScriptu (Chrome, Edge, Firefox, Safari)

(Volitelně) ngrok pro veřejné testování

2. Stažení projektu

Otevřete terminál (CMD/PowerShell/Bash) ve složce, kam chcete projekt umístit.

Pokud jste již dříve stáhli WebChatApp do stejné složky, buď:

Vynechte krok klonování a přejděte do existující složky:

cd WebChatApp

Nebo odstraňte starou složku a opakujte klon:

rm -rf WebChatApp    # Linux/macos
rmdir /s /q WebChatApp  # Windows

Pro klonujte repozitář (nahraďte <USERNAME> svým GitHub uživatelským jménem):

git clone https://github.com/<USERNAME>/WebChatApp.git
cd WebChatApp

Obnovte NuGet balíčky:

dotnet restore

3. Kompilace a spuštění

Sestavte projekt:

dotnet build

Spusťte server na všech rozhraních, port 5000:

dotnet run --urls "http://0.0.0.0:5000"

V terminálu by se mělo objevit:

Now listening on: http://0.0.0.0:5000

4. Přístup k aplikaci

Lokalně (na stejném PC):Otevřete v prohlížeči: http://localhost:5000

Z jiné stanice v LAN:

Zjistěte IP vaší stanice (serveru):

Windows: ipconfig

Linux/macOS: ifconfig nebo ip addr

V prohlížeči klientského zařízení otevřete: http://<IP_adresa_serveru>:5000

5. Princip fungování

Klient načte index.html a uloží připojení ke ChatHub.

Uživatel zadá jméno a zprávu, klikne Odeslat.

Frontend zavolá metodu SendMessage(user, message) na serveru.

Server rozesílá všem připojeným klientům událost ReceiveMessage.

Klienti zobrazí zprávu spolu s časovým razítkem (HH:MM:SS) a automaticky scrollují na konec.

6. Styl a vzhled

Moderní minimalistický design je definován v wwwroot/css/site.css:

Flexbox layout pro šířku a výšku viewportu.

Jemné stíny a zaoblené rohy zpráv.

Jednoduché barvy: bílá pozadí, šedé okraje, modrý akcent tlačítka.

7. Volitelná konfigurace

Pro změnu portu nebo URL upravte Properties/launchSettings.json nebo přidejte přepínač --urls při dotnet run.

Pokud je port 5000 blokován firewallem, povolte ho pro příchozí TCP.

