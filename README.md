# Attendance-App
🔹 Attendance App Full Blueprint

1. Login System

Teacher Login

Login via official email / username + password

Can create courses, semesters, divisions, sub-divisions

Can manually add students with:

Roll Number

User ID

Optional initial password (students can change later)



Student Login

Login via assigned User ID + password

On first login, app records Device ID (ANDROID_ID + Firebase Installation ID)

Device ID check:

Matches → login OK

Mismatch → prompt: “Request approval from teacher” → sends support request




---

2. Course & Lecture Management

Teacher Module

Add Courses / Semesters / Divisions / Sub-divisions

Add Students manually (Roll number, User ID)

Add Lecture Schedule (time/date)

Start lecture session (“season”) → generate OTP + record classroom GPS


Student Module

Enter OTP to join session → allowed only if valid and not expired (3–5 min)

Joins session pool for lecture



---

3. OTP + Unique QR System

Teacher

Click Generate QR → system generates unique QR per student

QR contains:

Lecture ID

Student ID

Session token

Expiry timestamp (time-limited)



Student

QR pops up inside their app

Tap “Mark Attendance” button → app validates:

Token matches student + lecture

Token not expired

GPS location (optional check, teacher-side)



Security

Each QR is unique per student

Scanning is in-app → no camera needed

Token + OTP together prevent proxy cheating



---

4. GPS Validation (Teacher-Side)

Students do not see GPS checks

Teacher can view live attendance dashboard

Alerts generated if student marked attendance outside classroom radius

Teacher can accept/reject flagged students

All GPS checks logged in attendance database



---

5. Manual Attendance Override

Teacher can manually mark attendance:

Select student by roll number

Or tap QR displayed in student app


Used for students with technical issues

Manual override logged separately for transparency



---

6. Device ID Security & Support Request

One Device = One Profile

On new device: student cannot login → sends request to teacher

Teacher approves/rejects → updates device ID for student profile

Old device deactivated automatically

Login attempts from unapproved devices logged



---

7. Closing Lecture Session

After lecture ends, teacher clicks Close Session

OTP + QR expire → no further attendance possible

Attendance report saved, can be exported (CSV/Excel)

Report includes:

Student status (present/absent)

GPS valid/invalid

Manual override

Device ID used
