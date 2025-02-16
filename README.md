# React Router v6 Catch-all Route Issue

This repository demonstrates a problem with the catch-all route (`/*`) in React Router v6.  The catch-all route should match any route that has not been matched by previous routes. However, this example shows that even when other routes are correctly defined, the catch-all route still renders.

## Problem
The issue occurs when you attempt to use a catch-all route in conjunction with other, more specific routes. Instead of acting as a fallback, the catch-all route seems to override any other matches.  This results in the 404 component always rendering.

## Solution
The solution lies in the order of routes in the `Routes` component. The catch-all route should always be the last route defined. If it is placed before the more specific routes, it will always match first. Moving the `/*` route to the end will correctly show other routes before triggering 404.