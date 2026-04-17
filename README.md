You are required to integrate Provider or Riverpod into your Flutter application and demonstrate scalable global state management. Your implementation must prove that shared state updates correctly across multiple screens without relying on prop-drilling or excessive setState.

Your submission should include:

A Flutter project with Provider/Riverpod integrated at the app root.
A Pull Request (PR) containing all state management–related code changes.
A video demonstration uploaded to Google Drive, with edit access enabled for all.
Scenario-Based Task (Must Be Shown in Video Demo)
Your app includes a feature called “Favorites Sync”, where users can add items to a favorites list from Screen A, and view/remove them from Screen B. This requires shared state that updates instantly across screens.

In your demo, you must clearly show:

1. Provider or Riverpod Setup
Provider: ChangeNotifierProvider at app root or
Riverpod: ProviderScope with a StateNotifier / StateProvider
2. Add to Favorites (Screen A)
User taps “Add to Favorites” → item added to global list.
No navigation parameters or prop passing should be used.
3. View Favorites (Screen B)
Screen B shows updated list automatically.
UI reacts instantly when changes happen in Screen A.
4. Remove Item
Removing an item from Screen B updates Screen A immediately.
5. Explanation
In your video, explain:

Why state is stored globally.
How Provider/Riverpod listens for changes.