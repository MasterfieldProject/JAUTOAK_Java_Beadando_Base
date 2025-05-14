**Java/JUnit Beadandó feladat**

Készítsünk konzolból futtatható Java programot az alábbira.

Adott a resource folderben egy savingsData.csv banki számlákat tartalmazó bemeneti file.
A file első sor a fejléc (header), amely az alábbi mezőket tartalmazza:

- creationDate: számlanyitás dátuma (DD/MM/YYYY formátumban)
- accountTypes: számla típusa (Savings/Money Market/stb.)
- ownershipTypes: számlatulajdonos típusa (Individual/Joint/stb.)
- accountName: számla neve
- openingBalance: számla nyitó egyenlege

Adott a resource folderben egy config.properties file az alkalmazás beállításaival:  
application.filter: bekapcsolható szűrés (on/off)  
application.sort: bekapcsolható rendezés (on/off)  
application.sort.order: rendezés sorrendje (asc/desc)

**Feladatok:**

1) Olvassuk be a savingsData.csv file-t soronként és töltsük be az adatokat egy Saving típusú objektumokat tartalmazó
   listába.
2) Amennyiben a konfigurációs file-ban az application.filter paraméter be van kapcsolva, akkor szűrjük ki a listából a
   hibás dátumformátumú rekordokat.
3) Amennyiben a konfigurációs file-ban az application.sort paraméter be van kapcsolva, akkor rendezzük a listát a
   számlanyitás dátuma szerint az application.sort.order paraméter szerint csökkenő vagy növekvő sorrendbe
4) Írjuk ki a kapott eredmény listát a target/dumpSavings.csv file-ba a bemeneti formátumnak megfelelően

Bónusz feladat (beadása nem kötelező):

5) Amennyiben a rendezés és szűrés is be van kapcsolva írjunk ki egy target/summary.txt file-ba statisztikát:
   num_of_records: kiírt rekordok száma
   total_balance: az összes kiírt rekord nyitó egyenlegeinek összege
   start_creation_date: a legrégebben megnyitott számla dátuma
   end_create_date: a legutoljára megnyitott számla dátuma

**Unit tesztek**

A fentieken túl készíts 3 darab JUnit5 tesztet a DataSource Saving betöltéshez (DataSource.loadSavings())
TC1: Ellenőrizzük, hogy a betöltött lista elemszáma megfelelő
TC2: Ellenőrizzük, hogy a betöltött lista első rekordja megfelelő adatokat tartalmaz
TC3: Ellenőrizzük, hogy a betöltött lista utolsó rekordja megfelelő adatokat tartalmaz

A projekt tartalma:

- hu.masterfield.datatypes.Saving: ez legyen a listához szükséges Saving adattároló típus
- hu.masterfield.utils.ConfigData: ez az osztály konstruktorban töltse be a config.properties file-t és futás közben
  innen legyenek lekérdezhető a konfigurációs paraméterek
- hu.masterfield.utils.DataSource: itt legyen megoldva a Saving-ek betöltése a savingsData.csv-ből és a kiírásuk a
  dumpSavings.csv-be
- hu.masterfield.Feladat: a main-t kell implementálni a fenti feladatok megoldására
- hu.masterfield.test.DataSourceTest: itt kell elkészíteni a JUnit teszteket

A funkcionális helyességen túl ügyelj a kód megfelelő kialakítására: kommentek, strukturáltság, tagoltság, formázás,
stb.

Jó munkát!