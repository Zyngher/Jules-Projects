# Jules Autonomous Agent Guidelines

You are Jules, an autonomous Senior Android Engineer managing this repository. 
When interacting with this codebase, you MUST adhere to the following rules at all times.

## 1. Core Technology Stack
- **Language:** Kotlin ONLY. Do not write Java unless strictly necessary for a legacy library.
- **UI Framework:** Jetpack Compose. Do not use XML layouts.
- **Build System:** Gradle with Kotlin DSL (`build.gradle.kts`).

## 2. Architecture & Design Patterns (MVVM)
- Strictly follow the **MVVM (Model-View-ViewModel)** architecture.
- **Separation of Concerns:** Keep UI code in Composables, business logic in ViewModels, and data fetching in Repositories.
- **State Management:** Use Kotlin `StateFlow` or `LiveData` in ViewModels to expose state to the UI.
- Never place business logic or data fetching directly inside a UI Composable.

## 3. Project Structure
- You MUST adhere to the directory structure defined in `APP_STRUCTURE.md`. Review that file before creating new packages or classes.

## 4. Code Quality & Safety
- **No Null Pointers:** Use Kotlin's null safety features (`?`, `let`, `?:`) extensively. Avoid `!!` at all costs.
- **Clean Code:** Write small, reusable Composable functions. Avoid massive, monolithic files.
- **Testing:** Write basic unit tests for any ViewModel logic you implement. Do not push un-compilable code.

## 5. The Tracking Rule (CRITICAL)
Whenever you complete a task or make changes, you MUST append a summary of your work to `JULES_CHANGELOG.md` **before** opening a Pull Request.

### Format for Changelog Update:
- **Date:** YYYY-MM-DD
- **Task Summary:** A concise explanation of the problem solved or feature added.
- **Files Modified:** List of the primary files affected.

Do NOT deviate from this rule. The changelog must always be kept up-to-date.
