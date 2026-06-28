# CS230.Mod8
8-2 Journal: Portfolio


 

Draw It or Lose It
CS 230 Project Software Design Template
Version 1.0
 Table of Contents

CS 230 Project Software Design Template	1
Table of Contents	2
Document Revision History	2
Executive Summary	3
Requirements	3
Design Constraints	3
System Architecture View	3
Domain Model	3
Evaluation	4
Recommendations	5


Document Revision History

Version	Date	Author	Comments
1.0	5/21/2026	Isaiah Bell	Initial software design document for The Gaming Room

Instructions 
Fill in all bracketed information on page one (the cover page), in the Document Revision History table, and below each header. Under each header, remove the bracketed prompt and write your own paragraph response covering the indicated information.  Executive Summary

     The Gaming Room would like to expand their current Android game, Draw It or Lose It, into a web-based application capable of supporting multiple platforms and users simultaneously. The goal of this project is to create a distributed application that allows players on different operating systems and devices to access the game through a web browser while maintaining a consistent user experience.

     The proposed solution is a Java-based web application that uses object-oriented programming principles and software design patterns to efficiently manage game data and user interactions. The application will support multiple teams and players while enforcing unique game and team names. To ensure that only one instance of the game service exists in memory, the singleton design pattern will be implemented. Iterator patterns will also be used to search collections efficiently when validating unique names and retrieving game data. This approach allows the software to scale more effectively while maintaining clean, reusable, and maintainable code.

Requirements

     The Gaming Room requires a web-based version of Draw It or Lose It that supports multiple operating systems and devices. The application must allow multiple teams to participate in games, with each team containing multiple players. Every game, team, and player must have a unique identifier and unique name to prevent duplication. Only one instance of the game service can exist in memory at a time. The system should also be scalable, secure, maintainable, and accessible across multiple platforms including Windows, Linux, Mac, and mobile devices.

Design Constraints

     One major design constraint is that the application must operate in a distributed web-based environment rather than a single-device Android application. This means the software must support multiple simultaneous users, network communication, and cross-platform compatibility. The development team must also consider browser compatibility, server performance, latency, and data synchronization across devices.

     Another constraint is maintaining unique game, team, and player names while ensuring only one game service instance exists in memory. These constraints require careful implementation of object-oriented design patterns such as the singleton pattern and iterator pattern. Security is also an important consideration because user data and network communication must be protected. Additionally, the application must remain scalable so it can support growth in the number of users and games over time.

System Architecture View

     The Draw It or Lose It application will use a client-server architecture. Users will access the game through web browsers or mobile devices connected to a centralized server. The server will manage game sessions, player information, team management, and communication between connected users.

     The application will use Java for the backend logic because Java supports portability, scalability, and object-oriented development. The server will interact with storage systems to maintain game and user information while distributing data to connected clients through standard network protocols.

Domain Model

     The UML domain model demonstrates inheritance and object relationships between the Entity, Game, Team, Player, and GameService classes. The Entity class serves as the base class and contains shared attributes such as id and name. The Game, Team, and Player classes inherit from Entity, which demonstrates the object-oriented principle of inheritance. This reduces duplicate code and improves maintainability because shared functionality only needs to be implemented once.

     The Game class contains multiple Team objects, while each Team object contains multiple Player objects. This demonstrates composition because teams and players exist as part of the game structure. The GameService class manages collections of games and controls object creation. The singleton pattern is used within GameService to ensure that only one instance exists in memory at any given time. Iterator patterns are used when searching for games, teams, and players by name.

     Encapsulation is also demonstrated because each class manages its own data and behaviors through methods. These object-oriented principles help fulfill the software requirements efficiently while improving modularity, readability, and scalability.

 

Evaluation

Using your experience to evaluate the characteristics, advantages, and weaknesses of each operating platform (Linux, Mac, and Windows) as well as mobile devices, consider the requirements outlined below and articulate your findings for each. As you complete the table, keep in mind your client’s requirements and look at the situation holistically, as it all has to work together. 

In each cell, remove the bracketed prompt and write your own paragraph response covering the indicated information. 

Development Requirements	Mac	Linux	Windows	Mobile Devices
Server Side	
Mac servers provide strong stability and security but are more expensive and less commonly used for enterprise web hosting. They are reliable for development but less practical for large-scale deployment.	
Linux is highly efficient, secure, and cost-effective for server-side hosting. It is widely used for web applications because of its stability, scalability, and open-source support.	
Windows servers provide strong compatibility with Microsoft technologies and enterprise tools but require licensing costs and greater system resources.	
Mobile devices are not suitable for hosting large-scale web applications because they have limited processing power, storage, and network reliability.
Client Side	Mac systems provide strong performance and a reliable user experience for web applications. However, development and testing on Mac hardware may increase costs.	Linux supports web applications well but has a smaller desktop user base, which may limit testing requirements.	Windows supports the largest number of desktop users and browsers, making it important for compatibility testing and support.	Mobile devices require responsive design and optimization for smaller screens, touch controls, and varying hardware capabilities.
Development Tools	Mac supports Java, Eclipse, IntelliJ IDEA, and Xcode for development. It is commonly used for cross-platform and mobile application testing.	Linux supports Java development tools and server technologies very well. Developers often use Eclipse, IntelliJ IDEA, Git, and Apache on Linux systems.	Windows supports many development tools including Visual Studio Code, Eclipse, IntelliJ IDEA, and Git. It is widely used for enterprise software development.	Mobile development requires testing tools such as Android Studio and mobile browser emulators to ensure compatibility across devices.

 Recommendations

Analyze the characteristics of and techniques specific to various systems architectures and make a recommendation to The Gaming Room. Specifically, address the following:

1.	Operating Platform: Linux is the recommended operating platform for The Gaming Room because it provides strong security, scalability, reliability, and cost efficiency for web-based applications. Linux servers are widely used in enterprise environments and support Java applications effectively. Its open-source nature also reduces licensing costs while providing flexibility for future growth.
2.	Operating Systems Architectures: The recommended architecture uses a distributed client-server model where users connect to centralized servers through web browsers and mobile devices. The server handles business logic, data processing, authentication, and communication between users. This architecture allows the game to scale efficiently as the number of users increases.
3.	Storage Management: A relational database management system such as MySQL or PostgreSQL is recommended for storing user accounts, game sessions, team data, and player information. These systems provide strong reliability, security, and support for concurrent users.
4.	Memory Management: The Java Virtual Machine (JVM) provides automatic memory management through garbage collection. This helps prevent memory leaks and improves application stability. The singleton pattern also helps reduce unnecessary memory usage by ensuring that only one instance of the GameService class exists.

5.	Distributed Systems and Networks: The application should use standard web technologies such as HTTP and HTTPS to communicate between servers and client devices. Distributed systems allow multiple users to connect simultaneously from different operating systems and locations. Redundant servers and reliable network infrastructure should be used to reduce downtime and improve availability.

6.	Security: Security measures should include encrypted communication using HTTPS, secure password storage, authentication controls, and input validation to protect user information. Firewalls, server monitoring, and regular security updates should also be implemented to reduce vulnerabilities. Linux provides strong built-in security features that make it a reliable platform for hosting the application.



Briefly summarize The Gaming Room client and their software requirements. Who was the client? What type of software did they want you to design?

The client was The Gaming Room. They wanted to take their game, Draw It or Lose It, which originally only worked on Android, and turn it into a web-based application that could be played across different operating systems. The game needed to support multiple teams and players while making sure there was only one game running at a time. It also needed to make sure every game, team, and player had a unique name. The overall goal was to create a design that was reliable, secure, and could grow as more users played the game.

What did you do particularly well in developing this documentation?

I think I did a good job explaining why certain design decisions would work best for the client. Instead of just listing different operating systems and technologies, I compared their strengths and weaknesses and explained why some options were a better fit than others. This helped me understand that every decision in software design should have a reason behind it and should support what the client is trying to accomplish.

What about the process of working through a design document did you find helpful when developing the code?

The design document helped me organize my thoughts before writing any code. It made me think about the overall structure of the program, how different parts would work together, and what problems I might run into later. Having everything planned out first made it much easier to understand what needed to be built instead of trying to figure everything out while coding.

If you could choose one part of your work on these documents to revise, what would you pick? How would you improve it?

If I could go back and change one part, I would spend more time explaining the overall system design and include more detailed diagrams. I understand software architecture much better now than I did when I first completed this project, so I think I could give clearer explanations of how the different components communicate with each other and why certain design choices were made.

How did you interpret the user's needs and implement them into your software design? Why is it so important to consider the user's needs when designing?

I started by focusing on what the client wanted the software to do and then built the design around those requirements. For example, I made sure the design supported multiple players and teams, prevented duplicate names, and could run on different platforms. Keeping the user's needs in mind is important because even well-written software won't be successful if it doesn't solve the problem the client asked you to solve. Understanding those needs helps create software that is easier to use, more reliable, and better prepared for future growth.

How did you approach designing software? What techniques or strategies would you use in the future to analyze and design a similar software application?

When designing the software, I broke the project into smaller pieces instead of trying to think about everything at once. I looked at the client's requirements first, compared different solutions, and chose the options that best met those needs. This project taught me that planning before coding saves time and helps avoid mistakes later. In future projects, I will continue taking time to gather requirements, create design documents, compare different approaches, and think about things like security, performance, and scalability before I start writing code.

