### List of Questions:

1. **Security Guidelines:**
   - What are the best practices for security in Flutter applications?
   - How does SecureStorage work in Flutter for sensitive data storage?
   - What are the differences between SSL and TSL, and how do they relate to HTTP and REST API security?
   
2. **Why Flutter?**
   - What are the advantages of choosing Flutter for app development?
   - How does Flutter's cross-platform capabilities impact development efficiency?

3. **Hot Restart and Hot Reload:**
   - What is the difference between hot restart and hot reload in Flutter?
   - How does Flutter manage hot reload without losing the app's state?

4. **Stateless vs Stateful Widgets:**
   - What is the key difference between stateless and stateful widgets in Flutter?
   - When should you use a StatelessWidget versus a StatefulWidget?

5. **Widget Lifecycle:**
   - What are the different stages in the widget lifecycle in Flutter?
   - What is the `didChangeDependencies()` method in Flutter, and when is it called?

6. **Build Context:**
   - What is the purpose of the `BuildContext` in Flutter?
   - How does `BuildContext` help manage widget hierarchies?

7. **Inheritance and Dart:**
   - Does Flutter support multiple inheritance? If not, what are the alternatives?
   - How do mixins in Dart differ from traditional classes?

8. **Private Members in Dart:**
   - How do you declare private members in a Dart class?
   - What is the convention for naming private members in Dart?

9. **Main Method & runApp:**
   - What happens if you do not call `runApp(MaterialApp())` in the `main()` method of a Flutter app?

10. **Mixins vs Classes:**
    - What are the differences between using a mixin and a class in Dart?
    - When should you prefer a mixin over a class in Flutter development?

11. **Required Annotation in Dart:**
    - What is the purpose of the `required` annotation in Dart, and how does it improve code safety?

12. **String Interpolation:**
    - What is string interpolation in Dart, and why is it preferred over traditional string concatenation? 

13. **Expanded and Flexible Widgets:**
    - What is the difference between the `Expanded` and `Flexible` widgets in Flutter, and when should each be used?

14. **Spacer vs SizedBox:**
    - What is the difference between the `Spacer` and `SizedBox` widgets in Flutter?

15. **ListView vs ListView.builder:**
    - What is the difference between `ListView` and `ListView.builder` in Flutter?
    - When should you use one over the other?

16. **State Management Patterns:**
    - What are the different state management patterns supported in Flutter?
    - What is the difference between BLoC, GetX, and Provider for state management?

17. **BLoC in Flutter:**
    - What is `buildWhen` in BLoC, and how does it control widget rebuilding?
    - What are the differences between `BlocProvider`, `BlocConsumer`, `BlocListener`, and `BlocBuilder` in Flutter?

18. **Routing in Flutter:**
    - How do you define routes in a Flutter application?

19. **Unit Testing and Mocking:**
    - Which libraries are commonly used for unit testing and mocking in Flutter?

20. **Const vs Final:**
    - What is the difference between `const` and `final` in Dart regarding compile-time and run-time values?
    - Can `final` variables in Dart be null?

21. **Fat Arrow Notation in Dart:**
    - What is the purpose of fat arrow (`=>`) notation in Dart, and when should it be used?

22. **Navigator 2.0:**
    - What are the differences between Navigator 1.0 and Navigator 2.0 in Flutter for managing navigation?

23. **Isolates in Flutter:**
    - What are isolates in Flutter, and how do they handle concurrency?

24. **Concurrent Futures:**
    - How do you run multiple futures concurrently using `await Future.wait` in Dart?

25. **RenderFlex Overflow:**
    - How do you handle the error "A RenderFlex overflowed by N pixels on the bottom"?

26. **Call Method in Dart Classes:**
    - What is the `call` method in Dart classes, and how does it allow class instances to emulate functions?

27. **Build Modes in Flutter:**
    - What are the different build modes in Flutter (debug, release, profile)?
    - How does tree-shaking work in Flutter builds?

28. **Debugging Broken UI:**
    - How do you debug a broken UI and find the root cause using `debugFillProperties`?

29. **Streams in Flutter:**
    - What are Streams in Flutter, and how are they used for asynchronous data handling?

30. **Widget Tree, Element Tree, Renderer Tree:**
    - What are the Widget Tree, Element Tree, and Renderer Object Tree in Flutter, and how do they relate to the rendering process?

31. **Orientation Handling in Flutter:**
    - How do you handle orientation changes for portrait and landscape mode in Flutter?

32. **SOLID Principles:**
    - How do the SOLID principles apply to Flutter app architecture?

33. **Flutter Plugins:**
    - How do you publish a Flutter plugin using `flutter packages pub publish --dry-run` and `flutter packages pub publish`?

34. **Non-functional Requirements:**
    - What are some common non-functional requirements for a Flutter app?

35. **Why Riverpod?:**
    - Why is Riverpod considered better than other state management options like Provider?

36. **HTTP Streaming Drawbacks:**
    - What are some of the potential drawbacks of HTTP streaming in Flutter?

37. **Event Loop in Dart:**
    - How does the event loop work with asynchronous operations in Dart, especially with `async` and `await`?

38. **Post-Deployment Issues:**
    - What are some ways to detect and resolve issues after deploying a Flutter app?

39. **Benchmarking and Analytical Tools:**
    - How do you use benchmarking and analytical tools in Flutter to assess performance?
  
40. **Null Safety in Dart:**
    - What is null safety in Dart, and how does it prevent null reference errors?

41. **Default Values in Dart Functions:**
    - How do you provide default values for parameters in Dart functions?

42. **Dart's Optional Named and Positional Parameters:**
    - What is the difference between optional named and positional parameters in Dart?

43. **GlobalKeys in Flutter:**
    - What is a `GlobalKey`, and how is it used to access the state of widgets?

44. **Flutter's GestureDetector:**
    - What is the `GestureDetector` widget in Flutter, and how does it handle touch events?

45. **AsyncSnapshot in Flutter:**
    - What is `AsyncSnapshot` in Flutter, and how is it used with `FutureBuilder` and `StreamBuilder`?

46. **Error Handling in Dart:**
    - How do you handle errors in Dart, and what is the difference between `try-catch` and `try-catch-finally`?

47. **Implicit Animations in Flutter:**
    - What are implicit animations in Flutter, and how do widgets like `AnimatedContainer` work?

48. **Flutter’s ShaderMask:**
    - What is `ShaderMask` in Flutter, and how can you use it for gradient effects?

49. **Difference Between RawPointerEvent and Gesture in Flutter:**
    - What is the difference between a `RawPointerEvent` and a gesture in Flutter?

50. **CustomPainter in Flutter:**
    - How do you use the `CustomPainter` class to create custom graphics in Flutter?

51. **How to Use Flutter Hooks:**
    - What are Flutter Hooks, and how do they help in managing state more efficiently?

52. **Flutter's Draggable and DragTarget:**
    - How do you implement drag-and-drop functionality using `Draggable` and `DragTarget` widgets?

53. **FutureBuilder vs StreamBuilder:**
    - What is the difference between `FutureBuilder` and `StreamBuilder`, and when should you use each?

54. **How to Use AnimationController in Flutter:**
    - How does the `AnimationController` class work in Flutter for building custom animations?

55. **Flutter Web Support:**
    - What are the key differences between developing for mobile and the web in Flutter?

56. **Accessibility in Flutter:**
    - How do you ensure accessibility in Flutter apps, especially for screen readers and keyboard navigation?

57. **Asset Management in Flutter:**
    - How do you manage assets (images, fonts, etc.) in a Flutter application, and what is the purpose of the `pubspec.yaml` file?

58. **Flutter's Hero Animation:**
    - What is a `Hero` animation in Flutter, and how does it enable shared element transitions between screens?

59. **Platform Channels in Flutter:**
    - What are platform channels in Flutter, and how do they facilitate communication between Flutter and native code?

60. **Memory Management in Flutter:**
    - How is memory managed in a Flutter app, and what tools can be used to detect memory leaks?
