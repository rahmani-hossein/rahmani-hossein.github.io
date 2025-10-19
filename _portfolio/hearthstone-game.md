---
title: "HearthStone Game"
collection: portfolio
permalink: /portfolio/hearthstone-game
excerpt: "A Graphical Client-Server HearthStone game utilizing multiple design patterns including SOLID principles, Factory, and Visitor patterns."
date: 2022-06-01
link: "https://github.com/rahmani-hossein/HearthStone"
---

A fully-featured multiplayer HearthStone game implementation with graphical interface, client-server architecture, and enterprise-grade software design patterns. Developed as the capstone project for Advanced Programming in Java (OOP) course at Sharif University of Technology.

## Project Highlights

This project demonstrates mastery of object-oriented design principles and software architecture patterns in a complex, real-world application. The game faithfully implements HearthStone mechanics including card effects, turn-based gameplay, hero powers, and win conditions while maintaining clean, extensible code.

## Architecture & Design Patterns

### SOLID Principles
- **Single Responsibility**: Each class has one well-defined purpose (Card, Player, GameEngine, etc.)
- **Open/Closed**: New card types can be added without modifying existing code
- **Liskov Substitution**: Card subtypes are fully interchangeable where base cards are expected
- **Interface Segregation**: Clients depend only on interfaces they use
- **Dependency Inversion**: High-level game logic doesn't depend on low-level card implementations

### Design Patterns Implemented
- **Factory Pattern**: Card creation system that instantiates appropriate card types based on configuration
- **Visitor Pattern**: Elegant handling of diverse card actions (attack, heal, buff, summon) without cluttering card classes with action-specific code
- **Observer Pattern**: Event system for game state changes and UI updates
- **Strategy Pattern**: Interchangeable AI behaviors and card effect implementations

## Technical Stack

- **Language**: Java (Advanced OOP features)
- **Architecture**: Client-Server with socket programming
- **GUI**: Java Swing/JavaFX for rich graphical interface
- **Networking**: Multi-threaded server handling concurrent game sessions
- **Data Persistence**: Serialization for game state saving/loading

## Key Features

- **Full Game Implementation**: Complete HearthStone mechanics including mana system, card draw, minion combat, and spellcasting
- **Multiplayer Support**: Network-based client-server architecture supporting multiple concurrent games
- **Graphical Interface**: Intuitive drag-and-drop UI with visual feedback for all game actions
- **Extensible Card System**: Easy addition of new cards through configuration files
- **AI Opponents**: Programmatic opponents with varying difficulty levels (bonus feature)

## Software Engineering Excellence

This project showcases professional-grade software engineering practices:
- Clean code architecture following industry best practices
- Comprehensive use of design patterns for maintainability
- Separation of concerns (game logic, networking, UI)
- Modular design enabling team collaboration and parallel development

The codebase serves as a reference implementation for applying advanced OOP concepts and design patterns to game development, demonstrating how theoretical software engineering principles solve practical problems in complex systems.

[View on GitHub](https://github.com/rahmani-hossein/HearthStone) · [Design Documentation](https://github.com/rahmani-hossein/HearthStone#architecture)
