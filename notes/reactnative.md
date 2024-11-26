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

## View

- view component: fundamental core component in React Native that serves as a building block for creating user interfaces
- functions as a container that suports layout using flexbox, styling, touch handling, and accessibility controls
- can be compared to the `<div>` tag
- typically nested inside other views and can have zero or more children of any type
