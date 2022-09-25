# Nexus

## Description  

A company website where staff and developers can manage classes (such as class creation, class deletion, redirects, etc) in an intuitive format.

## Background

Khan's Tutorial has a lot of systems and features that are kind of scattered through out the web. This is true for both developers as well as staff members, who constantly need to use a ton of different websites to ensure that operations are handled properly. To combat this issue, we will attempt to create nexus.ktlearning.com, or a company website, which should serve as the hub for all things  Khan's Tutorial, where both managers and developers can administer the technical portions of Khan's Tutorial.

## Overview

Nexus aims to be the one-stop company website for KT (hence the name) that should allow users access to other platforms as well as managing classes. This means that you should be able to sign into Nexus, redirect a class, view the current status of our servers and then hop onto the Admin portal within the same session.

Nexus ultimately serves two main groups of people - KT Staff and KT Developers. Staff features are those features that have been developed solely for use by managers, including feature such as redirecting classes, blocking IP addresses, etc. The features that the Developers should have access to should encompass the packages built within the automation repo, such as automatically creating and destroying classes. That is to say, we should now be able to create a class with the click of a button, without needing to run ode on the terminal.  

Nexus serves as the hub of Khans Tutorial and it should also have functionality that reflects that as well. Both groups should have features like the Internal Staff Forum, Support Tickets, etc.

## Pitch

* Nexus - an internal company website where KT Staff and Developers are able to administer internal operations
  * Beholden to other stakeholders (with no communication)
  * Cloud of features that have no path to each other
  * Environment limitations
  * Security Concerns (especially updating and storing sensitive)

## Employee Journey

When joining Nexus, there should be a single unified login button/page, which will prompt a user to sign in. When the user clicks Sign In, they should be signed in using Keycloak (if they are already signed into Keycloak than they enter Nexus, else bring them to the Keycloak login page using an authentication flow).

When someone is signed into Nexus, they should see "Hello {user_name}" as well as the current status of our servers. On the left, there should be a navigation bar populated with the different features for the user type (Manager as opposed to a Developer).

By clicking a section on the side navigation bar, a dropdown of the different features for that section should appear. Click on a feature will bring to the page where you can execute the feature (blocking an IP Address).

Some sample sections could be Student Administration, where you are able to block users, view blocked users, access the KT Admin Portal, etc.

## Roadmap

### MVP Features -Anticipated Release Date: 01/01/2023

* Sign into Nexus via Keycloak SSO
  * ODIC Protocol
* Sign out of Nexus
  * IdP Logout
* Navigation Bar dropdowns to access the following static pages
  * Due Date: October 31st, 2022
  * **Section 2 (Guides and Tutorials**
    * Instructor Resources
    * Making Sales
    * Importing Students
    * Viewing Classrooms/Live Dasboard
    * Error Handbook
  * **Section 4 - Meeting Rooms**
    * Meeting Rooms
    * Management
    * Sales
    * Enrollments
    * Monthly Staff Meetings
    * Curriculum
    * Data
    * Marketing
* Access to the following features (currently active on SquareSpace, will need to be imported to Nexus)
  * Due Date: December 15th, 2022
  * **Section 3 - Classroom Administration**
    * Redirecting Classrooms
    * Communication
    * Live Dashboard
    * Class Directory
    * KT Learning Access Logs
    * Block IP Address
    * Server Status
    * Scheduled Maintenance

**Technical Caveats**

At the basic level, we will need the following to develop our MVP features

* Front-End server secured with SSL
* Fully authenticated back-end server (using professional authentication techniques)
* Database (MongoDB) to store internal data, Redux for caching purposes

### Future Features

* Internal Forum - where employees can make posts and and establish topics
* Internal Communication Platform
* Staff Calendar
* Tech Support Tickets - submit a formal tech support request where we can reach out and help solve your problems
* Monthly Newsletter Post
* Resetting KeyCloak
