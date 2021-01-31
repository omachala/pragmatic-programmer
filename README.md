# Pragmatic Programmer
Andrew Hunt David Thomas, 1999

List of my notes:

## Building Your Portfolio

- **Invest regularly.**
Just as in financial investing, you must invest in your knowledge portfolio regularly. Even if it's just a small amount, the habit itself is as important as the sums. A few sample goals are listed in the next section.

- **Diversify.** The more different things you know, the more valuable you are. As a baseline, you need to know the ins and outs of the particular technology you are working with currently. But don't stop there. The face of computing changes rapidly—hot technology today may well be close to useless (or at least not in demand) tomorrow. The more technologies you are comfortable with, the better you will be able to adjust to change.

- **Manage risk.** Technology exists along a spectrum from risky, potentially high-reward to low-risk, low-reward standards. It's not a good idea to invest all of your money in high-risk stocks that might collapse suddenly, nor should you invest all of it conservatively and miss out on possible opportunities. Don't put all your technical eggs in one basket.

- **Buy low, sell high.** Learning an emerging technology before it becomes popular can be just as hard as finding an undervalued stock, but the payoff can be just as rewarding. Learning Java when it first came out may have been risky, but it paid off handsomely for the early adopters who are now at the top of that field.

- **Review and rebalance.** This is a very dynamic industry. That hot technology you started investigating last month might be stone cold by now. Maybe you need to brush up on that database technology that you haven't used in a while. Or perhaps you could be better positioned for that new job opening if you tried out that other language….


## Goals

- **Learn at least one new language every year.** Different languages solve the same problems in different ways. By learning several different approaches, you can help broaden your thinking and avoid getting stuck in a rut. Additionally, learning many languages is far easier now, thanks to the wealth of freely available software on the Internet.

- **Read a technical book each quarter.** Bookstores are full of technical books on interesting topics related to your current project. Once you're in the habit, read a book a month. After you've mastered the technologies you're currently using, branch out and study some that don't relate to your project.

- **Read nontechnical books, too.** It is important to remember that computers are used by people—people whose needs you are trying to satisfy. Don't forget the human side of the equation.

- **Take classes.** Look for interesting courses at your local community college or university, or perhaps at the next trade show that comes to town.

- **Participate in local user groups.** Don't just go and listen, but actively participate. Isolation can be deadly to your career; find out what people are working on outside of your company. Experiment with different environments. If you've worked only in Windows, play with Unix at home (the freely available Linux is perfect for this). If you've used only makefiles and an editor, try an IDE, and vice versa.

- **Stay current.** Subscribe to trade magazines and other journals (see page 262 for recommendations). Choose some that cover technology different from that of your current project.

- **Get wired.** Want to know the ins and outs of a new language or other technology? Newsgroups are a great way to find out what experiences other people are having with it, the particular jargon they use, and so on. Surf the Web for papers, commercial sites, and any other sources of information you can find.

## Critical Thinking

Think critically about what you read and hear. You need to ensure that the knowledge in your portfolio is accurate and unswayed by either vendor or media hype. Beware of the zealots who insist that their dogma provides the only answer—it may or may not be applicable to you and your project. Never underestimate the power of commercialism. Just because a Web search engine lists a hit first doesn't mean that it's the best match; the content provider can pay to get top billing. Just because a bookstore features a book prominently doesn't mean it's a good book, or even popular; they may have been paid to place it there

## Care and Cultivation of Gurus
- Know what you want to say.
- Know your audience.
- Choose your moment.
- Choose a style.
- Make it look good.
- Involve your audience.
- Be a listener.
- Get back to people.

## A Pragmatic Approach

How Does Duplication Arise

- **Imposed duplication** Developers feel they have no choice—the environment seems to require duplication.

- **Inadvertent duplication** Developers don't realize that they are duplicating information.

- **Impatient duplication** Developers get lazy and duplicate because it seems easier.

- **Interdeveloper duplication** Multiple people on a team (or on different teams) duplicate a piece of information.

## Organizing team
How do you organize teams into groups with well-defined responsibilities and minimal overlap? There's no simple answer. It depends partly on the project and your analysis of the areas of potential change. It also depends on the people you have available. Our preference is to start by separating infrastructure from application. Each major infrastructure component (database, communications interface, middleware layer, and so on) gets its own subteam. Each obvious division of application functionality is similarly divided. Then we look at the people we have (or plan to have) and adjust the groupings accordingly.

## Code
- **Keep your code decoupled** - Write shy code—modules that don't reveal anything unnecessary to other modules and that don't rely on other modules' implementations.

- **Avoid global data** - Every time your code references global data, it ties itself into the other components that share that data. Even globals that you intend only to read can lead to trouble. In general, your code is easier to understand and maintain if you explicitly pass any required context into your modules.

- **Avoid similar functions** - Often you'll come across a set of functions that all look similar—maybe they share common code at the start and end, but each has a different central algorithm. Duplicate code is a symptom of structural problems. Have a look at the Strategy pattern in Design Patterns for a better implementation.

### Always Use Source Code Control
Always. Even if you are a single-person team on a one-week project. Even if it's a "throw-away" prototype. Even if the stuff you're working on isn't source code. Make sure that everything is under source code control—documentation, phone number lists, memos to vendors, makefiles, build and release procedures, that little shell script that burns the CD master—everything. We routinely use source code control on just about everything we type (including the text of this book). Even if we're not working on a project, our day-to-day work is secured in a repository.

### Minimize Coupling
What's wrong with having modules that know about each other? Nothing in principle—we don't need to be as paranoid as spies or dissidents. However, you do need to be careful about how many other modules you interact with and, more importantly, how you came to interact with them.
Suppose you are remodeling your house, or building a house from scratch. A typical arrangement involves a "general contractor." You hire the contractor to get the work done, but the contractor may or may not do the construction personally; the work may be offered to various subcontractors. But as the client, you are not involved in dealing with the subcontractors directly—the general contractor assumes that set of headaches on your behalf.
We'd like to follow this same model in software. When we ask an object for a particular service, we'd like the service to be performed on our behalf. We do not want the object to give us a third-party object that we have to deal with to get the required service.

## Dynamic Configuration
We want to make our systems highly configurable. Not just things such as screen colors and prompt text, but deeply ingrained items such as the choice of algorithms, database products, middleware technology, and user-interface style. These items should be implemented as configuration options, not through integration or engineering.

## Metadata-Driven Applications
Not just using metadata for simple preferences. We want to configure and drive the application via metadata as much as possible. Our goal is to think declaratively (specifying what is to be done, not how) and create highly dynamic and adaptable programs. We do this by adopting a general rule: program for the general case, and put the specifics somewhere else—outside the compiled code base.

## How to Program Deliberately
We want to spend less time churning out code, catch and fix errors as early in the development cycle as possible, and create fewer errors to begin with. It helps if we can program deliberately:

- Always be aware of what you are doing.
- Don't code blindfolded. Attempting to build an application you don't fully understand, or to use a technology you aren't familiar with, is an invitation to be misled by coincidences.
- Proceed from a plan, whether that plan is in your head, on the back of a cocktail napkin, or on a wall-sized printout from a CASE tool.
- Rely only on reliable things. Don't depend on accidents or assumptions. If you can't tell the difference in particular circumstances, assume the worst.
- Document your assumptions. Design by Contract, can help clarify your assumptions in your own mind, as well as help communicate them to others.
- Don't just test your code, but test your assumptions as well. Don't guess; actually try it. Write an assertion to test your assumptions (see Assertive Programming). If your assertion is right, you have improved the documentation in your code. If you discover your assumption is wrong, then count yourself lucky.
- Prioritize your effort. Spend time on the important aspects; more than likely, these are the hard parts. If you don't have fundamentals or infrastructure correct, brilliant bells and whistles will be irrelevant.
- Don't be a slave to history. Don't let existing code dictate future code. All code can be replaced if it is no longer appropriate. Even within one program, don't let what you've already done constrain what you do next—be ready to refactor (see Refactoring). This decision may impact the project schedule. The assumption is that the impact will be less than the cost of not making the change.

### A Debugging Mindset

- Before you start debugging, it's important to adopt the right mindset. You need to turn off many of the defenses you use each day to protect your ego, tune out any project pressures you may be under, and get yourself comfortable. Above all, remember the first rule of debugging: Don't panic.
- You may need to interview the user who reported the bug in order to gather more data than you were initially given.
- Artificial tests (such as the programmer's single brush stroke from bottom to top) don't exercise enough of an application. You must brutally test both boundary conditions and realistic end-user usage patterns. You need to do this systematically
- Don't Assume It—Prove It

## Refactoring

- **Duplication.** You've discovered a violation of the DRY principle (The Evils of Duplication).
- **Nonorthogonal design.** You've discovered some code or design that could be made more orthogonal (Orthogonality).
- **Outdated knowledge.** Things change, requirements drift, and your knowledge of the problem increases. Code needs to keep up.
- **Performance.** You need to move functionality from one area of the system to another to improve performance.

How to:

1. Don't try to refactor and add functionality at the same time.
2. Make sure you have good tests before you begin refactoring. Run the tests as often as possible. That way you will know quickly if your changes have broken anything.
3. Take short, deliberate steps: move a field from one class to another, fuse two similar methods into a superclass. Refactoring often involves making many localized changes that result in a larger-scale change. If you keep your steps small, and test after each step, you will avoid prolonged debugging.


# List of General Tips

- We feel that there is no point in developing software unless you care about doing it well. 
- Think! About Your Work
- Provide Options, Don't Make Lame Excuses 
- Don't Live with Broken Windows
- Be a Catalyst for Changes
- Remember the Big Picture 
- Make Quality a Requirements Issue
- Invest Regularly in Your Knowledge Portfolio
- Critically Analyze What You Read and Hear
- It's Both What You Say and the Way You Say It
- DRY—Don't Repeat Yourself
- Make It Easy to Reuse 
- Eliminate Effects Between Unrelated Things
- There Are No Final Decisions
- Use Tracer Bullets to Find the Target
- Prototype to Learn
- Program Close to the Problem domain 
- Estimate to Avoid Surprises 
- Iterate the Schedule with the Code 
- Keep Knowledge in Plain Text 
- Use the Power of Command Shells 
- Use a Single Editor Well 
- Always Use Source Code Control
- Fix the Problem, Not the Blame 
- Don't Panic 
- Don't Assume It—Prove It 
- Learn a Text Manipulation Language 
- Write Code That Writes Code 
- You Can't Write Perfect Software 
- Design with Contracts 
- Crash Early 
- If It Can't Happen, Use Assertions to Ensure That It Won't 
- Use Exceptions for Exceptional Problems 
- Finish What You Start 
- Minimize Coupling Between Modules 
- Configure, Don't Integrate 
- Put Abstractions in Code Details in Metadata 
- Analyze Workflow to Improve Concurrency
- Design Using Services 
- Always Design for Concurrency 
- Separate Views from Models 
- Use Blackboards to Coordinate Workflow 
- Don't Program by Coincidence 
- Estimate the Order of Your Algorithms 
- Test Your Estimates 
- Refactor Early, Refactor Often 
- Design to Test 
- Test Your Software, or Your Users Will 
- Don't Use Wizard Code You Don't Understand 
- Don't Gather Requirements—Dig for Them
- Work with a User to Think Like a User 
- Abstractions Live Longer than Details 
- Use a Project Glossary 
- Don't Think Outside the Box—Find the Box 
- Listen to Nagging Doubts—Start When You're Ready 
- Some Things Are Better Done than Described 
- Don't Be a Slave to Formal Methods 
- Organize Around Functionality, Not Job Functions 
- Don't Use Manual Procedures 
- Test Early. Test Often. Test Automatically. 
- Coding Ain't Done 'Til All the Tests Run 
- Use Saboteurs to Test Your Testing 
- Test State Coverage, Not Code Coverage 
- Find Bugs Once 
- Treat English as Just Another Programming Language 
- Gently Exceed Your Users' Expectations 
- Sign Your Work

