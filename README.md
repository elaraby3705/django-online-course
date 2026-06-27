# django-online-course

> A Django-based online learning platform that enables course enrollment, multi-choice exams, and instant result evaluation.

![Python](https://img.shields.io/badge/Python-3.8+-blue) ![Django](https://img.shields.io/badge/Django-3.x%2F4.x-green) ![License](https://img.shields.io/badge/License-Hammad-gray)

---

## Overview

A full Django project built for educational purposes. Learners can enroll in courses, take multiple-choice exams, and immediately see their scored results with per-question feedback.

```
onlinecourse/
├── models.py          ← Course, Lesson, Question, Choice, Submission
├── admin.py           ← Admin interface with Inline editing
├── views.py           ← enroll, submit, show_exam_result
├── urls.py            ← URL routing
└── templates/
    ├── course_details_bootstrap.html
    └── exam_result_bootstrap.html
```

---

## Requirements

```bash
Python 3.8+
Django 3.x / 4.x
Pillow        # required for ImageField
```

```bash
pip install django pillow
```

---

## Quick Start

```bash
# 1. Clone the repo
git clone https://github.com/YOUR_USERNAME/django-online-course.git
cd django-online-course

# 2. Run migrations
python3 manage.py makemigrations onlinecourse
python3 manage.py migrate

# 3. Create superuser
python3 manage.py createsuperuser
# Username: admin | Password: p@ssword123

# 4. Start server
python3 manage.py runserver
```

Visit: `http://127.0.0.1:8000/onlinecourse/`  
Admin: `http://127.0.0.1:8000/admin/`

---

## Milestones

| # | Milestone | Tasks | Files |
|---|-----------|-------|-------|
| M1 | Build new models | Task 1 | `models.py` |
| M2 | Register model changes | Task 2 | `admin.py` |
| M3 | Course detail template | Task 3 | `course_details_bootstrap.html` |
| M4 | Test data + Submission evaluation | Task 4, 5 | `views.py`, `urls.py` |
| M5 | Exam result template | Task 6 | `exam_result_bootstrap.html` |

---

## Data Model

```
Course ──< Lesson
Course ──< Question ──< Choice
                              ↑
Enrollment ──< Submission >──┘  (ManyToMany)
```

---

## Required Screenshots

| File | Content |
|------|---------|
| `01-models.png` | `models.py` showing Question, Choice, Submission |
| `02-admin-file.png` | Updated `admin.py` |
| `03-admin-site.png` | Django admin — OnlineCourse section |
| `04-course-details.png` | Course detail page with exam section |
| `05-views.png` | `views.py` showing submit and show_exam_result |
| `06-urls.png` | `urls.py` showing new URL patterns |
| `07-final.png` | Exam result — Congratulations message |

---

## Key Concepts Covered

- Difference between `ForeignKey` and `ManyToManyField`
- `StackedInline` for editing related objects on one admin page
- Reading form data from `request.POST` manually
- Django template tags: `{% for %}`, `{% if %}`, `{% csrf_token %}`
- `get_object_or_404` as best practice over raw `Model.objects.get()`
- `@login_required` decorator for view protection

---

## Contributing

Open an Issue first to discuss the change, then submit a Pull Request using the template in `ISSUES.md`.

---

## License

MEee --# django-online-course
