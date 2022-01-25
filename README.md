# Excercice pour le 26 janvier 2022

>faire afficher sur une carte, 
>les lieux de conservation pour les sculptures d'Auguste Rodin uniquement conservées aux Etat-Unis

## Requête
```
#Sculptures de Auguste Rodin conservées aux Etat-Unis
#defaultView:Map
SELECT ?item ?itemLabel ?lieuconservation ?coord WHERE
{
  ?item wdt:P31 wd:Q860861 . #je cherche des sculptures
  ?item wdt:P170 wd:Q30755 . #tableau de Rodin
  ?item wdt:P17 wd:Q30. #aux Etats-Unis
  OPTIONAL{
  ?item wdt:P276 ?lieuconservation. #lieu de conservation
  ?lieuconservation wdt:P625 ?coord.    
  } 
    SERVICE wikibase:label {bd:serviceParam wikibase:language "en"} # Récuéprer les labels dans la langue de votre choix
}

```
## Résultats

<iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23Sculptures%20de%20Auguste%20Rodin%20conserv%C3%A9es%20aux%20Etat-Unis%0A%23defaultView%3AMap%0ASELECT%20%3Fitem%20%3FitemLabel%20%3Flieuconservation%20%3Fcoord%20WHERE%0A%7B%0A%20%20%3Fitem%20wdt%3AP31%20wd%3AQ860861%20.%20%23je%20cherche%20des%20sculptures%0A%20%20%3Fitem%20wdt%3AP170%20wd%3AQ30755%20.%20%23tableau%20de%20Rodin%0A%20%20%3Fitem%20wdt%3AP17%20wd%3AQ30.%20%23aux%20Etats-Unis%0A%20%20OPTIONAL%7B%0A%20%20%3Fitem%20wdt%3AP276%20%3Flieuconservation.%20%23lieu%20de%20conservation%0A%20%20%3Flieuconservation%20wdt%3AP625%20%3Fcoord.%20%20%20%20%0A%20%20%7D%20%0A%20%20%20%20SERVICE%20wikibase%3Alabel%20%7Bbd%3AserviceParam%20wikibase%3Alanguage%20%22en%22%7D%20%23%20R%C3%A9cu%C3%A9prer%20les%20labels%20dans%20la%20langue%20de%20votre%20choix%0A%7D%0A" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" ></iframe>
