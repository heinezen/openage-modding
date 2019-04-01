# Motivation

For games as an interactive medium, interfaces have the important role of giving players access to the game's mechanics annd thus have a huge influence on the fun factor that is achieved by it. However, interface design is often neglected in development, implemented without care or (even worse) without testing user feedback. As a result the games can feel frustrating and inaccessible. We want to show that designing is actually neither hard nor time consuming -- given a little bit of practice -- and that good interfaces lead to more joyful experiences.

# Goals of this guide

This guide introduces the basics of an **iterative development cycle** for user interface design. An iteration consists of four phases: **Analysis**, **Design**, **Prototyping** and **Evaluation**. For each phase, we will introduce various techniques and methods to develop and improve designs. Furthermore, we will provide examples of how these techniques can be used in the context of real-time strategy games.

The examples in this guide will not feature an example design of a complete and fully-functional interface. Instead, we will take a more general approach where we discuss and analyze specific parts of RTS interfaces and derive useful patterns from them. We will also include good and bad examples of interface design in other games.

# Openage engine considerations

Because openage is a multi-purpose RTS engine, it can potentially run many games with each of them targeting different audiences and implementing different design goals. As a result, we cannot provide a "definitive" interface in openage that works for everyone. Therefore, our focus will primarily be on providing a customizable interface with many options for enhancements. This includes the development of **sane defaults** for the interfaces of AoE1, AoE2 and SWGB as well as creating a library of **templates** for common interface patterns. The latter ones can then be used by game developers and modders for their own creations.

The three original Genie Engine games already have a working interface that can act as a reference for our own design. However, we will not shy away from remaking parts of the user interface if its classic version cannot be improved anymore. Furthermore, alternative designs for increasing **accessibility**, e.g. more input devices or color blind modes, will be explored.

# Helpful Literature

This guide is not supposed to be a complete guide on interaction design and will often act more as a reference sheet. Fortunately, there are a lot of great books that go more into detail of which we will now recommend a selection of three. It is recommended to read them, if you want a better understanding of user behavior and perception. Older versions can sometimes be found on the authors' websites.

- *Y. Rogers*, *H. Sharp*, *J. Preece* - Interaction Design: Beyond Human-Computer Interaction

A very comprehensive work on interaction design and also the basis for this guide. Many of the methods we will introduce in our guide are also described in this book with more explanations and examples.

- *B. Shneiderman*, *C. Plaisant* - Designing the User Interface

This book has a tighter focus on the incorporation of design methods into the software development process. It also discusses various input methods different to the classic keyboard and mouse combination. 

- *D. Norman* - The design of everyday things

Not so much about interaction with digital interfaces, but simple objects from your everyday life. Norman discusses the design of door handles, stoves, water faucets, teapots and more to introduce the concept of *user-centered design*. The book is full of examples of both good and bad design and is a great starting point for gaining design experience.
