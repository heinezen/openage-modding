# Agenda

(Analysis, Design, Prototype, Evaluation diagram)

Sections of this guide will follow the 4 phases **Analysis**, **Design**, **Prototyping** and **Evaluation** of the iterative development cycle. The **Requirements** phase that precedes the first iteration of the cycle will be briefly discussed, but is not the focus.

- **Requirements**: Acts as a formal setup phase for the design process. Here the development team decides what the project will be (in our case an RTS games), what its scope is, how much time is dedicated to each phase and which team member is responsible for which task.

- **Analysis**: We will present methods that can help identify the users of the UI as well as their needs, tasks and goals. Furthermore, we are introducing a few simple rules about perception from Gestalt psychology that can be used to judge existing user interfaces.
    - Understanding users
    - Interviews
    - Personas
    - User Stories
    - Scenarios
    - GOMS
    - HTA
    - Fitt's Law, Hick's Law, Steering Law
- **Design**: We will discuss basic design rules and go through important criterias for good design. Additionally, different approach to styling are explored.
    - Creativity
    - Gestalt psychology
    - Form follows function
    - Criterias (function, ergonomy, aesthetics, joy, symbolism)
    - Affordances
    - Skeuomorphism/flat/seamless design
    - Mental models (conceptional models, mappings, image schemata)
    - Principles, heuristics, patterns, standards, style guides (design guidelines)
- **Prototyping**: This phase is all about putting the design into practice by building prototypes. Various ways of prototyping as well as their advantages and disadvantages will be examined.
    - Human Action Cycle
    - Throw-away vs. evolutionary prototypes
    - Sketches, paper prototype, video prototype, wizard of oz
    - Wireframes
    - Mockups
    - Bottlenecks
- **Evaluation**: This phase puts a focus on empirical and analytical evaluation of prototypes. In addition to this, we will briefly discuss statistical tests.
    - Empirical methods
    - Explorative vs. hypothesis-based
    - Qualitative and quantitative results
    - Usability criterias
    - DECIDE framework
    - Cognitive walkthrough
    - Heuristical evaluation
    - Statistical tests

## Excursions

Excursions will deal with common UI patterns in strategy games such as the minimap, command panels and contextual cursors. Every excursion will discuss one specific pattern and their examples implementations from existing games.

## Misconceptions about Design

There are misconceptions about design processes that get repeated ever so often. Here are some examples:

* **Design is purely aesthetics**: Although aesthetics play an important role in design, they are not the only important aspect. Good design incorporates many other factors, including function, ergonomy, joy and symbolism, into the product. Visual aesthetics should complement the other factors, not work against them.
* **As a designer, you just need to be creative**: Creativity is not enough! Every design process involves a lot of analysis and research before the creative part kicks in. Finding out what your users want and what the project should accomplish is a necessary requirement to the creative process. Your design should never be random and always have reason.
* **It's the user's fault/RTFM/Error in OSI Layer 8**: Probably the worst misconception of them all because it doesn't solve anything. Neither does is make the design better nor does it help the user (who will instead become frustrated). When designing a user interface for an RTS, you have to remember that users want to play the game, not with your interface. Good design supports users and does not hinder them.
* **Users are a burden to the design process**: No, users are the most important reference for every designer. It often might seem like users do not know what they want and can therefore be ignored, but that is not actually true. Users usually know very well what they want, but cannot formulate it properly. "Translating" user feedback to interface requirements is an important part of interface design and will always pay off.
* **Old = bad, new = good**:
