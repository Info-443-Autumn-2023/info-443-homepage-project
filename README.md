# INFO 443 AU 23 Project 2

#### Group Members
- Minh Mai
- Chun Hin Matthew So 
- Joseph Tran 
- Jerry Yan

**Forked Repo:** [Link](https://github.com/jknt27/homepage)

**Documentation:** [Link](https://gethomepage.dev/)

## I. About the Project/Context and Background

### Project Name: *HomePage*

**Authors:** shamoon and over 200 independent contributors

**Type:** React Application

### Description:

*HomePage* is a robust React Application that functions as a versatile and user-friendly dashboard. Designed to be modern, fast, and secure, it offers a centralized platform for users to customize and access a wide array of features. These features include quick search capabilities, bookmark management, and real-time weather updates. The project was initially created by shamoon, with continuous contributions from a diverse community of over 200 independent contributors, making it the feature-rich and dynamic application it is today. Whether users are looking to streamline daily tasks, stay informed about the weather, or simply organize online activities, HomePage offers a seamless and personalized experience for users of all backgrounds and interests.

## II. Development View

### System Components

The following table below provides an overview of the primary components necessary for our application. Every component is in charge of a certain task and these all come together to create a functional system. These components are described in the table below by what they do and which dependencies it uses.

| Component | Purpose | Dependencies |
| :-------: | ------- | ------------ |
| Pages | Renders the primary "HomePage" UI and displays user's desired contents. | Bookmarks, Services, Toggles, Widgets|
| Bookmarks | Allows users to set frequently used applications and links for quick access. They may view items as groups or as a list. | Items |
| Items | An individual piece of data or statistical information that is accessible by the user. | None |
| Services | Allows user to monitor various services of their choice. This could vary from monitoring their desired server's statistics or checking the staus of their docker containers. | SiteMonitor, Widget |
| SiteMonitor | Acts similar to a `ping` command and checks the status of a server or site. | None |
| Toggles | These are similar to buttons that take the input of the user. This component changes the UI of the application based on the interaction with the user. There is a toggle for theme color, light and dark mode, and to reload the page. | None |
| Widgets | Displays information regarding current status of a desired system or basic information (such as time) | None|


*Table 1: Component Table with their purposes and dependecies.*

### UML Component Diagram

In the constructed UML component diagram for the HomePage React Application below, a hierarchical decomposition of system components is presented, epitomizing a modular architecture and encapsulation. The apex of this hierarchy is the HomePage application itself, which delineates into two principal components: the 'Library' and the 'Pages Component'.

The 'Library' serves as a foundational tier, encapsulating the React Library alongside the 'classnames' utility, indicating a reliance on React's component-driven architecture and dynamic styling capabilities for UI construction and manipulation.

Within the 'Pages Component', a composite structure unfolds, comprising 'Bookmarks', 'Items', 'Services', 'Site Monitor', 'Widgets', and 'Toggles' components. This layered approach manifests a clear dependency management strategy, where 'Bookmarks' requisition 'Items' for data representation, and 'Services' necessitate 'Site Monitor' and 'Widgets' for functionality. This delineation underscores an architecture where high-level components are abstracted from low-level operations, fostering an environment conducive to independent component development and testing, as well as scalability through facile integration of additional features. The diagram thus reflects a contemporary approach to React development, privileging component reusability and compositionality.

![UML Component Diagram for HomePage Application](./Images/UMLComponentDiagramDraft1.png)
*Figure 1: UML Component Diagram illustrating the modular structure and inter-component relationships within the HomePage React Application.*

### System Dependencies



### High-Level Codeline Model

[Link to the Diagram](https://miro.com/app/board/uXjVNEo28zk=/?share_link_id=220470306222)

The `component` folder defined by the `src` folder is the main repository that contains the most important code for the HomePage Application. Inside the `component` folder, it is divided into four main components: bookmark item, service, widget, and toggle, which all of them act an essential role in ensuring the proper execution of the HomePage application. 

### Testing and Configuration

This repository contains no forms of testing, whether automated or unit tests. As a result, we couldn't test their code unless we wrote our own.

## III. Applied Perspective

### Introduction to Perspective

Usability as an architectural perspective emphasizes designing systems that are efficient, effective, and satisfying for the end user. It focuses on how user interactions with the system are designed and how easily users can accomplish their desired tasks. In a usability-focused architecture, the primary goal is to create a system that is intuitive, easy to navigate, and accessible to a diverse range of users. This perspective is crucial in ensuring that the system is not only functional but also user-friendly and engaging.

### Concerns with this Perspective

When adopting a usability perspective, several key concerns must be addressed:

User Experience Design: Ensuring the system is intuitive, easy to learn, and pleasant to use. It involves understanding the users' needs, behaviors, and frustrations.

Accessibility: Making the system usable for people with a wide range of abilities. This includes considering users with disabilities and ensuring compliance with accessibility standards.

User Interface Design: Focusing on the aesthetics and layout of the system. The interface should be clear, responsive, and visually appealing.

Feedback and Error Handling: Providing clear, helpful feedback to users, especially in error situations. The system should guide users in correcting mistakes and understanding how to use it effectively.

Performance and Efficiency: Ensuring the system responds quickly to user input and operates smoothly, enhancing the overall user experience.

### Perspective Activities

In applying a usability perspective, the process begins with understanding the users. This means finding out what they need and prefer through surveys and studies. The information gathered is then used to create several versions of the design, which are improved over time. This improvement comes from testing the system with real users, where feedback is collected to identify what works well and what doesn’t.

At the same time, it's important to make sure the system is easy for everyone to use, including people with disabilities. This is done through accessibility checks. The system’s speed and responsiveness are also continuously checked and improved to make sure it works smoothly and quickly.

Finally, user feedback is an ongoing part of the process. It helps to tweak and enhance the system regularly. To help users get the most out of the system, clear instructions and training materials are provided. All these steps together make sure the system is not just functional but also easy and enjoyable to use.

## IV. Identify Styles & Patterns Used

### Architectural Style

All the components and modules are grouped together and layered by similar functionality. HomePage uses a Model-View-Controller (MVC) architectural style for their implementation. We can see this within the implemenation of the pages components. The model, `index.jsx`, is responsible for managing all the relevant data needed to run HomePage. `_app.jsx` is the View Layer as it is responsible for rendering all of the UI within the HomePage. The controller is made up of many `API` components which are responsible for managing user requests and updating the state of every item used.

### Software Design Patterns

[4 or more OOP patterns]

Observer Pattern - Observer design pattern is a behavioral design pattern that defines one-to-many relationships between dependency and object so that all dependents are updated when one object changes its state. In the HomePage applications, the item component in `src/components/services/item.jsx`, which are responsible for showing the item on the Homepage can be beneficial by using observer design pattern. The problem can be that multiple parts of the application need to be updated if there is a change in the information provided by the Items. Observer pattern could be seen in the code where `statsOpen`, `statsClosing`, and `SiteMonitor` as the observer to notify of any changes in the item state.

Strategy Pattern - The Strategy Design pattern is a design pattern that encapsulates similar algorithms to enable the component to be interchangeable. In the HomePage application, the toggle (`src/components/toggles`) handles user interactions that influence the user interface, such as toggling between light and dark mode, changing theme colors, and reloading the page. The problem is that different users might have different preferences for how they want the homepage to look. The Strategy pattern could be used to address this problem. Instead of hardcoding the user interface behavior within the `toggles` component, the application can define a family of monitoring algorithms (strategies) encapsulated in separate classes. Each strategy class implements a specific way to change the user interface.

Decorator pattern - Decorator pattern is a structural design pattern that provides flexibility for subclass to expand functionality by adding additional functions to an object. In the HomePage application, the group from the bookmarks component can be beneficial from the Decorator pattern. The purpose of this usage is to extend the functionality of the bookmark component without modifying its core code, which is item code. Inside the group, conditional rendering (layout?.header !== false) can also be considered as decorators to allow for the dynamic application of CSS classes based on certain conditions. Besides, the `beforeLeave` and `beforeEnter` functions inside the transition component can also act as decorators to customize the transition behavior, providing additional animation effects.

Composite pattern -  Composite pattern is a structural design pattern that treats individual objects the same as compositions of objects. In the HomePage application the weather from the widget component can be beneficial from the composite design pattern. The purpose of this pattern is to let the client use the same interface components to expand scalability and maintainability. Inside the `weather.jsx`, the weather api function acts as a composite to contains composites such as ContainerButton and widget to be treated the same by the client through sharing a common interface


## V. Architectural Assessment

### Design Principles

In the realm of software architecture, adhering to key design principles is crucial for creating a robust, scalable, and maintainable system. This section evaluates how the HomePage application aligns with four fundamental principles: the Single Responsibility Principle, Open/Closed Principle, Liskov Substitution Principle, and Principle of Least Privilege.

#### Single Responsibility Principle

The Single Responsibility Principle dictates that a component should have one, and only one, reason to change, signifying that it should have only one job. In the HomePage application, this principle is effectively implemented. The bookmarks component, for instance, systematically segregates tasks into items, lists, and groups, ensuring distinct responsibilities for each sub-task. This approach enhances the scalability and maintainability of the HomePage application by simplifying the complexity of the code architecture.

#### Open/Closed Principle (OCP)

The Open/Closed Principle states that software entities should be open for extension but closed for modification. This principle is embodied in the HomePage application through its modular design, which allows for the integration of new services or features without altering the existing codebase. The application's ability to add new APIs or services through configuration files or Docker labels, without needing to modify the core application logic, is a testament to its adherence to the OCP, resulting in a more robust and adaptable architecture.

#### Liskov Substitution Principle (LSP)

The Liskov Substitution Principle mandates that objects of a superclass should be replaceable with objects of its subclasses without affecting the functionality of the application. HomePage's architecture demonstrates this principle through its effective use of polymorphism and inheritance. The application ensures that components and their derived classes are interchangeable, like seamlessly substituting a basic widget with an advanced one that offers additional features but shares the same interface. This approach not only ensures the integrity of the application's functionality but also enhances its flexibility and extensibility.

#### Principle of Least Privilege (PoLP)

The Principle of Least Privilege advocates for minimal user profile privileges based on job necessities. In HomePage, this is reflected in the security design where all API requests to backend services are proxied, keeping API keys hidden and ensuring minimal exposure. This principle is critical for enhancing the application's security, as it restricts access rights for users to the bare minimum necessary to perform their tasks, thereby reducing the attack surface and potential damage from accidents or malicious actions

## VI. System Improvement

The `Site monitor`, `site-monitor.jsx`, from the `service` component is responsible for tracking the availability of the URL and displaying the delayed response time, which is integral for the proper execution of the Home Page application. However, there is some refactoring improvement to be made to improve its clarity, maintainability,and collaboration between programmers. Inside the `Site monitor` code -  `site-monitor.jsx`, the `t` in line 5 from `const { t } = useTranslation();` should be renamed as translation for better clarity. Also, the use of '403' from `if (data.status > 403)` may appear as a magic number to non-website programmer. Therefore, it should do a constant value of `const FORBIDDEN_STATUS_CODE = 403;`. Other than that, the site monitor should consolidate conditional expression and Replace Nested Conditional with Guard Clauses as defined by Martin. Inside the site monitor, there are too many if statements from line 15 to line 52, thus increasing the complexity for other programmers to understand and maintain the quality of code. Those if statements can be consolidated into a function and break down into several if statements according to the Replace Nested Conditional with Guard Clauses to return the value back to the export function to uphold the maintainability and readability.  