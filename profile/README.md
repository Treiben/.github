Propel provides feature flag libraries that separate code deployment from feature releases. Developers define flags as strongly-typed classes, product owners configure release timing and targeting through a management interface.

[Propel Feature Flags](https://github.com/Treiben/propel-feature-flags-csharp) • [Propel Dashboard](https://github.com/Treiben/propel-dashboard) • [Propel CLI](https://github.com/Treiben/propel-cli)

---

## Overview

Propel is a feature flag system designed around two core principles:

**Type safety**: Feature flags are defined as classes in code, not strings in configuration files. This provides compile-time validation, IDE support for navigation and refactoring, and explicit visibility into what flags exist and where they're used.

**Separation of concerns**: Developers define which features exist and deploy code. Product owners control when and how features are released - scheduling, targeting, gradual rollouts - without requiring code changes or developer involvement.

This approach enables true continuous deployment: code can be deployed at any time with features disabled by default, while release timing is managed independently through configuration.

---

## Projects

### [Propel.FeatureFlags](https://github.com/Treiben/Propel.FeatureFlags)
Core library for .NET applications (.NET Standard 2.0+, .NET Framework 4.6.1+, .NET Core, .NET 5+)

Feature flag library with PostgreSQL and SQL Server persistence, Redis caching, and support for scheduled releases, time windows, user/tenant targeting, percentage rollouts, and custom targeting rules.

**Status:** v2.2.1 - Available on NuGet

### [Propel Dashboard](https://github.com/Treiben/propel-dashboard)
Management interface for feature flags - Avaliable on DockerHub

Web application for configuring flag behavior - schedules, targeting rules, rollout percentages - and monitoring flag usage across applications.

### [Propel CLI](https://github.com/Treiben/propel-cli)
Database migrations and limited management interface for feature flags

**Status:** v1.1.2-beta.1.2 - Available on NuGet

---

## Architecture

**Auto-deployment**: Flags defined in code automatically register in the database on application startup. No separate deployment or migration steps required.

**Default-off pattern**: New flags start disabled by default. Code deploys safely, product owners enable features when ready.

**Evaluation modes**: Simple on/off toggles, scheduled activation, operational time windows, user/tenant targeting, percentage-based rollouts, and custom rule-based targeting.

**Caching**: In-memory and Redis distributed caching to minimize database queries during flag evaluation.

---

## Naming

**Treiben** follows a multilingual naming philosophy:

- **Treiben** (German) - Organization name. To propel, to drive forward.
- **Propel** - Product name and code namespace.
- **Knara** (Armenian) - Sister libraries focused on compile-time safety.
---

## Related Projects

Sister libraries under the [Knara](https://github.com/tasriyan) organization focus on preventing common enterprise bugs through compile-time enforcement:

- **[Knara.MultiTenant.IsolationEnforcer](https://github.com/tasriyan/Knara.MultiTenant.IsolationEnforcer)** - Roslyn analyzers that prevent cross-tenant data leaks
- **[Knara.UtcStrict](https://github.com/tasriyan/Knara.UtcStrict)** - Enforces UTC-only DateTime handling to eliminate timezone bugs

Where Knara prevents mistakes through enforcement, Treiben enables flexibility through separation of concerns.

---

## License

Licensed under the Apache License, Version 2.0. Copyright 2025 Tatyana Asriyan
