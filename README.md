# n8n Code Node: Automated Data Cleaning

A JavaScript snippet used inside n8n's Code node to clean and normalize incoming form data automatically, no manual data entry fixes needed.

## What it does

Splits and cleans full name into first and last name
Trims and lowercases email
Strips non numeric characters from amount, converts to float
Formats raw date into a readable format
Capitalizes names and messages safely, handles empty fields
Outputs clean, structured data ready for the next node

## Why it matters

Real world form submissions are often messy: extra spaces, wrong casing, junk characters in numbers. This script fixes all of that before data reaches storage or notifications, preventing broken records and manual cleanup.

## Tech

n8n Code Node (JavaScript)

## Usage

Paste into any n8n Code node after a form or webhook trigger. Adjust field names (full name, email, amount, date, message) to match your input source.
