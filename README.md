# 🍽️ ProjectAlpha Android - Social Dining & Discovery Platform

> **Note:** This is a commercial project currently in development. The source code is hosted in a **Private Repository**. This showcase repository demonstrates the engineering standards, UI/UX implementation, and architectural patterns used in the project. **This project still in progress**.

---

## 📱 Project Overview
**ProjectAlpha** is a consumer-facing (B2C) Android application that allows users to discover restaurants, create curated dining lists, write reviews, and interact with a social foodie community. Unlike standard utility apps, ProjectAlpha focuses heavily on **immersive user experience**, **fluid animations**, and **social connectivity**. 
>*It's the mobile port of ProjectAlpha Web Application *(made by our team as a project which is still in progress)* and also my very first Android Application.*

---

### 🎥 UI & Animation Demo
* [Demo Preview - 1 *Main Flow*](https://imgur.com/imToFFm)
* [Demo Preview - 2 *Login and Register Flow*](https://imgur.com/fcbU4OT)

---

## 🛠 Tech Stack & Highlights

* **Architecture:** Clean Architecture (Modularized: Presentation, Domain, Data)
* **UI Framework:** [Jetpack Compose](https://developer.android.com/jetpack/compose) with Material3
* **State Management:** MVVM + MVI Pattern (using `UiState` data classes)
* **Animations:** Animated headers, Scrollable tabs, and some animated interactive UI modules *(e.g., Fortune Wheel)*.
* **Local Storage:** [Room Database](https://developer.android.com/training/data-storage/room) & DataStore (Proto)
* **Network:** Retrofit + OkHttp (Authenticated requests with Token Management)
* **DI:** Hilt (Dagger)
* **Security:** Encrypted Shared Preferences & Auth Interceptors

---

---

## 🎨 Key Features

### 1. Advanced UI & Animations
The app utilizes advanced Compose animation APIs to create a seamless user journey.
* **Advanced Animation Components** Components like `AnimatedHeader` in Business Screen and `AnimatedLoadingScreen` which has an animated logo *(after loading logo moves to the topbar)* and animated presentation of features.*(they are presentating with a fluid animation.)*
* **Interactive Elements:** Features like the "FeastMyst" for gamified user engagement.
* **Adaptive Layouts:** Components like `AdaptiveTopBar` ensure consistency across different screen sizes.

### 2. Social & Content Management
* **FeastList:** Users can create, edit, and delete public/private restaurant lists using complex dialog flows.
* **FeastMyst:** Users can use a wheel to select one business to hangout with their friends.
* **Review System:** Full CRUD operations for user reviews with rich text support.
* **Profile System:** Dynamic user profiles with editable stats and settings.

### 3. Robust Data Layer
* **Offline Caching:** Uses Room Database (`BusinessDao`, `AppDatabase`) to cache restaurant data for offline viewing.
* **Type-Safe DataStore:** Manages user sessions and preferences securely using Proto DataStore.

---
## 🧩 Architectural Snippets

**1. Animation Logic (Compose):**
*Demonstrating the ability to handle complex UI states and animations.*
```kotlin
// Example logic from FeatureAnimation.kt
@Composable
fun FeatureAnimation(isVisible: Boolean) {
    AnimatedVisibility(
        visible = isVisible,
        enter = fadeIn() + slideInVertically(),
        exit = fadeOut() + slideOutVertically()
    ) {
        // Complex UI Content 
    }
}
```
**2. Clean Architecture (Repository Pattern):**
*Separation of concerns ensuring testability.*
```kotlin
class BusinessRepositoryImpl @Inject constructor(
    private val api: BusinessAPI,
    private val dao: BusinessDao
) : BusinessRepository {
    override fun getBusinessDetails(id: String): Flow<Resource<BusinessDetail>> = flow {
        // Logic to fetch from DB first, then API (Single Source of Truth)
    }
}
```
---

# 👨‍💻 Contact

I am available to discuss the technical architecture and development process of this project.

* **LinkedIn:** [İzzet Han ÇELİKDEMİR](https://www.linkedin.com/in/izzet-han-çelikdemir-157184309)
* **Email:** [ihancelikdemir@gmail.com](mailto:ihancelikdemir@gmail.com)

---

