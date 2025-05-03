WebAppChat

Krátká dokumentace k zprovoznění

1. Stažení a příprava

git clone <URL tvého repozitáře>
cd WebChatApp
dotnet restore

2. Kompilace a spuštění

dotnet build
dotnet run --urls "http://0.0.0.0:5000"

3. Přístup k aplikaci

V prohlížeči otevři:http://localhost:5000nebohttp://<IP_serveru>:5000 (při připojení z jiné stanice v síti)

4. Volitelná konfigurace

Pro změnu portu/URL uprav Properties/launchSettings.jsonnebo použij přepínač --urls při spuštění

5. Firewall

Ujisti se, že je port 5000 povolený pro příchozí TCP spojení
