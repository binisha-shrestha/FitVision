# FitVision - AI Mobile Fitness Coach

## 📖 Project Overview

FitVision is an AI-powered mobile fitness coaching application that uses computer vision and pose estimation to analyze exercise posture in real time. The application helps users perform exercises correctly by detecting body landmarks from the mobile camera, evaluating posture, counting repetitions, measuring hold duration, and providing instant corrective feedback.

The first version focuses on **Squats** and **Planks**, with future support planned for additional exercises such as Push-ups, Lunges, Burpees, and Jumping Jacks.

---

# 1. Features

## Exercise Selection
- Squat
- Plank

## AI Pose Detection
- Real-time pose estimation
- Mobile camera support
- Skeleton overlay
- Confidence score

## Squat Analysis
- Automatic repetition counting
- Knee angle analysis
- Hip depth analysis
- Back posture analysis
- Correct vs incorrect squat detection
- Real-time corrective feedback

## Plank Analysis
- Hold timer
- Back alignment detection
- Hip position monitoring
- Shoulder alignment analysis
- Real-time corrective feedback

## Dashboard
- Workout history
- Total workouts
- Total repetitions
- Longest plank
- Accuracy score
- Weekly progress

## Analytics
- Exercise statistics
- Progress tracking
- Personal best records
- Workout summaries

## Future Features
- Push-up detection
- Lunge detection
- Burpee detection
- Voice coaching
- Workout streaks
- AI workout recommendations
- Wearable integration

---

# 2. User Stories

### Authentication

- As a user, I want to create an account so my workout history is saved.
- As a user, I want to log in securely.
- As a user, I want to manage my profile.

### Workout

- As a user, I want to choose an exercise before starting.
- As a user, I want to use my phone camera for posture analysis.
- As a user, I want AI to detect my posture automatically.
- As a user, I want incorrect posture to be identified.
- As a user, I want live suggestions to improve my form.

### Squats

- As a user, I want my squat repetitions counted automatically.
- As a user, I want to know whether each squat is correct.
- As a user, I want feedback on my knee and hip position.

### Planks

- As a user, I want my plank duration measured automatically.
- As a user, I want feedback on my spine and hip alignment.

### Dashboard

- As a user, I want to review previous workout sessions.
- As a user, I want to monitor my fitness progress.
- As a user, I want to view workout statistics.

---

# 3. Database Schema

## users

| Field | Type |
|--------|------|
| id | INTEGER PK |
| full_name | TEXT |
| email | TEXT |
| password_hash | TEXT |
| created_at | DATETIME |

---

## workout_sessions

| Field | Type |
|--------|------|
| id | INTEGER PK |
| user_id | INTEGER FK |
| exercise_type | TEXT |
| duration | INTEGER |
| accuracy | REAL |
| calories | REAL |
| created_at | DATETIME |

---

## squat_results

| Field | Type |
|--------|------|
| id | INTEGER PK |
| session_id | INTEGER FK |
| repetitions | INTEGER |
| correct_reps | INTEGER |
| incorrect_reps | INTEGER |
| average_knee_angle | REAL |
| average_hip_angle | REAL |

---

## plank_results

| Field | Type |
|--------|------|
| id | INTEGER PK |
| session_id | INTEGER FK |
| hold_time | INTEGER |
| posture_score | REAL |
| average_back_angle | REAL |
| average_hip_angle | REAL |

---

## achievements

| Field | Type |
|--------|------|
| id | INTEGER PK |
| title | TEXT |
| description | TEXT |
| required_points | INTEGER |

---

## user_achievements

| Field | Type |
|--------|------|
| id | INTEGER PK |
| user_id | INTEGER FK |
| achievement_id | INTEGER FK |

---

# 4. API List

## Authentication

```
POST   /api/auth/register
POST   /api/auth/login
GET    /api/auth/profile
```

---

## AI

```
POST   /api/workout/start
POST   /api/workout/analyze
POST   /api/workout/end
```

---

## Dashboard

```
GET    /api/dashboard
GET    /api/history
GET    /api/statistics
```

---

## Workout

```
POST   /api/workout/save
GET    /api/workout/:id
DELETE /api/workout/:id
```

---

## Achievements

```
GET    /api/achievements
GET    /api/user-achievements
```

---

# 5. Folder Structure

```text
fitvision/

├── mobile/
│   ├── app/
│   ├── assets/
│   ├── components/
│   ├── navigation/
│   ├── screens/
│   ├── services/
│   ├── hooks/
│   ├── utils/
│   └── App.tsx
│
├── backend/
│   ├── app/
│   │   ├── api/
│   │   ├── controllers/
│   │   ├── database/
│   │   ├── middleware/
│   │   ├── models/
│   │   ├── services/
│   │   └── main.py
│
├── ai/
│   ├── pose_detector.py
│   ├── squat_detector.py
│   ├── plank_detector.py
│   ├── angle_calculator.py
│   ├── feedback_engine.py
│   └── utils.py
│
├── docs/
├── tests/
├── README.md
└── LICENSE
```

---

# 6. Timeline

## Week 1
- Project planning
- UI design
- Mobile project setup
- Authentication
- Database setup

---

## Week 2
- Camera integration
- MediaPipe Pose
- Skeleton detection
- Squat posture analysis

---

## Week 3
- Plank posture analysis
- Dashboard
- Workout history
- Analytics

---

## Week 4
- Testing
- Performance optimization
- Bug fixing
- Documentation
- Deployment

---

# 7. Sprint Plan

## Sprint 1 – Project Foundation

### Goal
Create the application foundation.

### Tasks
- Project setup
- Authentication
- Navigation
- Database
- UI screens

### Deliverables
- Working mobile application with login system

---

## Sprint 2 – AI Integration

### Goal
Implement pose estimation.

### Tasks
- Camera integration
- MediaPipe Pose
- Joint angle calculation
- Skeleton visualization

### Deliverables
- Live pose detection

---

## Sprint 3 – Exercise Analysis

### Goal
Implement posture correction.

### Tasks
- Squat analysis
- Plank analysis
- Feedback generation
- Workout saving

### Deliverables
- AI posture correction for squats and planks

---

## Sprint 4 – Finalization

### Goal
Complete the application.

### Tasks
- Dashboard
- Analytics
- Testing
- Documentation
- Deployment

### Deliverables
- Production-ready AI mobile fitness coach
