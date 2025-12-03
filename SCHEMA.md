# University

## Tables

- departments
- degrees
- courses
- teachers
- exam_sessions
- students

## departments

- id                            PRIMARY_KEY BIGINT AUTO_INCREMENT
- name                          VARCHAR(40) NOTNULL
- (one to many) degree_id       BIGINT FOREIGN_KEY

## degrees

- id                            PRIMARY_KEY BIGINT AUTO_INCREMENT
- name                          VARCHAR(40) NOTNULL
- id_code                       CHAR(4) NOTNULL
- (one to many) course_id       BIGINT FOREIGN_KEY

## courses

- id                            PRIMARY_KEY BIGINT AUTO_INCREMENT
- name                          VARCHAR(40) NOTNULL
- description                   TEXT NULL
- id_code                       CHAR(10) NOTNULL
- credits                       TINYINT NOTNULL
- (one to many) exam_session_id BIGINT FOREIGN_KEY

## teachers

- id                            PRIMARY_KEY BIGINT AUTO_INCREMENT
- name                          VARCHAR(30) NOTNULL
- address                       VARCHAR(40) NOTNULL
- phone                         CHAR(10) NOTNULL
- rank                          VARCHAR(25) NOTNULL

## pivot: course_teacher

- course_id                     BIGINT FOREIGN_KEY
- teacher_id                    BIGINT FOREIGN_KEY

## exam_sessions

- id                            PRIMARY_KEY BIGINT AUTO_INCREMENT
- course_id                     BIGINT FOREIGN_KEY
- date                          DATETIME NOTNULL
- location                      VARCHAR(5) NOTNULL

## students

- id                            PRIMARY_KEY BIGINT AUTO_INCREMENT
- registration_number           CHAR(8) NOTNULL
- name                          VARCHAR(30) NOTNULL
- address                       VARCHAR(40) NOTNULL
- phone                         VARCHAR(10) NOTNULL
- registration_date             DATE NOTNULL
- degree_id                     BIGINT FOREIGN_KEY

## pivot: exam_session_student

- student_id                    BIGINT FOREIGN_KEY
- exam_session_id               BIGINT FOREIGN_KEY
- vote                          CHAR(2) NOTNULL