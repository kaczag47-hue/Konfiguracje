# ADR-001: User authorization

## Status

Draft

## Context

Mamy wiele gotowych rozwiązań, które załatwiają za nas rejestracje, logowanie, refresh tokeny, MFA,
Rozwiązania takie to np: Boilerplate kodu, AWS Cognito, Supabase. Odpowiedź nie jest tak oczywista
ze względu natury startapów - niepewność, ograniczony budżet, nieznane koszta i potrzebę szybkiego wdrażania zmian

Wiedząc, że zespół może nie być duży, a chcemy być skoncetrowani na kolejnych iteracjach
produktu, łatwości skalowania, bezpieczeństwie oraz utrzymanie zespołu w kolejnych etapach.

- Mamy różne typy userów, z różnymi modelami danych i różną częstotliwością logowania.
    - Business unit(Lokale, Sponsorzy, Franczyzy)
    - Streamerzy
    - Gracze/Widz/Uczestnik
    - Partnerzy(np: Instreamly)

Z tego powodu system autoryzacji musi:
- Obsługiwać różne role i poziomy dostępu
- Być gotowym na obsługę klientów "korporacyjnych" np; Costa Coffe, dla których ważne mogą być
    - Wyskokie standardy bezpieczeńśtwa zgodne z certyfikacją SOC2, ISO27001, a może nawet i HIPAA
    - Przechowywanie zgodnie z GDPR/RODO
    - Multi-tentant(Separacja danych)
    - Mogą prosić o logi audytowe
    - Integracja z ich SSO
- Wymagać od nas minimalnej obsługi bezpieczeństwa po stronie zespołu
- Gotowe na obsługę mikroserwisów i serverless

## Decision

TODO

## Consequences

### Positive

- ✅ Pełne wsparcie Enterprise-ready
- ✅ REST API + dashboard


### Negative

- ❌ Czas wdrożenia dłuższy przez setup IAM, Poole
- ❌ Niezbyt intuicyjny interface



### Risks

- Risk of wrong domain boundaries (mitigated by iterative refinement)
- Risk of over-engineering small projects (mitigated by starting simple)

## Alternatives Considered

### Alternative 1: Cogito

Traditional layered architecture (controllers, services, repositories).
- ❌ Doesn't scale well organizationally
- ❌ Harder to maintain clear boundaries

### Alternative 2: Pure Code / Boilerplate

Complete service decomposition without domain modeling.
- ❌ Can lead to distributed monolith
- ❌ Missing business context in structure

## References

- [Why I Switched From AWS Cognito To Supabase The Week Before My Startup Launched](https://dev.to/sleeplessfox/why-i-switched-from-aws-cognito-to-supabase-the-week-before-my-startup-launched-269c)
- [Paid 360$ for AWS Cognito in December. Just switched to Supabase server side auth](https://www.reddit.com/r/Supabase/comments/1i27oow/paid_360_for_aws_cognito_in_december_just/)
- [Supabase Part 3: Multi Tenancy](https://arda.beyazoglu.com/supabase-multi-tenancy)
- [Multi-Tenancy Architecture - System Design](https://www.geeksforgeeks.org/system-design/multi-tenancy-architecture-system-design/)
- [supabase-vs-aws-pricing](https://www.bytebase.com/blog/supabase-vs-aws-pricing/)