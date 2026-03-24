# Expo to Swift Widget Architecture 🚀

A high-performance reference architecture demonstrating how to seamlessly bridge React Native (Expo) background tasks with native iOS Swift Widgets (WidgetKit) using Shared App Groups.

## The Problem
Syncing real-time data from a React Native application to a native iOS Home Screen Widget is notoriously difficult. Standard push notifications have severe rate limits, and standard React Native storage doesn't easily share data with native iOS targets.

## The Solution
This repository extracts the core syncing engine I built for real-time transit applications. It demonstrates how to:
1. Use `expo-background-fetch` and `expo-task-manager` to silently poll a FastAPI/Vercel backend.
2. Write the JSON payload directly to iOS `UserDefaults` via a shared App Group (`group.com.yourname.app`).
3. Use a native Swift `TimelineProvider` to instantly read that payload and refresh the Widget UI without waking the main React Native thread.

## Why This Matters
By abstracting this logic, developers can build real-time widgets (like stock tickers, live sports scores, or transit delays) without being bottlenecked by APNs (Apple Push Notification service) rate limits.

---
*Maintained by [@ruuuview](https://github.com/ruuuview) | Built with "Vibe Coding" for rapid iteration.*
