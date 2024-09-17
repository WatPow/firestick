Pour désactiver complètement la veille sur une Amazon Fire Stick à l'aide d'ADB, vous pouvez exécuter une série de commandes pour désactiver l'écran de veille et empêcher la mise en veille automatique. Voici les étapes :

1. **Connectez-vous à votre Fire Stick via ADB** (Assurez-vous que le mode Débogage ADB est activé sur la Fire Stick dans les paramètres).

```bash
adb connect <IP_de_votre_Fire_Stick>
```

Remplacez `<IP_de_votre_Fire_Stick>` par l'adresse IP réelle de votre Fire Stick.

2. **Désactiver le service de l'écran de veille** :

```bash
adb shell settings put secure screensaver_enabled 0
```

Cela désactive l'écran de veille.

3. **Désactiver la mise en veille automatique** (timeout) :

```bash
adb shell settings put system screen_off_timeout 2147483647
```

Cela met un très long délai avant que l'écran ne s'éteigne, rendant la mise en veille automatique presque impossible.

4. **Vérifier si les modifications ont été prises en compte** :

Vous pouvez vérifier que la valeur a bien été modifiée en exécutant la commande suivante :

```bash
adb shell settings get system screen_off_timeout
```

La valeur retournée devrait être `2147483647`, ce qui correspond à environ 24 jours.

5. **Déconnexion d'ADB** :

```bash
adb disconnect
```

Ces commandes devraient empêcher la Fire Stick de passer en veille.
