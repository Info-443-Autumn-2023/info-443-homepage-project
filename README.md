# INFO 443 AU 23 Project 2

#### Group Members
- Minh Mai
- Chun Hin Matthew So 
- Joseph Tran 
- Jerry Yan

**Forked Repo:** [Link](https://github.com/jknt27/homepage)

**Documentation:** [Link](https://gethomepage.dev/)

## About the Project/Context and Background

### Project Name: *HomePage*

**Authors:** shamoon and over 200 independent contributors

**Type:** React Application

### Description:

*HomePage* is a robust React Application that functions as a versatile and user-friendly dashboard. Designed to be modern, fast, and secure, it offers a centralized platform for users to customize and access a wide array of features. These features include quick search capabilities, bookmark management, and real-time weather updates. The project was initially created by shamoon, with continuous contributions from a diverse community of over 200 independent contributors, making it the feature-rich and dynamic application it is today. Whether users are looking to streamline daily tasks, stay informed about the weather, or simply organize online activities, HomePage offers a seamless and personalized experience for users of all backgrounds and interests.

## Development View

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

A UML component diagram for HomePage Application


[Figure 1: UML Component Diagram](https://miro.com/app/board/uXjVNNIpxuk=/?share_link_id=448532148778)

<img src="/Images/UMLCompoentDiagramDraft1.png" alt="UML Component Diagram">



### System Dependencies

### High-Level Codeline Model

### Testing and Configuration

was not able to find the testing file from the source repository to analyze how the organization conduct testing.


## Applied Perspective

### Introduction to Perspective

### Concerns with this Perspective

### Perspective Activities

## Identify Styles & Patterns Used

### Architectural Style

### Software Design Patterns

## Architectural Assessment

### Design Principles

#### Single Responsibility Principle

The Single Responsibility Principle suggests that one element should only have one responsibility or purpose in the program. 

As in the HomePage application, it effectively follows this principle. For example, in the bookmarks component, it systematically breaks down tasks into items, lists, and groups.This ensures that each sub-task, from retrieving an item from a bookmark parameter to placing it in a list and then consolidating all the lists into one group,is handled by a distinct responsibility. Similarly, the toggle component follows suit by separating the toggle functionality into distinct responsibilities for theme/color changes, design choices, and user input verification.

As a result, this principle improves HomePage application of its scalability and maintainability because of better design of code architecture to simplify the complexity.



## System Improvement
