# Treiben

**Type-safe feature flags that empower product owners**

*Treiben* (German: to propel, to drive) - Decouple deployment from release. Let developers deploy, let POs control when features go live.

[Propel.FeatureFlags](https://github.com/Treiben/Propel.FeatureFlags) • [Dashboard](https://github.com/Treiben/Propel.FeatureFlags.Dashboard)

---

## The Problem

**Magic strings everywhere.** Config files full of cryptic strings nobody understands. Is `"new-checkout"` a feature flag? A business rule? Who knows? One typo and features break silently in production.

**Developers control releases.** Product owners want to schedule a Black Friday launch? They need to file a ticket and wait for a developer to change a config file. Want to roll out gradually to 10% of users? Another ticket. Different targeting rules? More developer work.

**Config files become junkyards.** Years of accumulated strings with unknown purposes. Teams are afraid to delete anything because nobody knows what's still in use or where it's referenced.

**Continuous Deployment couples to Continuous Release.** Every code deployment means every feature goes live immediately, or teams resort to complex branching strategies and delayed deployments to control release timing.

---

## The Solution

Treiben separates deployment from release management.

**Developers define feature flags as type-safe classes** in code. No more magic strings scattered across config files. Compiler validates everything. Find-All-References shows exact usage. When you're done with a flag, delete the class and the compiler tells you everywhere it was used.

**Product owners control releases independently** through a management dashboard. Schedule releases for specific dates. Set up time windows for business hours only. Target specific users or tenants. Roll out gradually to percentages. Configure complex targeting rules. All without touching code or filing tickets.

**Clean codebases.** Explicit flags in code, not ambiguous strings in config. Everyone knows what's a feature flag versus permanent business configuration. Cleanup is trivial - delete the class, fix compiler errors, done.

**True continuous delivery.** Deploy code whenever you want, disabled by default. Product owners decide when features go live, completely independently from deployment cycles.

---

## Projects

### [Propel.FeatureFlags](https://github.com/Treiben/Propel.FeatureFlags)
Core library for .NET applications (.NET Standard 2.0+, .NET Framework 4.6.1+, .NET Core, .NET 5+)

Type-safe feature flag library with support for PostgreSQL, SQL Server, Redis caching, scheduled releases, time windows, user/tenant targeting, percentage rollouts, and custom targeting rules.

**Status:** Beta - Available on NuGet

### [Propel Dashboard](https://github.com/Treiben/Propel.FeatureFlags.Dashboard)
Web interface for product owners *(in development)*

Manage releases without developer involvement - configure schedules, targeting, rollouts, and monitor feature flag usage across all applications.

### Propel Release
Release management layer *(planned)*

Advanced release orchestration with metrics, approval workflows, and cross-application release coordination for enterprise deployments.

---

## Naming

**Treiben** follows a multilingual naming philosophy:

- **Treiben** (German) - To propel, to drive. The force that moves features forward.
- **Propel** - The product name and code namespace, familiar to developers.
- **Knara** (Armenian) - Lyre. Sister libraries with a different focus.

The sailboat icon represents controlled momentum. Like wind propelling a sailboat forward, feature flags drive releases with precision - developers steer the direction, product owners control the speed.

---

## Related Projects

Sister libraries under the [Knara](https://github.com/tasriyan) brand focus on compile-time safety and preventing common enterprise mistakes:

- **[Knara.MultiTenant.IsolationEnforcer](https://github.com/tasriyan/Knara.MultiTenant.IsolationEnforcer)** - Roslyn analyzers that prevent tenant data leaks with compilation errors
- **[Knara.UtcStrict](https://github.com/tasriyan/Knara.UtcStrict)** - Enforces UTC-only DateTime handling to eliminate timezone bugs

Where Knara prevents mistakes through opinionated enforcement, Treiben empowers teams through flexibility and autonomy.

---

## License

Apache-2.0

Built for teams tired of magic strings and release bottlenecks.
