# React Router Dom v6 Issue: Path `/*` Not Catching All Unmatched Routes

This repository demonstrates a common issue encountered when using `react-router-dom` v6 where the catch-all route `path="/*"` fails to capture all unmatched routes as expected.  The problem arises from how the router handles routing based on the order and specificity of defined routes.

## Problem

The `path="/*"` route, intended to act as a 404 Not Found handler, is often overshadowed by other routes if those routes are defined *before* the catch-all route.  Even if there's no exact match, if a route's path is a prefix to the current URL, it will take precedence. 

## Solution

The solution is simple.  Ensure that your catch-all route (`/*`) is the *last* route defined in your `Routes` component. By placing it last, the router will only use it after checking all other more specific routes.

## Setup

1.  Clone this repo.
2.  `npm install`
3.  `npm start`