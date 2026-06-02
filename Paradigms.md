Object-Oriented Programming (OOP) — classes, encapsulation of state (_calculator, _history), and method-based behavior on Calculator, CalculatorService, XmlHistoryRepository

Abstraction — ICalculator, IHistoryRepository, ICalculatorService define contracts via ABC and @abstractmethod, hiding implementation details from consumers

Dependency Injection — CalculatorService receives its dependencies (ICalculator, IHistoryRepository) via constructor rather than creating them internally

Interface Segregation / Programming to an Interface — CalculatorService depends on abstract types, not concrete classes, enabling substitution (e.g., swapping XmlHistoryRepository for another storage backend)

Immutable Value Objects — CalculationRecord uses @dataclass(frozen=True), making it a value object with no identity beyond its field values

Repository Pattern — IHistoryRepository / XmlHistoryRepository isolate persistence logic behind a load/save interface, separating data access from business logic

Service Layer Pattern — CalculatorService orchestrates the calculator and repository, acting as an application-layer facade

Functional-style dispatch — operation_map in calculate() uses a dictionary of functions to replace a chain of if/elif conditionals
