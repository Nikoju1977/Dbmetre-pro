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