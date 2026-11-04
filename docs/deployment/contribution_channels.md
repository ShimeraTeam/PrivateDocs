# Shimera Contribution Channels

This document explains why the Shimera team calls for external contributions, how those calls are made, and on which platforms. It expands on Phases 2 and 3 of the [Distribution Strategy](./diffusion_strategy.md).

## 1. Why we call for contributions

- **Open source works through its community**: Shimera is fully open source under GPL 3.0. A low-level graphics library gains value and trust through peer review and external contributions, not only through the work of its original team.
- **Limited team capacity**: the team is small and its availability drops during exam and internship periods. External contributors help keep the project moving (backends, shaders, tests, documentation).
- **Hardware and platform coverage**: a graphics library behaves differently depending on the GPU, driver, and operating system. Contributors using their own setups help find bugs and portability issues the team cannot reproduce on its own machines.
- **Feedback on the API**: developers who integrate Shimera into their own projects show us what is unclear, missing, or hard to use.
- **Credibility**: external contributors and an active community help the project be seen as a serious tool rather than a student project.

## 2. How we call for contributions

### Before posting

A call for contributions only works if newcomers can start quickly. Before posting anywhere, the repository must have:

- A clear README (overview, code examples, screenshots or GIFs of shader demos).
- A `CONTRIBUTING.md` explaining how to build, test, and submit changes.
- A `LICENSE` file (GPL 3.0).
- Open issues labeled `good first issue` and `help wanted`, so newcomers know where to begin.
- A tagged release with a changelog.

### What each post contains

- What Shimera is, in one or two sentences.
- Where the project stands today (what works, what is in progress).
- What kind of help we are looking for, with links to the matching issues.
- A visual (screenshot or GIF of a shader effect).
- A link to the GitHub repository and to `CONTRIBUTING.md`.

### Posting rules

- **Read each community's rules first**: many communities limit self-promotion or require it in a specific place (showcase channel, weekly thread, flair).
- **Adapt the message to the audience**: a graphics programming community cares about rendering and shader details, a game development community cares about integration with their engine or framework.
- **Do not spam**: post once per community, avoid posting the same message everywhere on the same day, and space out follow-up posts (for example, one per major release).
- **Stay present after posting**: answer comments and questions quickly, especially during the first days.
- **Post as the team**: posts are made from a team member's account and clearly state that they are part of the Shimera team.

### After posting

- Respond to new issues and pull requests from newcomers quickly, since a slow first reply is the main reason contributors leave.
- Track simple metrics after each post (stars, forks, new issues, new contributors) to see which channels work best.

## 3. Platforms and placements

### Reddit

| Placement | Audience | Notes |
|---|---|---|
| [r/GraphicsProgramming](https://www.reddit.com/r/GraphicsProgramming/) | Graphics and rendering programmers | Main Reddit target. Focus the post on the rendering/shader side of Shimera and include visuals. |
| [r/raylib](https://www.reddit.com/r/raylib/) | Raylib users | Focus the post on the Raylib backend and show how to add Shimera effects to a Raylib project. |
| [r/sfml](https://www.reddit.com/r/sfml/) | SFML users | Focus the post on the SFML backend and show how to add Shimera effects to an SFML project. |

### Discord

| Server | Audience | Notes |
|---|---|---|
| Epitech and Epitech Toulouse | Student Developers | Post in the channel the server dedicates to project showcases or self-promotion, following its rules. |

### GitHub

| Placement | Audience | Notes |
|---|---|---|
| Repository topics and issue labels | Developers browsing GitHub for projects to contribute to | Add topics (`opengl`, `glsl`, `raylib`, `sfml`, `cpp`, `shader-library`) and keep issues labeled `good first issue` / `help wanted`. GitHub uses them to recommend projects. |
| [goodfirstissue.dev](https://goodfirstissue.dev/) | First-time open source contributors | Projects are not listed automatically: we must request the addition of Shimera on the website, following its listing requirements. Once listed, the site shows our `good first issue` issues. |
| GitHub Discussions | Users and contributors of Shimera | Enable Discussions on the repository so contributors can ask questions and propose ideas without opening issues. |
| "Awesome" lists (e.g. awesome-opengl, awesome-cpp, awesome-raylib) | Developers looking for libraries in a given ecosystem | Open a pull request on each list to add Shimera, following each list's contribution rules. |

### Other

| Platform | Audience | Notes |
|---|---|---|
| [Bluesky](https://bsky.app/) | Game developers and graphics programmers | Post short updates with visuals (GIFs of shader effects) and relevant hashtags such as `#gamedev` and `#graphicsprogramming`. |
