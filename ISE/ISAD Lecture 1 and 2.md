  
. . . .  
Communication via (Peer) Review  
► Peer review is a two-way communication.  
► The reviewer gains an understanding of your work and  
your ideas.  
► The reviewer offers advice, on:  
► Faults found.  
► Efficiency issues – could your code be faster, or use  
less memory?  
► Maintenance issues – could your code be simpler?  
► Style issues – could your code be more readable?  
► Test case issues – do your test cases cover enough  
of the system’s behavior? ( more on test cases will  
be in later lectures)  

  

# ISAD lecture no 1

We also need to:  
► Co-ordinate a team, and plan and manage a project.  
► Understand user requirements.  
► Design the software (components/modules).  
► Implement the components/modules of the software.  
► Test the software, piece by piece.  
► Verify that the software meets its goals.  
► Maintaining the software  

  

► The “Software Development Life Cycle” is the idea that  
software projects are divided into different kinds of  
activities:  
► Gathering requirements.  
► Designing the system.  
► Implementing the system.  
► Testing and inspecting it.  
► Maintaining (fixing and improving) it.  

  

Common Categories of Life Cycle Models

Common categories :  
► Predictive life cycle: A more traditional approach, with the bulk of planning  
occurring upfront, then executing in a single pass; a sequential process.  
► Iterative life cycle: An approach that allows feedback for unfinished work  
to improve and modify that work. ( e.g.; Iterative waterfall.)  
► Incremental life cycle: An approach that provides finished deliverables  
that the customer may be able to use immediately. ( e.g.; Spiral)  
► Agile life cycle: An approach that is both iterative and incremental to  
refine work items and deliver frequently  

- Predictive models and Agile methods are at extremes but commonly a middle  
    ground is used in the industry.  
      
    

![[Untitled 7.png]]

The Iterative Waterfall Model (Discussion)  
► The software life cycle phases are done one after another, in  
order.  
► It is expected that some “iteration” will be needed.  
► It will take several attempts to get each phase “right”.  
Note : You will encounter iteration when you write code also.  
It’s also called “looping”.  
But here it relates to the humans, rather than the code.  

Non-Iterative Waterfall?  
► “The waterfall model” is often the subject of ridicule.  
► Some people will say it’s outdated and unworkable, and  
an example of what not to do.  
► They are sort-of right, if you squint.  
► There are several things to unpack here:  

1. Often people consider the “waterfall model” to  
    be non-iterative (by default).  
    
2. A non-iterative waterfall is indeed a terrible idea – you  
    can’t correct your mistakes!  
    
3. But, nobody ever actually had the idea in the first place!  
    Some people just got confused.  
    
4. BUT, it is still a useful discussion point on the need  
    for iteration. (Hence this slide!)  
    

![[Untitled 1 3.png]]

The Spiral Model (Discussion)  
► A project’s timeline is divided into cycles (iterations).  
► Each cycle accomplishes something.  
► What it accomplishes is flexible, and not precisely mapped  
out in advance.  
► Not certain how many cycles you will need.  
► But basically, as you get further “outwards”, you get  
further through the life cycle phases: requirements,  
design, coding, testing and maintenance.  
► The Spiral Model makes iteration both more detailed and  
more flexible.  
► By contrast, Iterative Waterfall has iteration, but doesn’t  
really say how it works.  

Parts of a Spiral Cycle  
► Each cycle consists of four parts:  

1. Determine what the cycle is going to accomplish, and  
    possible options for how.  
    
2. Determine the risks of each option (what could go wrong), and  
    resolve them, possibly using prototyping.  
    
3. Develop the material (whether requirements, design, code or  
    testing) that needs to be done, and verify that it’s acceptable.  
    
4. Review the work done, and ensure that everyone is ready  
    to proceed to the next cycle.  
    ► Throughout the software project, we have requirements,  
    design, coding, testing and maintenance.  
    ► The four parts of the cycle address all of the phases.  
    ► The Spiral Model is a systematic way to develop anything in a  
    team.  
    

  

Risk Mitigation” (Playing it Safe)  
► Spiral Model is more suitable when your project is risky.  
► Don’t worry, you’re not going to be in mortal danger. . . 2  
► SE risks are all to do with money and reputation.  
► Every project always has risks:  
► It could go over-budget.  
► It could go over-time.  
► It could fail altogether.  
► Some projects have more risks than others, mainly when  
you don’t have enough information:  
► About what the client wants.  
► About the best way to do something.  
► Prototyping is one way to get more information, to  
help address risks.  

. . . .

  

Prototyping  
► A prototype is a quick piece of work.  
► You may discard them (throw-away) or convert it to usable  
work(evolutionary/incremental etc.)  
► It helps you get early insight into the best ways to design  
your software.  
► The earlier you know something, the fewer mistakes  
you’ll make as a result!  
► User interface (UI) prototypes:  
► A poor UI can make software virtually unusable.  
► The look and layout of the software (on the screen) can  
be a real artform.  
► So, design several mockups of the screen layout, and show  
them to the client.  
► The client may not like them, but you’ll learn useful info.  

  

Project Management methods and SDLCs  
► The Waterfall/Spiral models are very abstract, lofty ideas(Not the  
whole story.)  
► To actually plan and manage a project, we also need  
something more detailed and down-to-Earth.  
► We need to plan our time and resources effectively to  
deliver the intended outcome of the project.  
► To plan and manage SE projects, some project  
management methods used in other domains are  
adopted.  
► Once we know the scope and the goals of the project, we can  
start the planning process with a work breakdown structure  
(WBS).  
► WBS helps to identify tasks, find dependency between tasks, time  
needs to complete the tasks and more information.  

  

Work Breakdown Structure(WBS)  
► We break up a project into a series of tasks.  
► We break up tasks into smaller sub-tasks.  
► Eventually our tasks are “bite-sized” enough that we can  
easily see how to do each one, and how long it will take (  
time estimation).  
► Helps to identify how each task depend on each other (  
dependency identification)  
► Helps the team understand everything that needs to be done.  
► Different tasks get assigned to different team members.  

![[Untitled 2 3.png]]

► A case of “divide-and-conquer”.  
► We’re much better at solving a series of small problems  
than one big one.  
► You’ll see this idea coming up again and again!  
► Not specific to software projects.  
► This is a generic planning tool – you can use it for  
planning any project.  
► Not a schedule.  
► We have more work to do before we get to that.  
► We haven’t even assigned an order to the tasks yet.  
► Not broken down “too far”.  
► Nobody wants to deal with a thousand 1-minute tasks.  

WBS: Dependencies and Milestones  
► Some tasks must be completed before  
others can begin. e.g.  
► We can’t test a game until after it’s been  
coded.  
► To code a game, all four design tasks to  
be complete.  
► We need to know the dependencies.  
► Ideally, we’d like to do things in parallel –  
much faster!  
► Dependencies tell us what can’t be done  
in parallel.  
► Milestones are a way of measuring  
progress.  
► A milestone is “reached” upon completion of a  
specific activity (or activities), so that others  
can begin.  
► Milestones are defined in advance, at the start  
of a project.  

eg….—→

1. Market research
2. Prototyping
3. Game design  
    3.1 identify core game..  
    3.2 Storyline ..  
    3.3 Develop game …  
    3.4 Specify characters  
    
4. Game implementation  
    4.1 Artwork  
    4.2 Coding  
    
5. Testing  
    5.1 Functionality  
    5.2 Playability  
    5.3 Rework  
    
6. Release

![[Untitled 3 3.png]]

![[Untitled 4 3.png]]

Activity Graphs  
► Activity graphs ( project network diagrams / activity  
diagrams) are widely used to show a graphical breakdown  
of a project.  
► Shows which activities depend on which other activities.  
► Two representations:  

Activity-on-Node (AON) – nodes are activities, arcs  
indicate dependencies.  
Activity-on-Arc (AOA) – nodes are milestones, arcs  
are activities.  

  
► These represent the exact same information, but in  
different ways. (One will probably feel more “natural” to  
you.)  
► In both AON and AOA graphs, “start” and “stop” nodes  
represent the beginning and end of a project.  

The entire graphical representation is from page 32/63 !!

Additional notes: Program Evaluation and Review  
Technique (PERT) is given in additional informations in the last pages of the notes  

![[Lecture1_Planning_2024_S1_1pp.pdf]]

![[Untitled 5 2.png]]

I discovered that number of dependencies is equal to number of lines

read page 36 too..!!

  

Estimating the duration of activities  
► Time (or Effort) is Money  
► In SE, you spend money on two main things:  
► Staff salaries (per person per year).  
► Office space (rent per m2 per year).  
(There’s also hardware, various services, etc., but those  
costs are usually relatively small.)  
► And your office space is based on how many staff you have.  
► So, the total cost of an SE project mainly just depends on:  
► How many people it takes.  
► How much time it takes.  
► We often express this in “effort”:  

Effort = Time × Number of People  
(Effort is measured in “person-hours”, “person-months”, etc.)  

  

Estimation Models: COCOMO  
► COCOMO (the COnstructive COst MOdel) 3 lets  
you estimate time and effort of a SE project.  
► It actually doesn’t really work! But why is interesting.  
► Based on statistical “regression”:  
► Boehm collected data on (initially) 61 software projects.  
► Total time, effort and total size (lines of code, or LOC).  
► Other characteristics: team experience and  
interdepenencies on other systems.  
► Created equations to calculate time & effort from size.  
► To use COCOMO, you:  
► Estimate the eventual size (LOC) of your upcoming project.  
► Categorise: experienced/inexperienced team, separate  
from or dependent on other systems, etc.  
► Finally, evaluate the equations  

. . . .  
SE Overview Software Lifecycle Activities Estimation Critical Path Gantt Charts  
Real-World Estimation  
► In reality, cost/time estimation is mostly done on a  
task-by-task basis, using a WBS.  
► Several experienced engineers independently take an educated  
guess, for each task, based on experience and intuition.  
► Estimates are compared, argued over and adjusted.  
► Roughly speaking, this is the Wideband Delphi process.  

![[Untitled 6 2.png]]

![[Untitled 7 2.png]]

► First, we need to know how long the project should  
take.  
► We can do this by Earliest Start (ES) and Earliest Finish  
(EF) time calculation.  
► Find the task with the highest earliest-finish (EF) time.  
► By definition, this is when you expect the project to end.  
► This is the project duration.  
► We find Latest Start (LS) and Latest Finish (LF) also for getting  
other useful information such as critical path  

Watch this 3 videos and you dont need to read any notes regarding this

[https://youtu.be/GRlXRYok3oQ?si=ik560nYB02tM0xeG](https://youtu.be/GRlXRYok3oQ?si=ik560nYB02tM0xeG)

[https://youtu.be/bobDz_Bh3tI?si=Ab-_x3L3Bb6k-Ysu](https://youtu.be/bobDz_Bh3tI?si=Ab-_x3L3Bb6k-Ysu)

[https://youtu.be/4oDLMs11Exs?si=I2fJTT-S2NPoB-vU](https://youtu.be/4oDLMs11Exs?si=I2fJTT-S2NPoB-vU)

[https://youtu.be/jmCc5VIMOro?si=6wTzEPJulRQtuiDL](https://youtu.be/jmCc5VIMOro?si=6wTzEPJulRQtuiDL)

► Assume the project starts on “day 0”.  
► We give each task four other numbers:  
► Earliest Start (ES) and Earliest Finish (EF): given the task’s  
dependencies, when can it first conceivably be started and  
finished?  
► Latest Start (LS) and Latest Finish (LF): when must the task  
be started/finished, so that the project remains on-time?  
► For tasks with no dependencies, ES = 0.  
► You can start them right away.  
► Other tasks can start once their dependencies are complete.  
► ES for task X = highest EF among task X’s dependencies.  
► For all tasks, EF = ES + Duration.  
► This is enough information to find ES and EF for every task.  

![[Untitled 8.png]]

The Critical Path  
► There is always a sequence of activities that each have  
zero slack time.  
► Equivalently, their earliest and latest times are the same.  
► If you delay any of them, you delay the whole project.  
► This is the critical path; each activity on it is a  
critical activity.  
► “Critical” in terms of time, not the final result.  
► “Non-critical” activites are still essential.  
► Monitoring the progress of critical activities will tell  
you whether the whole project is on track or not.  
► Must always span the whole project timeline from start to  
end.  
► Critical path can be find using activity graphs with ES, EF,  
LS, LF information. ( first calculate the slack activities)  

![[Untitled 9.png]]

  

This is the channel for everything regarding the estimation in Lecture 1f

> [!info] Engineer4Free  
> I've made over 500 free engineering tutorials to help engineering students understand and pass the following university courses: C++ programming, calculus, circuits, general chemistry, differential equations, dynamics, engineering economics, fluid mechanics, linear algebra, mechanics of materials, project management, statics, and structural analysis.  
> [https://www.youtube.com/@Engineer4Free](https://www.youtube.com/@Engineer4Free)  

![[Lecture1_Planning_2024_S1_1pp 1.pdf]]

# Lecture 2

Types of Processes in SDLC Software development Life Cycles  
► There are many well-known processes; e.g.:  
► Scrum, Lean Development, Extreme Programming, the Unified  
Process, Team Software Process, etc.  

What are sprints in project management?

A sprint is **a short, time-boxed period when a scrum team works to complete a set amount of work**.  
Sprints are at the very heart of scrum and agile methodologies, and  
getting sprints right will help your agile team ship better software  
with fewer headaches.  

  
► Kanban may be considered a process, or at least part of a  
process.  
► Many (most?) organisations will use a hybrid/customised  
process.  
► Borrowing ideas from several processes and models.  
► What happens in practice is never exactly what you read about in  
books.  
► Most organisations will try to be “agile”.  
► “Agility” means that you can deal well with changing  
situations.  
► Scrum is one of the best-known agile processes.  
► These often look a lot like a case of the spiral model.  
► We focus on Scrum in ISE because we can’t cover everything!  

![[Untitled 10.png]]

![[Untitled 11.png]]

The Two Backlogs

► A backlog is a list of user stories not yet implemented.

► User stories represent user needs. Each user storyrepresents a piece of software functionality for a particularkind of user.

► In Scrum, you keep track of two backlogs.

► The “Product Backlog” – a todo list for the overall product.

► Everything the customer wants the software to do that hasnot yet been implemented.

► The “Sprint Backlog” – a todo list for the current sprint.

► Select a few user stores from the product backlog, at thestart of the sprint

► Each user story takes time to implement, and you only have 4 weeks.

► Go for the “highest priority” user stories.

► You may not necessarily ﬁnish them all in this sprint.

► Each user story may need to be broken down into sub-tasks!

  

Sprint Meetings (“Ceremonies”)  
Each sprint has several key meetings between the people  
involved:  
► Sprint Planning is typically a day-long meeting at the start of a sprint.  
► The developers talk to the customer and figure out what to  
do for the next 4 weeks.  
► Sprint Review is typically a half a day meeting at the end of a sprint.  
► The developers show the customer what has been done.  
► Sprint Retrospective is another one day meeting right after the sprint  
review.  
► The developers discuss how well things went, and what might be  
improved.  
► This is about the team itself, not the product.  
► Daily Scrum (or “stand-up”) is a 15-minute meeting at the start of  
each day.  
► The developers discuss their planned work for the day.  

  

Scrum Roles  
► Scrum assigns special roles to people.  
► The Product Owner helps the team make the right product.  
► They make sure user stories are correct, and decide which  
have the highest priority.(The PO is not the customer though.)  
► Responsible for delivering the product (as much value as  
possible)  
► The Scrum Master helps the team follow Scrum.  
► They must be on top of all the Scrum practices.  
► They must understand what should happen when, and make  
sure everyone else is aware of this.  
► The Development Team writes the software.  
► 3–9 software developers.  
► They take user stories and implement them.  

Tools for monitoring projects :  
► Conventionally, Gannt chart is updated while the  
project is progressing.  
► Now , many other tools are also being adopted.  

> Tools for software project monitoring  
> ►Burn-up charts  
> ►Kanban boards  

![[Untitled 12.png]]

Kanban  
► Kanban boards are another way to visualise your  
project.  
► Burn-up charts show the big picture.  
► Kanban shows the status of individual tasks, related  
to the workflow.  
► A visulaization tool.  
► Kanban boards contain columns.  
► One column for each workflow step, arranged  
left-to-right  

![[Untitled 13.png]]

► Kanban boards contain columns.  
► One column for each workflow step, arranged left-to-  
right; e.g. “Todo”, “Selected”, “Coding/testing”,  
“Review”, “Ready to merge” and “Done”.  
► Columns contain “cards”.  
► Each card represents a task.  
► Each card (task) is moved from left-to-right (from  
column to column) as it progresses through its steps.  

  

Work In Progress: Enforcing Limits  
► We might put a limit of (say) 3 tasks in the coding/testing, and 3  
in review.  
► So, if there are already 3 tasks under review. . .  
► We can’t move another task from coding/testing to review.  
► One of the existing reviews has to complete first.  
► This may cause a “pile-up” in an earlier column.  
► But, in a sense, this is actually a good  
thing, because it lets us see an  
underlying problem.  
► We can identify parts of our process  
that are “bottlenecks” (slow points),  
and re-assign team members to deal  
with them.  
► The review stage is holding everything  
up? Then we need  
more reviewers and fewer coders.  

  

More functionality and “Bugfixes” and as Tasks  
► You can add more cards to the “todo” column, mid-project.  
► The client may (all of a sudden) want more functionality.  
► Or you might discover problems (bugs) that need to be fixed.  
► These tasks needs to follow the same flow; start from “to-do” and move  
forward.  

  

. . . .  
. . . .  
Scrum and Kanban  
► Scrum and Kanban are not the same thing.  
► e.g. Kanban has no fixed-length sprints, and instead  
delivers each user story by itself incrementally.  
► But they can be joined into a single process –  
“Scrumban”.  
► The sprint backlog could be the left-most column on  
your Kanban board.  
► What ends up in the “done” column is what you deliver,  
at the end of the sprint.  

  

Code Review  
► A collection of techniques for achieving two ends:  

1. for one person (or the rest of the team) to understand  
    another’s work (code), and  
    
2. to find faults in that work  
    Helps to improve code quality.  
    ► Different techniques:  
    ► Formal Inspection – formal group-based fault-detection process,  
    ► Walkthrough – informal meeting to understand the code,  
    ► Pair Programming – programmers write all code in pairs, with  
    one reviewing the other’s work in real-time. (And roles  
    swapping as needed.)  
    ► Over-the-shoulder – show our code to a colleague  
    ► …...  
    ► In all cases, you requires someone other than the author of  
    the work.  
    ► . . . but someone who is familiar with the project.  
    ► A peer.  
    ► Code review is sometimes referring as peer review.  
    From Planning to Doing KanbanScrum Code ReviewsBurn-up charts  
    

  

Pull Requests and Code Reviews  
► Typically, a developer makes a “pull  
request” when they think they’ve finished  
a task. ( more in week 5)  
► Your code will be discussed, and  
your request accepted or rejected.  
► Pull requests typically trigger a “code review”.  
► Another team member will look through your code in  
detail.  
► They’ll check:  
► Whether your changes do what is needed.  
► Whether they break other things.  
► Whether they’re otherwise up-to-standard.  
► They often find defects, and will ask you to fix them  

  

. . . .  
. . . .  
Communication via (Peer) Review  
► Peer review is a two-way communication.  
► The reviewer gains an understanding of your work and  
your ideas.  
► The reviewer offers advice, on:  
► Faults found.  
► Efficiency issues – could your code be faster, or use  
less memory?  
► Maintenance issues – could your code be simpler?  
► Style issues – could your code be more readable?  
► Test case issues – do your test cases cover enough  
of the system’s behavior? ( more on test cases will  
be in later lectures)  

More detailed version of information starts from page no 35/49 from the pdf file

![[Introduction_to_Software_Engineering_(ISAD1000)_-_Lecture_1_Planning_-_Lecture1_Planning_2024_S1_1pp.pdf]]

![[Lecture2_AgileProjectManagement_2024_S1_1pp.pdf]]