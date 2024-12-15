#  Sprawdzian 1
```
2 40%  10   ->  14
3 51%  15   ->  21
4 75%  22   ->  26
5 90%  27   ->  28
6 98%  29   ->  30
```

* Wszystkie pliki dodać w katalogu `src`
* Można używać notatek i zadań z lekcji
* Kod ma się kompilować
* Nie można korzystać z internetu
* Nie można korzystać z co-pilot lub innych narzędzi AI do generowania kodu

---------------------------------------
1. [_4_] Stworzyć hierarchię klas w pakiecie `edu.technischools.java.vehicles`, jak na rysunku poniżej,
``` 
         Vehicle 
      /           \
   Plane           Bike 
     |              |   
CargoPlane      CargoBike  
```

Gdzie:

* Klasa  `Vehicle` jest klasą abstrakcyjną zawierającą pola
    * `brand` - przechowujące nazwę producenta-typu znakowego
    * `model` - przechowujące model urządzenia-typu znakowego
* Klasa `Plane` zawiera pola:
    * `noOfSeats` - typu całkowitoliczbowego, przechowującą ilość miejsc
    * `fuelConsumption` - typu zmiennoprzecinkowego, przechowującą zużycie paliwa
* Klasa `Bike` zawiera pola:
    * `wheelSize` - typu całkowitoliczbowego

Dla wszystkich pól stworzyć gettery i settery oraz konstruktory (minimum jeden) - mogą być bezparametrowe, mogą być ze wszystkimi parametrami.

2. [_2_] Nadpisać metodę `toString()` w klasie `Vehicle` tak by zwracała model i producenta.

3. [_2_] Stworzyć interfejs `FreightTransporter` z metodami
    * `int getLoad()`
    * `void setLoad(int load)`

4. [_3_] Dodać interfejs `FreightTransporter` do klas `CargoPlane` i `CargoBike` i zaimplementować brakujące metody, oraz dodać pole `load`

5. [_2_] Nadpisać metodę `toString()` w klasach implementujących ten interfejs, tak by dodatkowo wypisać zmienną `load`

6. [_4_] W pakiecie `edu.technischools.java` stworzyć klasę `VehicleShowroom` wraz z metodą `public static void main(String[] args)`, w metodzie :
    * stworzyć po 2 instancje klas `Plane`, `CargoPlane`, `Bike` i `CargoBike`
    * ustawić **wszystkie** pola w klasach-poprzez konstruktory lub settery

7. [_2_] Stworzyć listę `vehicles` i dodać do nej wszystkie stworzone instancje

8. [_4_] Stworzyć mapę `vehiclesByMean`, gdzie kluczem jest ciąg znaków *air* i *road*, a wartością zbiór typowany `Vehicle`. Przeiterować po elementach listy `vehicles` i dodać do odpowiednich elementów mapy - *air* jeśli klasa rozszerza klasę `Plane` i *road* jeśli rozszerza klasę `Bike`.

9. [_1_] Używając lambdy, wypisać na konsolę elementy zbioru z mapy pod kluczem *road*.

10. [_4_] Stworzyć klasę `LoadChecker` implementującą interfejs `java.util.function.Predicate<Vehicle>`, która jako parametr konstruktora przyjmuje zmienną `minLoad` całkowitoliczbową, która z metody `test` zwróci:
* `true` - jeśli parametr metody `test` implementuje interfejs `FreightTransporter` i metoda `getLoad()` zwraca wartość większą bądź równą niż parametr przekazany przez `minLoad`
* `false` - w przeciwnym wypadku-parametr metody `test` nie implementuje podanego interfejsu lub metoda `getLoad` zwraca wartość mniejszą niż parametr `minLoad`

11. [_2_] Używając klasy powyżej usunąć wszystkie pojazdy ze zbioru pod kluczem *air* w mapie-należy użyć metody `removeIf` 
