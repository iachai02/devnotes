# React Native Notes

What is react native?

- React Native is an open-source framework for building native Android and iOS applications using React
- React itself ia library designed for building user interfaces

## Setting up

- `npx create-expo-app@latest NameOfFile`: creates a new expo application
- pacakge.json: contains scripts, dependencies, and metadata
- app.json: configuration options for the project

## Running your app

- npm start: starts the application

## Core Components

- In Android and iOS development, we employ a fundamental building block called a "view" for user interfaces
- A view is a small rectangular element on the screen that can display text, images, or respond to user input
- At runtime, React Native generates the corresponding Android and iOS views for these components
- React Native offers a collection of essential pre-built components known as "core components", which are readily available for building your native app's user interface

## View Component

- view component: fundamental core component in React Native that serves as a building block for creating user interfaces
- functions as a container that suports layout using flexbox, styling, touch handling, and accessibility controls
- can be compared to the `<div>` tag
- typically nested inside other views and can have zero or more children of any type

## Text Component

- component for displaying text
- supports nesting, styling, and touch handling
- will translate this component to either UITextView (iOS), a TextView (Android), or a 'p' (web)

## Image Component

- image component enables us to display various types of images, including:
  - static images
  - network images
  - images from the local disk, such as the camera roll
- react native seamlessly translates the image component to platform-specific counterparts:
  - UIImageView for iOS
  - ImageView for Android
  - 'img' for the web

## ScrollView Component

- wraps the platform-specific scrolling functionality
- require a bounded height to function properly

## Button Component

- allows users to trigger actions
- has platform-specific rendering for iOS and Android
  - onPress

## Pressable Component

- a wrapper component that detects various stages of press interactions on its defined children
- you can create a custom button using pressable
  - onPressln: press is activated
  - onLongPress: triggered when a press is held for longer than 500 milliseconds
  - onPressOut: press gesture is deactivated

## Modal Component

- screen that overlays the app content to provide important information or prompt the user for a decision
- since they are purposefully interruptive make sure you use them only when necessary
  - visible
  - onRequestClose
  - animationType
  - presentationStyle

## StatusBar Component

- allows you to control the application's status bar
- the status bar is the zone, typically at the top of the screen, that displays the current time, Wi-Fi and netowrk information, battery level other status icons
  - backgroundColor
  - barStyle
  - hidden

## ActivityIndicator Component

- displays a circular loading indicator
- used to inform users about the status of ongoing processes, such as loading an app, submitting a form, or saving updates
  - size
  - color
  - animating

## Alert Component

- launches an alert dialog with specified title and message
- optionally, you can also specify a list of buttons

## Styling React Native Apps

- react native does not use CSS for styling
- you style your app using JavaScript
- Names are written in camel case
  - Ex. backgroundColor instead of background-color
