# Performance audit Github
<!-- Geef je project een titel en schrijf in één zin wat het is -->
![image](https://user-images.githubusercontent.com/30351629/165138429-9dce3c0f-8638-42db-a532-2a83eda8faa3.png)



## ContentAudit
Beschrijf de website die je hebt geanalyseerd en de datum dat je hebt getest. Voeg de url en een screenshot toe. 

Website: http://github.com  
Datum: 25-04-2022  

![Website](https://user-images.githubusercontent.com/30351629/165062244-42a19ceb-b96e-43e4-96ad-4c762eae3f6c.png)


### All

**Properly size images**
Sommige images die worden gebruikt zijn tussen de 40px en 60px breed. Terwijl de orginele image 400x400 is. Hierdoor wordt er een grotere image geladen dan dat ze daadwerkelijk nodig hebben.

### First Contentful Paint (FCP)
De performance score van Github is 82 op Desktop. Er zijn een paar verbeter punten waarmee ze de score omhoog kunnen krijgen.

**Eliminate render-blocking resources**
Er zijn bepaalde resources die worden ingeladen en daardoor de FCP blocken. Deze kunnen worden opgelost door bijvoorbeeld inline styling te gebruiken doormiddel van een ```<style></style>``` tag of een ```<script></script>```

**Reduce unused CSS**
Er zijn een paar regels in de CSS bestanden van github die niet worden gebruikt. Als ze deze zouden verwijderen zou de FCP sneller moeten laden.

**Serve images in next-gen formats**
Aangezien de images die worden geladen al iets te groot zijn, zouden ze dit ook kunnen aanpakken door next gen image formats te gebruiks zoals WEBP of AVIF. Deze type images zijn beter gecompressed. Dit betekent dat de images sneller geladen kunnen worden en minder data verbruiken.


### Time to Interactive (TTI)
Om de TTI snelheid te verbeteren kan Github een paar dingen doen:

- De render-blocking resources fixen waardoor de FCP sneller word gemaakt en ze ook sneller door kunnen naar de TTI
- De JavaScript execution time verlagen (denk aan compression of minify)

### Speed Index
De speed index kan worden verbeterd door de FCP te verbeteren.

### Total Blocking Time (TBT)

**Remove duplicate modules in JavaScript bundles**
In heel veel JS bestanden van Github zijn er modules (waaronder node_modules) die worden ingeladen die niet worden gebruikt. Hierdoor worden onnodige bytes ingeladen. Als ze deze zouden verwijderen zouden ze hun TBT kunnen verbeteren.


### Largest Contentful Paint (LCP)
**Eliminate render-blockink resources**
Er zijn bepaalde resources die worden ingeladen en daardoor de LCP blocken. Deze kunnen worden opgelost door bijvoorbeeld inline styling te gebruiken doormiddel van een ```<style></style>``` tag of een ```<script></script>```

**Reduce unused CSS**
Er zijn een paar regels in de CSS bestanden van github die niet worden gebruikt. Als ze deze zouden verwijderen zou de LCP sneller moeten laden.

**Reduce unused JavaScript**
Er zijn een paar client side javascript bestanden die niet worden gebruikt. Dit zouden ze kunnen verbeteren door deze niet in te laden op deze pagina.

### Cumulative Layout Shift (CLS)
De tab container (aka de feed), de sidebar en de footer zijn grote elementen die zorgen voor een grote layout shift. Ze zouden dit beter kunnen opdelen in meer kleinere elementen.


## Bronnen
[web.dev](https://web.dev/)
[Google Lighthouse](https://developers.google.com/web/tools/lighthouse)

## Licentie

![GNU GPL V3](https://www.gnu.org/graphics/gplv3-127x51.png)

This work is licensed under [GNU GPLv3](./LICENSE).
