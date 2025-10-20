[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/oqKLEXJJ)
# 🎓 Ethical Admissions Algorithm Simulation

This repository is a classroom exercise exploring **ethics and fairness in algorithmic decision-making** — specifically in college admissions.

You’ll implement and reflect on how feature selection and weighting can impact fairness, transparency, and equity in automated systems.

---

## 🧩 Overview

You are part of the admissions committee for **Anonymous University**, located near Anonymous City.  
Due to a large number of applications, the committee decides to use an algorithm to help **rank and shortlist applicants**.

Your task:
- Decide which factors to include (GPA, test scores, extracurriculars, essays, recommendation letters, legacy status, income, etc.)
- Assign weights to each factor.
- Compare outcomes under two models:
  - **Blind model**: Ignores sensitive factors.
  - **Aware model**: Includes them intentionally to promote fairness (e.g., extra weight for first-gen or low-income applicants).

---

## ⚙️ How to Run

You can run the code on any online Java compiler (e.g. [Replit](https://replit.com/~) or [Programiz Java Compiler](https://www.programiz.com/java-programming/online-compiler))  
or locally via terminal:

```bash
javac Applicant.java Admissions.java Main.java
java Main


## my stuff

## no change 
=== Admissions Results ===
Alice Stark     | Blind: 0.91 (Admitted) | Aware: 1.00 (Admitted)
Bob Parker      | Blind: 0.90 (Admitted) | Aware: 0.92 (Admitted)
Carlos Rivera   | Blind: 0.72 (Rejected) | Aware: 0.82 (Rejected)
Diana Chen      | Blind: 0.91 (Admitted) | Aware: 0.94 (Admitted)
Fatima Al-Sayed | Blind: 0.69 (Rejected) | Aware: 0.82 (Rejected)
George Johnson  | Blind: 0.71 (Rejected) | Aware: 0.81 (Rejected)
Hannah Miller   | Blind: 0.67 (Rejected) | Aware: 0.69 (Rejected)
Ishaan Singh    | Blind: 0.85 (Admitted) | Aware: 0.88 (Admitted)
Jasmine Okafor  | Blind: 0.73 (Rejected) | Aware: 0.86 (Admitted)
Liam Wang       | Blind: 0.84 (Admitted) | Aware: 0.86 (Admitted)

## final 
        score += (app.gpa / 4.0) * 0.3;     // GPA normalized
        score += (app.test / 1600.0) * 0.4;  // Test score normalized
        score += app.extra * 0.0;
        score += app.essay * 0.1;
        score += app.rec * 0.2;
        if (app.income <= 32000) score += 0.1;     // low-income boost
        if (app.firstGen) score += 0.5;           // first-generation bonus
        if (app.disability) score += 0.03;         // accessibility consideration
        if (app.legacy) score += 0.01;             // legacy advantage
        if (app.local) score += 0.01;              // local preference
=== Admissions Results ===
Alice Stark     | Blind: 0.92 (Admitted) | Aware: 1.00 (Admitted)
Bob Parker      | Blind: 0.91 (Admitted) | Aware: 0.92 (Admitted)
Carlos Rivera   | Blind: 0.69 (Rejected) | Aware: 0.79 (Rejected)
Diana Chen      | Blind: 0.90 (Admitted) | Aware: 0.91 (Admitted)
Fatima Al-Sayed | Blind: 0.67 (Rejected) | Aware: 0.82 (Rejected)
George Johnson  | Blind: 0.69 (Rejected) | Aware: 0.79 (Rejected)
Hannah Miller   | Blind: 0.64 (Rejected) | Aware: 0.65 (Rejected)
Ishaan Singh    | Blind: 0.84 (Admitted) | Aware: 0.85 (Admitted)
Jasmine Okafor  | Blind: 0.72 (Rejected) | Aware: 0.82 (Admitted)
Liam Wang       | Blind: 0.84 (Admitted) | Aware: 0.85 (Admitted)

Part 2: Discussion & Reflection
After running both models, discuss and reflect on the following:
Feature Selection & Design
● What variables did you include, and why?
        score += (app.gpa / 4.0) * 0.3;     // GPA normalized
        score += (app.test / 1600.0) * 0.4;  // Test score normalized
        score += app.extra * 0.0;
        score += app.essay * 0.1;
        score += app.rec * 0.2;
        if (app.income <= 32000) score += 0.1;     // low-income boost
        if (app.firstGen) score += 0.5;           // first-generation bonus
        if (app.disability) score += 0.03;         // accessibility consideration
        if (app.legacy) score += 0.01;             // legacy advantage
        if (app.local) score += 0.01;              // local preference
 we flipped the test and the gpa
 then equalized the bias for the disability, income, and firstGen
 I did this because we wanted to select people who are prepared to go to school

● Did you exclude any sensitive features? Why or why not?
  no
● Should “legacy” still carry a positive weight?
  Yes but it should be small
● What other features (e.g., proximity, essay strength, disability) might you add or adjust?
  Maybe cut off lower, or maybe add some randomness to it, just to make it a chance thing. 


Fairness & Outcomes
● Between the blind and aware models, which applicants benefited or lost out?
Jasmine Okafor  | Blind: 0.72 (Rejected) | Aware: 0.82 (Admitted)

● Which applicants specifically benefited from the aware model?
Jasmine Okafor  | Blind: 0.72 (Rejected) | Aware: 0.82 (Admitted)

● Does adding income or first-generation status make the system fairer or less fair? Why?
More fair. Because money can affect your ability to participate in school.
● Which model feels more fair overall, and why?
The second one. Because more of the economically challenged  

Transparency & Accountability
● How transparent is your algorithm?
● Could you clearly explain a rejection to an applicant?
● Would you feel comfortable if this algorithm evaluated your application? Why or why not 

I think it is quite transparent.
The student who benefited the most was the one who had good test scores and was not far behind on his GPA, and was disabled. if you look at 
Hannah Miller   | Blind: 0.64 (Rejected) | Aware: 0.65 (Rejected)
She had a 3.0 but a 960 test score. she also was not disabled and is wealthy she was not accepted becaus she is not good at taking tests and has no excuse for the pore performance
I would still not feel comfortable if this algorithm evaluated my application
because it is a bit in favor of bad students with good test scores vs 
the latter and students who are first gen 


Broader Implications
● What risks might arise if such an algorithm were used in real admissions?
 It doesn't capture everything about a person.
● What real-world parallels exist (e.g., hiring, policing, scholarships)?
 loan applications, grants for research, and adoptions 
● What does this exercise reveal about fairness in algorithmic decision systems?
 It's hard to make a fair system.
● Can algorithms ever be truly fair, or do they just shift where bias appears?
 I don't think that it can ever be fair. because the concepts don't exist. fair is not something that you can have in the real world.
● How should fairness and accountability be balanced in automated decisions?
 human interventions for close calls or boundary values