Project Structure Overview:

To ensure a well-organized, maintainable, and testable codebase, this project leverages Clean Architecture. The structure is divided into three key layers, each serving a distinct purpose:

Presentation Layer:

Responsible for user interface management and event-driven logic.

Utilizes BLoC (Business Logic Component) for handling UI state.

Triggers domain logic through UseCases and listens for outcomes.

Presents different UI states such as loading indicators, success views, or error messages based on the results.

Data Layer:

Acts as the bridge between external services (e.g., APIs) and internal domain logic.

Contains Models, DataSources, and Repository Implementations.

Transforms raw external data into structured domain-friendly formats (Entities).

Responsible for fetching, parsing, and preparing data for the domain layer.

Domain Layer:

The heart of the application containing core business rules and logic.

Comprises Entities, UseCases, and abstract Repository Interfaces.

Completely independent from UI and data sources—framework-agnostic.

Provides a stable and reusable foundation for business operations.

Feature Example: News Module

A practical illustration of Clean Architecture principles can be seen in the News feature:

news_bloc.dart (Presentation Layer)
Handles all News-related UI events and emits corresponding UI states.

get_top_headlines.dart (Domain Layer)
Executes the use case of retrieving top headlines from the repository.

news_repository.dart (Domain Layer)
Declares the expected functionality of a news repository without tying it to implementation.

news_repository_impl.dart (Data Layer)
Implements the repository interface, fetching data via API and converting it into domain Entities.

SOLID Principles in Action:

The system adheres to the SOLID principles to promote clean, modular, and flexible code:

Single Responsibility: Classes are designed to handle one specific job.

Open/Closed: Functionality can be extended without altering existing code.

Liskov Substitution: Abstract repositories ensure implementations can be swapped easily.

Interface Segregation: Contracts are broken down into focused, minimal interfaces.

Dependency Inversion: Domain and UI layers depend on abstractions, not concrete logic.
