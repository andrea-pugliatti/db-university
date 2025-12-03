# University

## Tables

- departments
- degrees
- courses
- teachers
- exam_sessions
- students

## departments

- id 
- name 
- (one to many) degree_id

## degrees

- id 
- name 
- (one to many) course_id

## courses

- id 
- name
- credits
- (many to many) teachers_id
- (one to many) exam_session_id

## teachers

- id 
- name
- address
- phone
- rank
- (many to many) course_id

## pivot: course_teacher

- id
- course_id
- teacher_id

## exam_sessions

- id 
- course_id
- (one to many) student_id
- date
- location

## students

- id
- registration_number
- name
- address
- phone
- registration_date
- degree_id
- (one to many) course_id
- (many to many) exam_sessions

## pivot: exam_session_student

- id
- student_id
- exam_session_id
- vote