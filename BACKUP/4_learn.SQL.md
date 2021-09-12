# [learn SQL](https://github.com/Daydog/gitblog/issues/4)

- 初步熟悉一下操作和语句
- [SQL Tutorial - Full Database Course for Beginners - YouTube](https://www.youtube.com/watch?v=HXV3zeQKqGY)
- [MySQL ALTER命令 ](https://www.runoob.com/mysql/mysql-alter.html)

```
create, insert, update, delete

# CREATE TABLE
CREATE TABLE student (
    student_id INT PRIMARY KEY,
    name VARCHAR(20),
    major VARCHAR(20)
);

DESCRIBE student;

DROP TABLE student;

ALTER TABLE student ADD GPA DECIMAL(3,2);

ALTER TABLE student DROP COLUMN GPA;

#INSERTING DATA
INSERT INTO student(student_id, name) VALUES(3, 'Claire');
INSERT INTO student VALUES(4, 'Jack', 'Biology');
INSERT INTO student VALUES(5, 'Mike', 'Computer Science');

#updating and delete
UPDATE student
set major = 'gaming'
where name = 'Claire'

update student
set major = 'coding'
where major = 'Sociology' or major = 'Bio'

update student
set name = 'Tom', major = 'undecided'
where student_id = 1;

update student
set major = 'accounting'

delete from student
where student_id = 5;

delete from student
where name = 'Tom' and major = 'accounting'

delete from student;

```

1:56 basic queries
