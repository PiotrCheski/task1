# Security By Design - Zadanie 1 - Domain Driven Design


1. **Króki opis zadania**
Celem zadania było zamodelowanie fragmentu bezpiecznej aplikacji bankowej wykorzystując zasady Domain Driven Design. W ramach zadania zdefiniowano Bounded Contexts (KontoBankowe, Przelewy, Obligacje), a następnie określono Agregaty, Encje i Obiekty Wartości. Przygotowano także graficzną reprezentację modelu domeny. Na poniższym rysunku Agregaty oznaczono za pomocą okręgów, prostokąty reprezentują Encje, natomiast elipsy to Obiekty Wartości.

2. **Graficzna reprezentacja modelu**

<img width="2231" height="1231" alt="DDD drawio" src="https://github.com/user-attachments/assets/2aab4a26-3c95-4d18-8ca9-9fc3569bff24" />

4. **Opis części modelu i przyjęte założenia**

| Bounded Context  | Opis                                                                                          |
| ---------------- | --------------------------------------------------------------------------------------------- |
| **KontoBankowe** | Realizacja operacji związanych z podglądem aktualnego stanu swoich kont przez klientów banku. |
| **Przelewy**     | Realizacja operacji wysyłania i odbierania przelewów przez klientów banku.                    |
| **Obligacje**    | Realizacja operacji dotyczących zakupu i zarządzania obligacjami przez klientów banku.        |

---

**Agregaty**
- **WyświetlKontoBankowe**  
- **ZlećPrzelew**  
- **KupObligacje**  

---

**Encje i ich atrybuty**
- **Klient**  
  - NumerIDKlienta  
  - NumerKontaKlienta  
  - ImięKlienta  
  - NazwiskoKlienta  
- **Przlew**  
  - NumerIDPrzelewu
  - NumerKontaNadawcy  
  - NumerKontaOdbiorcy  
- **Obligacje**  
  - NumerIDObligacji
  - CenaObligacji  
  - TerminWykupu  

---

**Obiekty Wartości**
- **StanKontaKlienta**  
- **StanKontaKlientaDoPrzelewu**  
- **StanKontaKlientaDoZakupuObligacji**  
- **KwotaWychodzacegoPrzelewu**  
- **LiczbaKupowanychObligacji**  


W modelu założono, że informacja o stanie konta będzie występowała w każdym z trzech kontekstów. Jednocześnie w każdym z nich będzie ona reprezentowana przez inny obiekt wartości, ponieważ w przypadku StanKontaKlienta chodzi o informację ile pieniędzy ma klient na koncie wyłącznie w celu informacyjnym w obszarze kontekstu KontoBankowe. Jednocześnie StanKontaKlientaDoPrzelewu i StanKontaKlientaDoZakupuObligacji (odpowiednio w kontekście Przelewy i Obligacje) będą pozwalać realizować cele związane z np. weryfikacją, czy klient ma wystarczająco środków do zlecenia przelewu lub zakupu obligacji.
