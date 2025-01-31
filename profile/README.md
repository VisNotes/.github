<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->


# visnotes-docs

|     | Repo |
| -------- | ------- |
| Docs  |  [Repo](https://github.com/VisNotes/visnotes-docs)  |
| Web App | [Repo](https://github.com/JustinFay01/visnotes-react)     |
| API    | [Repo](https://github.com/JustinFay01/visnotes-api)  |
| Infrastructure | [Repo]() |

# Road Map

## Docs

- [ ] Unify Docs from each repo
- [ ] Add section on configuring VPS

## Infrastructure

 - [ ] Create Repo
 - [ ] Move traefik stack from API to this repo
 - [ ] Deploy Loki, Promtail, and Grafana stack for log viewing
 - [ ] Deploy KeyCloak
 - [ ] Deploy [MiniIO](https://min.io/)
 - [ ] Create actions for stack file changes

## API

 - [ ] Switch AUTH to KeyCloak
 - [ ] Implement Read Repair for blob storage
 - [ ] Remove IFormFile from the Service Layer

## Web App

 - [ ] Fix Repo secrets
 - [ ] Switch Auth to KeyCloak
 - [ ] Create a mobile friendly Notes Section
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


