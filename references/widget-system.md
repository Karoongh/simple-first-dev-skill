# Widget / Container System

Goal: let the end user personalize the main workspace without developer help.

## Core concepts

- Slot / Container — a place on Home that can hold widgets
- Widget — a self-contained card (status, list, number, shortcut, chart…)
- Preset — a saved combination of widgets for a role or preference
- User preference — which widgets are visible, their order, and optionally size

## Minimum viable personalization (phase 1)

Even before full drag-and-drop, support:

1. Show / hide each widget
2. A few role or style presets the user can switch
3. Save preference per user (or per role)

This already makes the product feel personal.

## Later phases

- Drag to reorder
- Resize (small / medium / large)
- Optional extra widgets for power users

## Simple data shape

- user_id or role
- widget_key (stable string id)
- visible (boolean)
- position (integer)
- size (optional)

## Design rules

- Every new Home capability should be born as a widget, not a fixed block
- Mandatory always-visible widgets should be rare
- Widgets must work independently (hiding one must not break another)
- Keep widget code modular
- Default preset should stay light — start with a focused set, not everything

## What to avoid

- Hard-coded Home layout the user cannot change
- Tight coupling between widgets
- Overloaded default screens full of cards the user never asked for
