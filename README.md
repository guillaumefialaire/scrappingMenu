### Comment lancer

- ouvrir l'inspecteur sur la page du navigateur (f12 ou clic droit inspecter) sur le menu
- chercher la valeur de la classe du menu que tu veux scrapper (ex : container)
- aller dans l'onglet console de l'inspecteur
- coller la fonction dans la console
- lancer extractHrefAndContent([classe]) avec [classe] le nom de la classe du menu 

### FONCTION A COPIER COLLER
```
function extractHrefAndContent(classe){
let array = [];
let menu = document.querySelector(classe);
let links = menu.querySelectorAll("a");
links.forEach(link => {
        let tmp = link.getAttribute("href")
        let txt = link.textContent;
        let txt2 = txt.replaceAll('\n','');
        let obj = [
            tmp,
            txt2
        ];
        array.push(obj);
    });
    let str = JSON.stringify(array);
    let a = str.replaceAll("],","]\n");
    let b = a.replaceAll('"',"");
    let c = b.replaceAll('[',"");
    let d = c.replaceAll(']',"");
    let e = d.replaceAll(',',' , ');
    console.log(e);   
}
```
