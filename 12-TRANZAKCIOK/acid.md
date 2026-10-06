# ACID

| Betű | Jelentés | Egyszerűen |
|------|----------|------------|
| **A**tomicity | Atomicitás | Vagy minden sikerül, vagy semmi |
| **C**onsistency | Konzisztencia | Constraint-ek / szabályok megmaradnak |
| **I**solation | Elszigetelés | Párhuzamos tranzakciók nem „látnak félkész” állapotot (szintek szerint) |
| **D**urability | Tartósság | COMMIT után megmarad (háttértár) |

## ZH-felismerés

- „Visszavonható egység” → tranzakció / atomicitás  
- „Véglegesítés után is megvan” → durability  
- „Másik session nem látja” → isolation (szint függő)
