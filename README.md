# Tech Stack Mobile App

A cross-platform mobile application built as a React Native practice project. The app presents a list of technologies and lets users tap an item to expand and view its description.

[View the repository on GitHub](https://github.com/ping58972/tech-stack-mobile-app)

## What this project demonstrates

- Building a cross-platform mobile UI with React Native.
- Creating reusable functional and class-based React components.
- Rendering technology data with React Native's `FlatList`.
- Managing application state with Redux and `react-redux`.
- Connecting list items to Redux actions and reducers.
- Expanding and collapsing list items with `LayoutAnimation`.
- Creating reusable UI components such as headers, cards, card sections, buttons, text inputs, and loading indicators.
- Maintaining native Android and iOS project targets from one JavaScript codebase.

## Technology stack

### Programming languages and formats

- **JavaScript (ES6+)** — application logic, components, Redux actions, and reducers.
- **JSX** — declarative React Native UI markup.
- **Java** — Android activity and application entry points.
- **Objective-C / Objective-C++** — iOS native application files and tests.
- **Groovy** — Android Gradle build scripts.
- **Ruby** — CocoaPods configuration in `ios/Podfile`.
- **XML** — Android manifests, resources, and iOS launch-interface resources.
- **JSON** — package metadata, app configuration, and the local technology dataset.

### Frameworks and libraries

- **React 16.8.6**
- **React Native 0.60.4**
- **Redux 4.0.4**
- **React Redux 7.1.0**
- **React Native core components and APIs**
  - `FlatList`
  - `View`, `Text`, and `TextInput`
  - `TouchableOpacity` and `TouchableWithoutFeedback`
  - `LayoutAnimation`
  - `ActivityIndicator`
  - `UIManager`
- **JavaScriptCore (JSC)** for the Android JavaScript runtime configuration. Hermes is disabled in the current Android build configuration.

### Development tools and build systems

- **Node.js and npm** — dependency installation and JavaScript tooling.
- **npm scripts** — start, test, and lint commands defined in `package.json`.
- **Metro** — React Native JavaScript bundler.
- **Babel** — JavaScript transformation through `@babel/core`, `@babel/runtime`, and the React Native Babel preset.
- **Jest** — JavaScript testing.
- **React Test Renderer** — React component test support.
- **ESLint** — JavaScript linting with the React Native Community ESLint configuration.
- **Android Studio / Android SDK** — Android development and emulator workflow.
- **Gradle** — Android build automation and dependency configuration.
- **Xcode** — iOS and tvOS project development.
- **CocoaPods** — iOS native dependency configuration.
- **Watchman** — file-watching support used by the React Native development workflow.
- **Flow configuration** — repository-level static-analysis configuration in `.flowconfig`.
- **Buck configuration** — Android build-related configuration in `.buckconfig`.

## Application architecture

```
src/
├── app.js                    # Root component and Redux Provider
├── actions/
│   └── index.js              # select_library action
├── reducers/
│   ├── LibraryList.json      # Technology data
│   ├── LibraryReducer.js     # Technology list state
│   ├── SelectionReducer.js   # Selected/expanded item state
│   └── index.js              # Combined reducers
└── components/
    ├── LibraryList.js        # FlatList container
    ├── ListItem.js           # Expandable technology item
    └── common/               # Reusable UI components
```

The root component creates the Redux store and provides it to the application. `LibraryList` reads technology data from Redux, while each `ListItem` dispatches `select_library` when tapped. The selected library ID determines whether the item's description is displayed.

## Prerequisites

The project uses an older React Native toolchain. The original project configuration specifies:

- Node.js **12.6.0**
- npm
- Android Studio with an Android emulator, or Xcode/iOS tooling for iOS
- Android SDK with the versions configured in `android/build.gradle`

Because React Native 0.60.4 and its native dependencies are legacy versions, newer Node.js, Android SDK, Xcode, or CocoaPods versions may require compatibility adjustments.

## Getting started

Clone the repository and install JavaScript dependencies:

```bash
git clone https://github.com/ping58972/tech-stack-mobile-app.git
cd tech-stack-mobile-app
npm install
```

Start the Metro development server:

```bash
npm start
```

Run the Android application:

```bash
npx react-native run-android
```

Run the iOS application:

```bash
npx react-native run-ios
```

For iOS native dependencies, install CocoaPods dependencies when needed:

```bash
cd ios
pod install
cd ..
```

## Testing and code quality

Run the configured test suite:

```bash
npm test
```

Run ESLint:

```bash
npm run lint
```

The repository includes the starter test file at `__tests__/App-test.js`.

## Project status and scope

This repository is a learning-focused React Native application. It contains the cross-platform project scaffolding and a Redux-backed expandable technology list. The checked-in configuration targets the legacy React Native 0.60.4 ecosystem; modernizing the dependencies would be a separate maintenance task.

## Author

**(Ping) Nalongsone Daddank** — [ping58972](https://github.com/ping58972)

## License

This project is licensed under the MIT License.
