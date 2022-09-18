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

## MVP Features

* Sign into Nexus via Keycloak SSO
* Sign out of Nexus
* Navigation Bar dropdowns to access static pages
* Access to features such as redirecting a class, etc

### Technical Caveats

At the basic level, we will need the following to develop our MVP features

* Front-End server secured with SSL
* Fully authenticated back-end server (using professional authentication techniques)
* Database (MongoDB) to store internal data, Redux for caching purposes

## Features to Import

* Checking that all of our servers are currently operational
* Redirecting classes - both viewing and adding new redirects
* Blocking IP Addresses - viewing and blocking new ip addresses
* Viewing all Zoom URLS (the Keycloak User Directory)
* Viewing the past 300 students who entered into what class
* The Error Handbook (static page)
* How to Log Into Keycloak (static page)
* Accessing the KT Admin Portal (requires a static link with Nipa's Application)
* ...and more!

## Planned Features

* Internal Forum - where employees can make posts and and establish topics
* Internal Communication Platform
* Staff Calendar
* Tech Support Tickets - submit a formal tech support request where we can reach out and help solve your problems
* Monthly Newsletter Post
* Resetting KeyCloak