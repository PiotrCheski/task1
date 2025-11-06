# Security By Design - Zadanie 1 - Domain Driven Design


1. **Króki opis zadania**
Celem zadania było zamodelowanie fragmentu bezpiecznej aplikacji bankowej wykorzystując zasady Domain Driven Design. W ramach zadania zdefiniowano Bounded Contexts (KontoBankowe, Przelewy, Obligacje), a następnie określono Agregaty, Encje i Obiekty Wartości. Przygotowano także graficzną reprezentację modelu domeny. Na poniższym rysunku Agregaty oznaczono za pomocą okręgów, prostokąty reprezentują Encje, natomiast elipsy to Obiekty Wartości.

2. **Graficzna reprezentacja modelu**

3. **Opis części modelu i przyjęte założenia**

Bounded Context | Opis
- KontoBankowe - Realizacja operacji związanych z podglądem aktualnego stanu swoich kont przez klientów banku.
- Przelewy - Realizacja operacji wysyłania i odbierania przelewów przez klientów banku.
- Obligacje - Realizacja operacji dotyczących zakupu i zarządzania obligacjami przez klientów banku.

Agregaty
- WyświetlKontoBankowe
- ZlećPrzlew
- KupObligacje 

Encje i ich atrybuty
- Klient
    NumerIDKlienta
    NumerKontaKlienta
    ImięKlienta
    NazwiskoKlienta
- Przlew
    NumerID
    NumerKontaNadawcy
    NumerKontaOdbiorcy
- Obligacje
    NumerID
    CenaObligacji
    TerminWykupu

Value Objects
- StanKontaKlienta
- StanKontaKlientaDoPrzelewu
- StanKontaKlientaDoZakupuObligacji
- KwotaWychodzacegoPrzelewu
- LiczbaKupowanychObligacji
