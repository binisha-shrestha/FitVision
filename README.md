# FitVision -- Real-Time Squat & Plank Posture Correction

## Project Overview

An AI-powered fitness coaching application that uses computer vision to
detect squat and plank exercises in real time, evaluate posture, provide
corrective feedback, count repetitions or hold time, and track user
progress.

## Problem Statement

Many people exercise without supervision, leading to poor form and
increased injury risk. This project provides instant AI-based posture
analysis using a webcam.

## Objectives

-   Detect squats and planks in real time.
-   Evaluate posture using body landmarks.
-   Count squat repetitions.
-   Measure plank hold duration.
-   Give live corrective feedback.
-   Store workout history and analytics.

## Tech Stack

### Frontend

-   React + Vite
-   CSS
-   Webcam API

### Backend

-   FastAPI
-   SQLite

### AI

-   MediaPipe Pose
-   OpenCV
-   NumPy

## Features

### Authentication

-   Register
-   Login
-   Logout

### AI Coach

-   Live webcam
-   Pose estimation
-   Joint-angle calculation
-   Posture scoring
-   Feedback overlay

### Squats

-   Rep counting
-   Knee angle analysis
-   Hip depth analysis
-   Correct/incorrect rep detection

### Planks

-   Hold timer
-   Spine alignment
-   Hip position monitoring
-   Shoulder alignment

### Dashboard

-   Workout history
-   Accuracy
-   Calories estimate
-   Weekly progress
-   Achievements

## User Stories

1.  As a user, I want to register so my workouts are saved.
2.  As a user, I want to log in securely.
3.  As a user, I want to choose squat or plank.
4.  As a user, I want AI to detect my body.
5.  As a user, I want live posture feedback.
6.  As a user, I want squat reps counted.
7.  As a user, I want plank duration tracked.
8.  As a user, I want posture corrections.
9.  As a user, I want workout history.
10. As a user, I want progress charts.
11. As a user, I want achievements.
12. As a user, I want confidence scores.
13. As a user, I want session summaries.
14. As a user, I want calorie estimates.
15. As a user, I want to compare previous sessions.

## Database Schema

### users

  Field           Type
  --------------- ------------
  id              INTEGER PK
  name            TEXT
  email           TEXT
  password_hash   TEXT

### workout_sessions

  Field           Type
  --------------- ------------
  id              INTEGER PK
  user_id         INTEGER FK
  exercise_type   TEXT
  duration        INTEGER
  accuracy        REAL
  calories        REAL

### squat_results

session_id, repetitions, correct_reps, incorrect_reps,
average_knee_angle

### plank_results

session_id, hold_time, posture_score, average_hip_angle

### achievements

id, title, description

## API List

### Authentication

-   POST /api/auth/register
-   POST /api/auth/login

### AI

-   POST /api/start-session
-   POST /api/analyze-frame
-   POST /api/end-session

### Workout

-   POST /api/workout/save
-   GET /api/history/{userId}
-   GET /api/dashboard/{userId}

## Folder Structure

``` text
fitness-ai/
├── frontend/
├── backend/
├── ai/
│   ├── pose_detector.py
│   ├── squat_analyzer.py
│   ├── plank_analyzer.py
│   ├── angle_calculator.py
│   └── feedback_generator.py
├── tests/
├── docs/
└── README.md
```

## AI Pipeline

Webcam → OpenCV → MediaPipe Pose → Landmark Extraction → Angle
Calculation → Exercise Detection → Feedback → Database

## Timeline

### Week 1

Planning, UI, backend, authentication.

### Week 2

Pose estimation and squat detection.

### Week 3

Plank detection, dashboard, database.

### Week 4

Testing, optimization, deployment.

## Sprint Plan

### Sprint 1

Setup project, authentication, webcam.

### Sprint 2

Pose estimation, squat analysis.

### Sprint 3

Plank analysis, history, dashboard.

### Sprint 4

Testing, deployment, documentation.

## Functional Requirements

-   Webcam access
-   Real-time inference
-   User authentication
-   Workout tracking
-   Feedback generation

## Non-functional Requirements

-   Responsive UI
-   Low latency
-   Secure authentication
-   Modular architecture
-   Maintainable code

## Testing

-   Unit tests
-   API tests
-   Integration tests
-   UI tests
-   AI validation

## Deployment

-   Frontend: Vercel
-   Backend: Render
-   Database: SQLite
-   Docker support

## Future Enhancements

-   Push-up detection
-   Lunge detection
-   Voice coaching
-   Mobile app
-   Personalized workout plans
-   Wearable integration

## Resume Highlights

-   Built a real-time AI fitness coach using MediaPipe Pose and OpenCV.
-   Developed FastAPI backend with REST APIs.
-   Built React frontend with webcam integration.
-   Implemented posture scoring and correction algorithms.
-   Stored workout analytics in SQLite.
-   Designed modular AI pipeline for scalable exercise recognition.

## License

MIT

## Acknowledgements

MediaPipe, OpenCV, FastAPI, React, Vite, SQLite.
