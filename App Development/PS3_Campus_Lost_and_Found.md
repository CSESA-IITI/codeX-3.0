# Campus Lost & Found – PS3

**Difficulty:** Intermediate (Induction Challenge)

## Problem Statement

Items misplaced around campus are often reported through scattered messages, making them hard to find later. Build a mobile app where students can post lost or found items, browse reports, and connect relevant listings. The app should remain small enough to complete as an induction project.

## Objectives

- Build a multi-screen app with structured data and meaningful user flows.
- Practice searching, filtering, and updating records.
- Introduce a manageable amount of backend or local-database integration.

## Features

- Create a **Lost** or **Found** listing with item name, description, category, location, and date.
- Attach an item photo (camera or gallery); a placeholder is acceptable when no photo is provided.
- Browse listings and filter by Lost/Found, category, or location.
- Search listings by keywords.
- Open a detailed view of an item and see its status.
- Mark a listing as **Resolved** and prevent it from appearing in active results by default.
- Provide a way to contact the poster (for example, an email address or in-app contact detail).
- Store listings so they remain available after restarting the app.

## Tech Stack (Example)

- **Frontend:** Kotlin / Java (Android Studio), Flutter (Dart), or React Native
- **Data:** Firebase Firestore / Supabase, or SQLite / Room for an offline single-device version
- **Images (optional):** Firebase Storage / Supabase Storage or local file storage

## Notes

- A functional single-device prototype is acceptable; a shared online database is a bonus, not a requirement.
- Login, chat, push notifications, and automatic item matching are **not** required.
- If using a shared database, ensure users cannot arbitrarily edit other users' listings.
- Focus on a complete create → browse/search → view → resolve flow rather than adding extra features.
