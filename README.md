# Esercizio CheckTelefono Morelli Giovanni 5H

### Descrizione:
Ricevuto come parametro un vettore di string, ritornare al chiamante la prima stringa che assomiglia molto ad un numero di telefono cellulare italiano ovvero:

che inizia con +39 (esattamente lungo 13)
oppure con 0039 (esattamente lungo 14)
oppure con un 3 (esattamente lungo 10)
Se il numero non viene trovato, ritornare stringa vuota ""

Ad esempio. Se arriva "05417373", "3367726712", "778823" Tornare "3367726712"

Se arriva "33677267", "33677232", "778823" Tornare ""

Se arriva "", "05417723", "+391231231234" Tornare "+391231231234"

Se arriva "3", "05417723", "00391231231230" Tornare ""

etc

### Svolgimento:

Apriamo il progetto dezippato su Visual Studio Code e creiamo una classe  chiamata "Telefono" dove all'interno si trova il metodo "Check":
```
public static class Telefono
{
    public static string Check(string[] vettore)
```
Questo è il metodo principale che prende un vettore (array) di stringhe come parametro e restituisce una stringa. Il suo scopo è trovare la prima stringa nel vettore che rappresenta un numero di telefono italiano valido.

Grazie al ciclo foreach controlliamo ogni numero di telefono contenuto nel vettore
```
foreach (var numero in vettore)
        {
            if (IsValidNumeroTelefono(numero))
            {
                return numero;
            }
```

Per il controllo della validità del numero occorre la seguente funzione:
```
private static bool IsValidNumeroTelefono(string numero)
    {
        return (numero.Length == 13 && (numero.StartsWith("+39") || numero.StartsWith("0039"))) ||
               (numero.Length == 14 && numero.StartsWith("0039")) ||
               (numero.Length == 10 && numero.StartsWith("3"));
```
Se troviamo un numero di telefono italiano valido, lo restituiamo come risultato della funzione Check.

Se non troviamo nessun numero di telefono italiano valido, restituiamo una stringa vuota come risultato.
