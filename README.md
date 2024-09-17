
1. **Lister les appareils connectés** :
   Exécutez cette commande pour voir les appareils actuellement connectés à ADB :

   ```bash
   .\adb.exe devices
   ```

   Vous obtiendrez une liste des appareils, par exemple :

   ```bash
   List of devices attached
   192.168.1.101:5555	device
   emulator-5554	device
   ```

2. **Connectez-vous à votre Fire Stick** :
   Si vous voyez plusieurs appareils, vous devrez spécifier l'adresse IP ou l'ID de l'appareil que vous souhaitez utiliser. Par exemple, si votre Fire Stick est connecté via l'IP `192.168.1.101`, exécutez la commande suivante pour toutes les commandes ADB :

   ```bash
   .\adb.exe -s 192.168.1.101:5555 shell settings put secure screensaver_enabled 0
   ```

   Ou si vous utilisez un appareil USB, vous pouvez utiliser son ID, par exemple :

   ```bash
   .\adb.exe -s emulator-5554 shell settings put secure screensaver_enabled 0
   ```
