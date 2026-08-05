# Table Read Tools — un plugin per a Beat

*[Read this in English](README.md)*

**Table Read Tools** és un plugin fet a mida per a [Beat](https://www.beat-app.fi), el programa de guionatge en format Fountain per a Mac. Afegeix fotografies als personatges i a les localitzacions, i converteix els diàlegs del guió en una vista de conversa tipus xat o en un mode de lectura en veu alta ("table read") en directe.

![Table Read Tools a Beat](web/Images/hero.png)

Beat, de per si, no permet posar fotos a personatges ni localitzacions ni visualitzar els diàlegs com una conversa — aquest plugin ho afegeix tot per sobre, sense modificar el guió.

---

## Funcionalitats

### Fotos de personatges i localitzacions
Arrossega una imatge des del Finder sobre la targeta d'un personatge o localització, o selecciona la targeta i enganxa (⌘V) una imatge copiada. Les fotos es redimensionen i queden incrustades directament dins l'arxiu del guió — no depenen de cap arxiu extern, així que el guió es manté totalment portàtil.

### Ordre d'importància dels personatges
Reordena els personatges per importància amb les fletxes ◀ ▶ de cada targeta. Aquest ordre decideix qui apareix com a "protagonista" (a la dreta, destacat) i qui són els secundaris (a l'esquerra, cadascun amb el seu color) tant a la vista de Conversa com al Table Read Mode.

### 💬 Vista de Conversa
Mostra el diàleg de cada escena com una conversa de xat:
- Els diàlegs del personatge protagonista de l'escena apareixen a la dreta; la resta, a l'esquerra, cadascun amb un color propi.
- Les fotos dels personatges es fan servir com a avatar.
- Cada escena comença amb una petita banda que mostra la foto de la localització (si en té).
- Les línies d'acció apareixen com a avisos centrats i discrets entre les bombolles de diàleg.
- Cada missatge porta una hora acumulada (començant a 0:00 a cada escena), i cada escena acaba amb el temps total, ben visible.

### 🎭 Table Read Mode
Un mode de lectura en pantalla completa, sense distraccions, pensat per llegir el guió en veu alta:
- Un cercle gran per cada personatge present a l'escena; el cercle de qui parla s'il·lumina amb un anell brillant.
- Un cronòmetre circular es va omplint al voltant del cercle de qui parla, mostrant quant queda de la seva frase — calculat per una estimació de velocitat de lectura (per caràcters, no per paraules, perquè les frases curtes i llargues es cronometrin de manera justa).
- El text de la línia apareix en una bombolla tipus "escenari", unida al personatge amb una cua d'còmic, del mateix color que el personatge.
- **Mode automàtic**: avança tot sol quan s'acaba el temps estimat de cada línia, amb una petita pausa entre frases.
- **Mode manual**: avança al teu ritme amb els botons de la pantalla o amb les fletxes del teclat / la barra espaiadora.
- La finestra és redimensionable, i la disposició (la filera de cercles, els controls) es manté sempre al mateix lloc perquè res no es mogui encara que canviï la llargada del text.

### 🌐 Interfície en diversos idiomes
La interfície del plugin (no el teu guió) està disponible en **català, anglès, francès i èuscar**. Es detecta automàticament segons l'idioma del sistema la primera vegada que obres la finestra, i es pot canviar manualment des del desplegable de la capçalera — la tria queda desada.

### 📤 Exporta / 📥 Importa fotos
Les fotos es guarden dins del propi arxiu del guió, així que si obres el mateix `.fountain` en un altre Mac (amb Beat i aquest plugin instal·lats), ja hi veuràs totes les fotos sense fer res més.

Exportar/Importar serveix per a un cas diferent: portar les mateixes fotos a un document **diferent** (per exemple, personatges recurrents en diversos guions) o guardar una còpia de seguretat independent només de les fotos. Exportar desa un únic arxiu `.json` amb totes les fotos incrustades en base64 (no una referència als arxius d'imatge originals, així que segueix sent vàlid encara que després esborris o moguis els originals). Importar fusiona les fotos d'aquell arxiu amb el document obert actualment, sobreescrivint només els personatges/localitzacions amb el mateix nom.

### 🔒 Eliminar totes les fotos
Un control bloquejat per seguretat, a la part inferior de la pestanya Personatges, permet esborrar totes les fotos de personatges i localitzacions del document actual. Per defecte està desactivat — cal desbloquejar-lo primer — i sempre demana confirmació abans d'esborrar res, ja que l'acció no es pot desfer.

---

## Instal·lació

Instal·la **Table Read Tools** des de la **Plugin Library** de Beat i obre'l des del menú **Tools**.

Per instal·lar-lo manualment:

1. Copia la carpeta sencera `Table Read Tools.beatPlugin` dins la carpeta de plugins de Beat:
   ```
   ~/Library/Containers/fi.KAPITAN.Beat/Data/Library/Application Support/Beat/Plugins/
   ```
2. Reinicia Beat si ja el tenies obert.
3. Obre un guió i vés a **Tools → Table Read Tools**.

## Com es guarden les dades

Tot (fotos, ordre dels personatges, idioma triat) es desa dins la configuració pròpia del document del guió (fotos, ordre — així viatgen sempre amb l'arxiu `.fountain`) o com a preferència personal de l'usuari (idioma de la interfície, mida de la finestra — així es mantenen iguals entre guions diferents al teu Mac). Res no s'envia mai per xarxa; el plugin funciona totalment sense connexió, dins de Beat.

## Dreceres de teclat (Table Read Mode)

| Tecla | Acció |
|---|---|
| → o Espai | Línia següent |
| ← | Línia anterior |

Controls en pantalla: **⏮** torna al principi de tot de la llista de l'escena, **▶ / ⏸** activa o pausa la reproducció automàtica, **→** avança una línia manualment.

## Llicència

Table Read Tools es distribueix sota la llicència [GPL-2.0-or-later](LICENSE).
