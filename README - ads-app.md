Strunktura programu:
- cely projkt je v jednom monorepo
- ma oddelene sucasti pre clienta, server, a scripty

RPO API:
- data z rozlicnych registrov (aj zivnostnici)
- paging (neviem), kosice a presov viac ako 500 (neviem aky paging pouziva)
FETCHOVANIE DAT (SEEDER):
- vytvorenie interface pre fetchnuty json (na uspokojenie typescriptu)
- vytvorenie rpoRaw interface pre zachovanie type safty (konverter cez web), a nasledna transformacia na CompanyData[] na ocistenie dat