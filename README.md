<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/header-dark.svg">
  <img alt="Mike Bronner. Laravel and Developer Experience Engineer." src="assets/header-light.svg">
</picture>

<br>
<br>

I've been developing in PHP since 1999. During that time I have watched the same problems reappear:
the frameworks change and the tooling changes, but the challenges developers face stay roughly the
same. I have always been interested in addressing those challenges, in order to allow development to
be focused on creating solutions without being distracted by tooling and process friction.

The best tools get the job done and get out of your way. Ideally they are invisible and you don't
even realize they are there. It removes friction and then stops asking for attention, freeing up
your mental bandwidth to focus on the things that matter.

Over my entire career I have worked on tackling automated logging, CI/CD pipelines and automated
testing, automated linting, as well as IDE tooling.

<br>

## What I have come to learn

### Mental debt is the real cost of code.
This is the mental effort required to read code and
actually understand it. Naming, structure, and comment decisions are mostly decisions about reducing
mental debt, because every reader after the first pays that cost again from scratch.

### Opinions only matter once they become practices.
The resulting code standards I developed over years are written as a progression: from a single
thought on a line up through statements, concepts, methods, classes, and domains, each level
composed from the one below it. Initially these served as documentation for teams to read and
implement in their code. The constant friction surfaced during review when not all standards were
met because they were not clearly understood or simply honestly missed during development.

### A standard nobody enforces is not a standard.
If a rule depends on a person remembering it, it may hold for about a month. Plus it introduces
frustration and possible resentment during reviews. Putting it into tooling and automating it is
the next logical move in making it a low-friction standard that can be followed during development
and review.

### Only implement those tools that work.
Implementing tooling that only does half the job or fails half the time to produce correct results
is worse than no tooling. It is a constant source of frustration and prevents the developer from
accomplishing their work. Initially only a subset of the code standards were able to be implemented
in linter rules, but now with AI it is so much easier to expand on them and implement the more
complex ones as well. Now with nearly complete coverage we have a full linting suite backing up the
code standards.

### Process is engineering, not ceremony.
To make everything work seamlessly together, processes must be developed and implemented. And just
like with tools, processes can be automated so that the tedium gets out of the way, and the human
interaction is supported by a process framework, like Scrum. Scrum gets out of the way as much as
possible and is only prescriptive where not being so would be detrimental to performance. The result
of combining automated tooling and a process framework lets developers focus on what they do best,
while providing a platform for teams to continuously deliver value.

<br>

## What I ended up doing

### Automated and consistent feedback on code standards
Implementing as much of your coding standards through automated linting in both the IDE (for 
immediate feedback) and during CI (for review feedback as a safety net) removes several areas that
otherwise can provide friction. More importantly, it provides value to the company by having code
that is easier to maintain through minimized mental debt, and further creates clear expectations for
onboarding new developers.

Out of the box PHP Code Sniffer provides basic linters, but they don't address more advanced or
custom code standards. Slevomat adds quite a few good linters, but still doesn't get everything
exactly as a team might want their standards. So I built my own custom linters on top of PHPCS and
Slevomat as needed so that all code standards are represented by a linter, and even auto-fixable if
possible.

### Processes and procedures
Working in a development team comes with difficulties that don't exist for when you are working by
yourself. Employing a framework helps make the team be the best it can be by providing a commonly
understood set of processes and procedures. The Agile Manifesto provides a comprehensive set of 
common sense guidelines. One such framework built around these is Scrum. When implemented correctly,
it can support the individual developer, improve the team, and increase value for the company.

I always felt that agile development was a better solution than the traditional
waterfall-project-managed-never-is-what-the-client-wanted-when-finished projects, and when I finally 
discovered Scrum started implementing it in the teams I was part of. I studied it, lived it, and
obtained several certifications, starting with Scrum Master and Product Owner certification.

### Optimized IDE tooling
Having an IDE that supports you in your daily development wherever it can helps developers improve
their effectiveness by removing tedium, frustration, and providing contextual awareness. Having a
comprehensive language and framework integration is vital for providing insight into code, allowing
the developer to make informed decisions as they are typing. Further, it helps remove tedium and
frustration, resulting in a more enjoyable development experience overall.

I developed several extensions for Zed (my currently preferred IDE) that I now use on a daily basis
for development, which include Laravel, PHPCS, and PHPMD LSPs for tightly integrated linting,
auto-completion, and code insight.

### Agentic development
The recent emergence of LLMs and agentic development is seen by many as something that will make
developers obsolete, and by others as the silver bullet. I think the truth lies somewhere in the
middle, in that AI is a tool that developers are best suited at to implement effectively. Each of
the above is directly applicable to making agentic development successful.

I implemented this in the form of Claude plugins, a dedicated Github app that also serves as MCP,
all integrated into a Github project that allows me to easily manage all the work being done by my
agentic team.

<br>

## What ended up in projects

I would like to express a huge thank you to everyone using any of my packages! They all started out
of a personal need, and I dogfooded them to develop their functionality in all my projects.
Open-sourcing them to the community is my way of helping developers everywhere and give back to the 
community. This in turn led to feedback, bug reports, and feature requests, starting a
self-perpetuating cycle.

<br>

### Laravel packages

| Package | The problem it solves |
|---|---|
| [**laravel-pivot-events**](https://github.com/mikebronner/laravel-pivot-events) | Eloquent fires events for everything except pivot changes, so cache invalidation and audit logging silently do not run. |
| [**laravel-model-caching**](https://github.com/mike-bronner/laravel-model-caching) | The same query runs on every request, and the N+1 the ORM made easy to write stays invisible until one client has real data volume. |
| [**laravel-caffeine**](https://github.com/mikebronner/laravel-caffeine) | The user spent twenty minutes filling in your form, then the session expired and took the work with it. |
| [**laravel-socialiter**](https://github.com/mikebronner/laravel-socialiter) | Every project reimplements Socialite user persistence slightly differently, which means everybody has slightly different security bugs in it. |
| [**laravel-impersonator**](https://github.com/mikebronner/laravel-impersonator) | Support cannot reproduce what the customer is seeing, so the thread becomes a slow exchange of screenshots. |
| [**laravel-changelog**](https://github.com/mikebronner/laravel-changelog) | Nobody can tell customers what changed without asking an engineer first. |

[All packages, with documentation](https://mikebronner.dev/packages).

<br>

### Zed editor extensions

| Extension | The problem it solves |
|---|---|
| [**zed-laravel**](https://github.com/mike-bronner/zed-laravel) | Zed has no idea what a Blade component, route helper, or container binding is, so it cannot autocomplete or navigate any of them. |
| [**zed-phpcs-lsp**](https://github.com/mike-bronner/zed-phpcs-lsp) | Coding standard violations only surface in CI, long after the moment they were cheap to fix. |
| [**zed-phpmd-lsp**](https://github.com/mike-bronner/zed-phpmd-lsp) | Complexity and code-smell warnings live in a separate report nobody opens. |

<br>

### Linters

| Project | The problem it solves |
|---|---|
| [**phpcs-rules**](https://github.com/mike-bronner/phpcs-rules) | Written code standards decay because nothing enforces them, and the ones a token-based sniff genuinely cannot verify get claimed anyway. |

[The code standards these enforce](https://mikebronner.dev/clean-code), written as a progression
from a single thought on a line up through statements, concepts, methods, classes, and domains.

<br>

If you are experiencing issues with any of my projects, please do reach out by opening an issue or 
emailing me directly for security issues. I fully appreciate any feedback, as it helps improve each 
project, and I realize that many of the packages might be used in production environments, so
addressing any bugs is vitally important to me.
