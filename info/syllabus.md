# Syllabus

## Course information for A ATM 622: General Circulation of the Atmosphere

### Essential details

- Class number: 9006 (Fall 2026)
- Meeting time: Tuesday / Thursday 1:30 - 2:50 PM in ETEC 480
- Prerequisites: _A ATM 500 Atmospheric Dynamics_
- Credit hours: 3

### Instructor and office hours

- Instructor: [Brian Rose](https://www.atmos.albany.edu/facstaff/brose/)
- Email: <brose@albany.edu>
- Office: ETEC 404
- Office hours: after class or by appointment

### Course website

Most of the course content, including a detailed schedule, will be delivered through a website maintained by Professor Rose: 

[https://brian-rose.github.io/general-circulation/](https://brian-rose.github.io/general-circulation/)

### Grading: A-E, 3 credit
- Assignments and Labs: 60%
- Term project and presentation: 40%

Late assignments/labs, makeup exams, late term projects/presentations will only be allowed for university recognized reasons. Please discuss absences and late work with Prof. Rose in advance whenever possible.

### Resources and references

There is no single required textbook for the course. Professor Rose may at times distribute papers or book exerpts for reading assignments.

One particularly useful and up-to-date book is [_The Atmospheric General Circulation_ by Wallace, Battisti, Thompson, and Hartmann (2023)](https://agc.atmos.uw.edu/index.html). The book is for sale in hardcover print or electronic format from [Cambridge University Press](https://www.cambridge.org/highereducation/books/the-atmospheric-general-circulation/). There is a copy at the UAlbany Science Library.

## Course description

The course will explore fundamental questions about why the circulation looks the way it does, bringing together observations, theory, and models. The [bulletin description](https://www.albany.edu/graduatebulletin/a_atm.htm) says

> Processes which maintain the general circulation of the Earth's atmosphere; investigation of observed angular momentum, energy and water vapor budgets of the atmosphere; atmospheric energetics; application of numerical methods to studies of the general circulation.

Our approach will be hands-on and data-centric wherever possible. We will put significant emphasis on reproducible workflows to generate the maps and diagnostics we look at. So in addition to fundamental science, the course should arm you with a useful toolkit of modern Python-based analysis tools. We will also spend some time in the Fluids lab carrying out rotating tank experiments to complement the observations and theory.

## Final project

Each student will investigate some aspect of the general circulation of atmosphere or ocean. A wide variety of topics are possible, but it must fit into the themes of the class. The project should include some original calculations using real data. Possible ideas include:

- Using methods introduced in class in some aspect of your own thesis research
- Revisit a classic study from the literature with a modern dataset
- Design and implement your own laboratory / tank experiment to investigate some analog of the general circulation

Students will write short proposals for their project ideas and get feedback from the instructor before starting (due dates TBD).

Both written and oral presentations are required. Oral presentations will happen in the last week of class. Details for these and the written presentations will follow later, but expect a focus on *reproducibility* of calculations. Written reports will likely take the form of self-computing Jupyter notebooks.

## Learning outcomes

In this course, students will achieve the following:

- Become familiar with the long-term observed structure of the atmosphere and its circulation.
- Develop an understanding of the classical theories for the maintenance of the observed circulation.
- Become aware of the limitations of those theories, including areas of current active research.
- Gain skills in data-intensive analysis and visualization using modern, cloud-based tools.
- Apply theoretical and data-analysis methods developed in this course to an original research problem.
- Communicate their research results clearly in oral and written form, with an emphasis on computational reproducibility.

## Academic integrity and use of generative AI tools

In this class we will strive to be interactive, learning by doing and by discussion. Some collaboration on exercises is therefore encouraged. However you are ultimately expected to submit **your own work** and **your own thoughts**, and to **give proper credit to others** for previous work and ideas.

**This is very important when writing computer code!** There is nothing wrong with borrowing useful pieces of code from classmates or online sources  (including code generators) -- in fact reuse is the central principle of open-source software. 

However, **you must always acknowledge the original author(s)**. The chatbot that you may use to generate useful code will often provide links to original sources. Follow these links and cite sources to the best of your ability. This effort is not just good scholarship (which is required), but it is also part of your learning process about the code. Ultimately you are responsible for the intellectual content of the code you apply to your research problem. You must, wherever practical, **understand** the code you are borrowing and be able to explain what it does.

If you submit nearly-identical code as a classmate for part of an assignment, you need to include a statement describing the nature of the collaboration, e.g. “I worked together with xxxxx to figure out how to plot this figure”, or “I borrowed these lines of code from xxxxx”. Prof. Rose reserves the right to ask any student individually to explain any code that is submitted as one’s own work.

Generative AI tools such as ChatGPT, Claude Code, Microsoft CoPilot, etc. can be very powerful assistants to the code-writing process, and their use _can align with the learning goals of this course_. But they can also easily lead us astray. It is therefore particularly important to use them wisely and skeptically. Permitted uses in this course include:

- Suggesting Python code as a starting point for some data analysis and visualization
- Finding and summarizing information on a topic for your own planning purposes
- Brainstorming project ideas

The key point is that when you submit work with your name on it, you are responsible and are claiming ownership over the content. Before submitted your work, consider asking yourself questions such as

- Do you understand what the code is doing? 
- Do you think your result is correct and consistent with what is being asked? 
- Do your written answers accurately reflect your own personal understanding of the topic? 
- Are you respecting the intellectual property of original sources? 

The use of generative AI tools is **not permitted in this course** for any activity that amounts to impersonating you in classroom contexts, such as by using the tool to compose entire sentences or paragraphs for written components of assignments or research projects. Such uses run afoul of UAlbany’s academic integrity standards and will be treated accordingly.

It is every student's responsibility to become familiar with the standards of academic integrity at UAlbany. Claims of ignorance, of unintentional error, or of academic or personal pressures are not sufficient reasons for violations of academic integrity. Please refer to the UAlbany academic integrity policies here: <https://www.albany.edu/graduate-bulletin/regulations-and-degree-requirements.php>

## Course outline

_Roughly one to two weeks per topic. Schedule and topics are subject to change based on time available and student interests._

1. Earth's radiation budget
1. Computing seasonal and monthly means from reanalysis data
1. The observed circulation
1. Decompositions of the circulation
1. Angular momentum budget
1. Energy budget
1. Available potential energy and the Lorenz energy cycle
1. Theories of the Hadley circulation
1. Planetary waves
1. Effect of eddies on the zonal mean circulation
