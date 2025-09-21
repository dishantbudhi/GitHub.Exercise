# Copilot Instructions

## Project Overview
This is a TypeScript-based student transcript management system focused on type definitions and data structures for academic grading.

## Core Architecture

### Type System (`Types.ts`)
- **Domain primitives**: `StudentID` (number), `StudentName` (string), `CourseID` (string), `Grade` (number 0-100)
- **Core entity**: `Transcript` - central data structure containing student info and course grades array
- **Pattern**: Use explicit type aliases for domain concepts rather than primitive types directly

### Key Patterns
- Transcript structure follows `{ studentID, studentName, courses: Array<{ courseID, grade }> }` pattern
- Grade values are constrained to 0-100 range (documented in type comment)
- Course relationships are embedded within transcript rather than normalized

## Development Guidelines

### Type Definitions
- Maintain type exports in `Types.ts` as the single source of truth
- Use descriptive comments for constraints (e.g., grade ranges, ID uniqueness)
- Follow the existing pattern of type aliases for domain concepts

### File Organization
- Keep all shared types in `Types.ts`
- The commented import example shows expected usage pattern: `import { StudentID, StudentName, Transcript, CourseID } from "./Types"`

### Data Structure Conventions
- Transcripts embed course data rather than using foreign key references
- Student identification uses numeric IDs paired with string names
- Course grading uses simple numeric scores (0-100 scale)

## Current State
- Minimal project with core type definitions established
- No build system, testing, or runtime code yet implemented
- Ready for implementation of business logic using the defined types