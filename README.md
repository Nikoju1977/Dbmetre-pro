# DBMètre

Application web autonome de mesure sonore.

## Fonctions
- autorisation microphone explicite avec état accordé/refusé
- fallback getUserMedia pour anciens navigateurs compatibles
- analyse spectrale FFT temps réel de 20 Hz à 20 kHz
- fréquence dominante
- énergie moyenne par bandes : graves / médiums / aigus
- mesure micro en temps réel
- affichage dBFS
- offset de calibration pour approximation dB SPL
- moyenne et pic
- graphe temps réel
- journal horodaté
- export CSV
- enregistrement audio via MediaRecorder
- téléchargement de l'enregistrement

## Lancer
Le micro est généralement autorisé uniquement depuis :
- `https://...`
- ou `http://localhost`

Exemple :
```bash
python3 -m http.server 8080
```
Puis ouvrir :
`http://localhost:8080`

## Calibration
Les navigateurs ne fournissent pas une valeur SPL absolue fiable.
Pour calibrer :
1. placez un sonomètre de référence près du téléphone/ordinateur ;
2. diffusez un bruit stable ;
3. comparez la valeur de référence à la valeur dBFS affichée ;
4. entrez la différence dans "Offset de calibration SPL".


## Précision des mesures et limites

**Thème : son · outils de mesure.** Le niveau numérique **dBFS** est une mesure relative à la pleine échelle du signal acquis ; ce n'est pas une mesure absolue de pression acoustique en **dB SPL**. L'offset permet une estimation uniquement après comparaison à un sonomètre de référence dans des conditions contrôlées, mais ne remplace pas la réponse fréquentielle, l'étalonnage et les tolérances d'un appareil de mesure certifié.

L'application dépend des caractéristiques du microphone, des traitements du système, du navigateur et des autorisations de capture. Ne pas l'utiliser pour une expertise réglementaire du bruit, une évaluation d'exposition professionnelle ou une décision de sécurité auditive.

**Confidentialité :** l'accès au microphone exige l'autorisation de l'utilisateur ; examiner le code et les destinations réseau avant utilisation avec un son confidentiel. Les enregistrements ne doivent pas être publiés dans les issues GitHub.

**Statut :** instrument de visualisation / exploration non certifié ; tests de précision non attestés.

[Catalogue Studio Niko Design](https://github.com/Nikoju1977).


## Précision, permissions et confidentialité

- L'interface affiche le **dBFS**, c'est-à-dire un niveau numérique relatif à la pleine échelle. Ce n'est pas une mesure absolue en **dB SPL**.
- L'offset de calibration fourni par l'application est **une approximation** dépendant du microphone, de son traitement automatique, du navigateur, de la fréquence et de l'environnement. Il ne transforme pas le téléphone en sonomètre réglementaire.
- Une autorisation explicite du microphone est nécessaire. Vérifier les paramètres de confidentialité du navigateur ; une éventuelle capture audio ne doit être faite qu'avec l'accord des personnes concernées.
- Pour des mesures de sécurité au travail ou de conformité acoustique, employer un instrument approprié et étalonné.

**Statut :** outil expérimental de visualisation sonore, sans qualification métrologique revendiquée.

[Catalogue des outils Studio Niko Design](https://github.com/Nikoju1977).
