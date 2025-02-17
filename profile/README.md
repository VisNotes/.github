# visnotes-docs

|     | Repo |
| -------- | ------- |
| Docs   | [Repo](https://github.com/VisNotes/.github)  |
| Web App | [Repo](https://github.com/JustinFay01/visnotes-react)     |
| API    | [Repo](https://github.com/JustinFay01/visnotes-api)  |
| Infrastructure | [Repo](https://github.com/VisNotes/visnotes-infrastructure) |

# Road Map

## Docs

- [ ] Unify Docs from each repo
- [ ] Add section on configuring VPS

## Infrastructure

 - [x] Create Repo
 - [x] Move traefik stack from API to this repo
 - [x] VPS CrowdSec for Fail2Ban replacement
 - [ ] Deploy Loki, Promtail, and Grafana stack for log viewing
 ~~- [ ] Deploy KeyCloak~~  **Abandoned, became a roadblock for progress, using free tier of auth0 instead**
 - [ ] Deploy [MiniIO](https://min.io/)
 - [ ] Create actions for stack file changes

## API

 ~~- [ ] Switch AUTH to KeyCloak~~ **Abandoned, became a roadblock for progress, using free tier of auth0 instead**
 - [ ] Implement Read Repair for blob storage
 - [ ] Remove IFormFile from the Service Layer
 - [ ] Add Users table
 - [ ] Make a unique constraint for files that use a users id and the file name to prevent repeat files (and avoid calling the DB for existence check in the API)

## Web App

 - [x] Fix Repo secrets
~~- [ ] Create a mobile friendly Notes Section~~ **Abandoned, became a roadblock for progress, using free tier of auth0 instead**
 - [ ] Add a warning when analyzing a note that has already been analyzed
 - [ ] Add a button to generate a new word cloud instead of automatically generating it
 - [ ] Add a button to download the word cloud as different file types
 - [ ] Allow users 'correct' AI analysis of notes and save it as a preference
 - [ ] Save users column widths as a preference
 - [ ] Save selected columns as a preference
 - [ ] Add a button to download the word cloud as an image
 - [ ] Add different Layout options
 - [ ] Update the Analysis view when selecting a note
 - [ ] Fix weird null condtion checks for analysis
 - [ ] Clean up how updating files int he table connects to the word cloud
 - [ ] Remove duplicate source folder
 
# Modern React

## Introduction

This repo contains a set of opinionated guides that help you to build modern React applications with Vite. It is a collection of best practices that have been cultivated by the industry and the community. It is not a boilerplate or a template, but aims to provide the information you need to build a modern React application.

It heavily focuses on integration with tools like ESLint, Prettier, TypeScript, and Vite. It also provides a set of recommended configurations for these tools.

## The Docs

- [Quick Start](../docs/react/quick-start.md)
    - Get started with a new React + Vite + TypeScript project using create-vite.
- [Best Practices](../docs/react/best-practices.md) 
    - Learn about a set of theories that can help you build better React applications.
    - Learn about the recommended tools for building React applications.
    - Each section will lead you to to a configuration guide that also includes a set of recommended implementations.
- [Project Structure](../docs/react/project-structure.md) 
    - Learn about an easily maintainable project structure for React applications.
- [Project Standards](../docs/react/project-standards.md) 
    - Learn about the recommended tools that are used across the industry for building React applications.
- [Package Managers](../docs/react/package-managers.md) 
    - Learn about the recommended package managers for building React applications.
