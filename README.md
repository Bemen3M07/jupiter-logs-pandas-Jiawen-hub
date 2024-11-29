[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/ULiw8LbN)
# Not Empty
Exercici 1:
tail -f /etc/mp/fitxer.log Per analitzar els logs de un fitxer.log. 
grep "paraula_a_cercar" /etc/mp/fitxer.log Per trobar la paraula encronquet dintre del fitxer log.


El concepte logging és molt important en la programació, alhora que està estrictament
relacionat amb el tema que estem treballant. Un log en el nostre àmbit vindria a ser
un fitxer que conté dades relacionades amb els principals esdeveniments i successos
que ocorren en un programa o en un sistema operatiu, així doncs, ja sigui per saber
en quin punt hem tingut un error, perquè l&#39;execució del programa no ha anat bé, o
quina sèrie de passes ha seguit una persona mentre utilitzava la nostra aplicació i
moltes altres utilitats, els Logs són vitals al món del software.






Exercici 2:
Que creieu que és millor mostrar els logs per exemple a la terminal durant l'execució del programa o bolcar-los en un fitxer de text? 
Afegiu al readme.md del repositori aquesta pregunta amb la seva reposta 

És molt més millor i practic revisar els logs bolcats en fitxer de text perqué d'aquesta forma és molt més fàcil de poder debuggear
ja que en un escenari real amb un programa certament complex el terminal pot esta "spamejad" per logs i errors i no seria gaira fàcil de llegir 
i entendre el que esta passant.


**Mètode**                                                                                                                                                                              
|------------------------------------------------------    |
| **Configuració per defecte del mòdul `logging`**         |                         
| **Instanciar un objecte logger i parametritzar-lo**      |
| **Instanciar un logger des d’un fitxer de configuració** | 

| **Exemple**                                                                                                                                  |------------------------------------------------------------------------------------------------------|
| ```python<br>import logging<br>logging.basicConfig(level=logging.INFO)<br>logging.info("Missatge informatiu")<br>```     

| ```python<br>logger = logging.getLogger("app_logger")<br>handler = logging.FileHandler("app.log")<br>logger.addHandler(handler)<br>```      

| - Fitxer de configuració (JSON):<br>`{"version":1,"handlers":{"file":{"class":"logging.FileHandler","filename":"app.log"}}}`<br>- Programa:<br>`logging.config.dictConfig(config)` 

| **Avantatges**       
|------------------------------------------------------------------------------------------------------|
| - Fàcil d'implementar<br>- Ideal per a projectes petits<br>- No cal configurar explícitament *handlers* ni *formatters*. |
| - Alta flexibilitat<br>- Suporta múltiples *handlers* i configuracions avançades.<br>- Pot separar el *logging* per mòduls. |
| - Centralitza configuracions complexes<br>- Pot ser fàcilment modificable sense tocar el codi<br>- Ideal per a grans aplicacions. |

| **Desavantatges**                                               
| - Limitat en funcionalitat<br>- Difícil d'adaptar en aplicacions grans<br>- No suporta configuracions avançades. |
| - Necessita més codi per a configuració inicial<br>- Pot ser confús si no està ben documentat.          |
| - Afegir fitxers externs pot complicar la distribució<br>- No és intuïtiu si no es coneixen els formats. |