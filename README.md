git push -u origin main --forceWebChatApp

Krátká dokumentace k zprovoznění

1. Požadavky

.NET SDK 7.0 nebo novější (https://dotnet.microsoft.com)

Moderní webový prohlížeč s podporou JavaScriptu (Chrome, Edge, Firefox, Safari)

2. Stažení a příprava

git clone <URL tvého repozitáře>
cd WebChatApp
dotnet restore

3. Kompilace a spuštění

dotnet build
dotnet run --urls "http://0.0.0.0:5000"

4. Přístup k aplikaci

V prohlížeči otevři:http://localhost:5000nebohttp://<IP_serveru>:5000 (při připojení z jiné stanice v síti)

5. Volitelná konfigurace

Pro změnu portu/URL uprav Properties/launchSettings.jsonnebo použij přepínač --urls při spuštění

6. Firewall

Ujisti se, že je port 5000 povolený pro příchozí TCP spojení

7. Nasazení

Pro produkční build:

dotnet publish -c Release
