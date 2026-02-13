# Technical Documentation

## Tech Stack and Architecture
iOS uses SwiftUI + GRDB + Firebase; Android uses Kotlin/Compose + Room + Firebase; backend uses Firestore rules/indexes.  
The architecture is local-first: lists/reminders sync to Firestore, while occurrences stay local for reliable notifications.  
Conflicts are resolved with deterministic last-write-wins using timestamps and device IDs.

## RevenueCat Implementation
Both apps use RevenueCat entitlement `Premium` (offering `default`) to determine paid access.  
Premium status unlocks reminder/list creation beyond free limits, and restore purchases is available in Settings.  
On iOS, RevenueCat identity is synced with Firebase UID; Android currently uses the configured RevenueCat client flow.
