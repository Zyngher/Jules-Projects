# Android App Structure

Jules, when building and adding features to this Android application, you MUST follow this package structure. We use a feature-based package structure combined with MVVM.

## Root Package: `com.zyngher.bacalaureat`

```text
app/src/main/java/com/zyngher/bacalaureat/
│
├── MainActivity.kt        # Entry point of the app, sets up navigation and base theme
├── BacalaureatApp.kt      # Application class (if needed for dependency injection setup like Hilt)
│
├── core/                  # Core logic, base classes, and utilities shared across the app
│   ├── theme/             # Jetpack Compose Theme, Colors, Typography, Shapes
│   ├── navigation/        # Navigation graphs and route definitions
│   └── utils/             # Helper functions, constants, extensions
│
├── data/                  # The Data Layer
│   ├── local/             # Room Database, DataStore, or local JSON files
│   ├── remote/            # Retrofit API interfaces, network models
│   └── repository/        # Repository implementations that combine local and remote data
│
├── domain/                # The Domain Layer
│   ├── models/            # Core business models used across the app (e.g., Subject, Lesson)
│   └── repository/        # Interfaces for the repositories
│
└── presentation/          # The UI Layer (Grouped by Feature)
    ├── home/              # Home Screen feature
    │   ├── HomeScreen.kt          # Compose UI
    │   ├── HomeViewModel.kt       # ViewModel managing state for Home
    │   └── components/            # Composables specific to the Home screen
    │
    ├── subject/           # Subject details feature
    │   ├── SubjectScreen.kt
    │   ├── SubjectViewModel.kt
    │   └── components/
    │
    └── common/            # Reusable Composables (e.g., custom buttons, top bars)
```

## Key Rules for Structure:
1. **Feature-Based Grouping:** Place UI files inside `presentation/<feature_name>/` rather than grouping all ViewModels together and all Screens together.
2. **Domain Models First:** Use the `domain/models` to pass data to the UI. The `data/` models should map to domain models before reaching the ViewModel.
3. **No UI in Data:** The `data` and `domain` packages must have zero dependencies on Android UI classes or Compose.
