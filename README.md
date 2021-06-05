# Continuous Delivery

Definition: "Delivery high quality software and with big value eficiently, quickly and trustful"

Set of process and behaviors in order to make the deployment process more often and automated. 

Focus on avoiding issues/risks of a delayed deploy one day before the deadline.

Important to make work propertly:

- Granularity;
- Frequence;
- Automazation.

Main Points:

1. Automize;
2. Version everything;
3. Repeat the process everytime possible;
4. Guarantee the quality; 
5. Define "done";
6. Create delivery team;
7. Use continuous improvements.

Elements of Continuous Delivery:

- DevOps Culture:
    - Feedback, cooperation and trustful;
    - continuous improvements and learning.
- Patterns:
    - deployment pipeline;
    - deploy pattern (blue/green, canary, feature toggle)
- Architecture:
    - New properties: testability, deployyability;
    - SOLID, Services, 12 Factor App.

## Release Antipatterns

- Manual environment management;
- Manual deploy;
- Deploy just in the end of a circle/sprint.

All this bad practices create:
 - Unreliable process, nobody trust on what gonna happen on the production environment;
 - Communication problems, out of date documentation (needed because It is manual);
 - Few colaboration and feedback among the team
 - creates a lot of risks, Unreliable.

## Release pattern

The exactly the opposite of the Antipatterns:

- Automated environmental management;
- Automated deploy
- Continuous deploy, after each change for example;

## Continuous Deployment VS Continuous Delivery

Continuous delivery (CD) is a software engineering practice in which teams develop, build, test, and release software in short cycles. It depends on automation at every stage so that cycles can be both quick and reliable.

Continuous Deployment is the process by which qualified changes in software code or architecture are deployed to production as soon as they are ready and without human intervention.

## Deployment Pipeline

This type of pipeline focus on the fail first if there is a problem. Start with the nimble tasks and then the slow and manual activities. Making a long story short: Optimization and faster builds.

Important Rules:

- Deploy just through pipeline;
- Same deploy for all the machines, same script, same rules, same steps;
- Keep the pipeline as faster as possible;
- Build just once per deploy.
- Build is independent of any client environment;
- QA/Dev/Production need to keep as similar as possible;
- Temporary environment (Recreate the environment) *if the team can and need to afford this.
    - Docker is the guy here.

Steps:

1. Commit Stage
 - Unit Tests;
 - Build;
 - Analysis.
2. AAT(Automated Acceptance Tests);
3. Homologation
 - UAT (User Acceptance Tests);
 - CTS (Capacity Testing Stage);
4. Deploy;
5. Release


### Commit Stage

Execute automated tests;
Focus on the unitary and integration tests;
Need to be fast, near to 10 minutes;

### AAT Stage

AAT Stage focuses on the tests based on some requests/acceptance points, testing the whole application, taking more time to execute.
AAT tests generally are the hardest ones to write, manage and execute, however, bring a lot of benefits for the application. They are written by the whole time.

### Homologation Stage

- UAT (User Acceptance Tests): The final user is gonna valid if the application solution respects and executes well-enough the needs and expectations. The app team needs to follow this step, opportunity to gather feedback about usability, opinions and acceptances.

- CTS (Capacity Testing Stage): Check non-functional requirements, such as, scalability, performance, security. It needs to be executed frequently.


## Deploy Stage

Put the changes in production: manage, configure and install.

## Release Stage

Allow the user to access some features/fixes.

There are some types:

- Blue-Green Deployment: There are all 2 environments, blue which is the old one, green is the new.Both keep running even when all the users are accessing the green one, because if there is any trouble in the new version, It is just necessary switch to the blue one. It needs a router to manage the access to the versions.

- Canary Release: The users increasingly change from one version to the other based in some logic. Critical point to check if there will be a problem.

- Feature Toggles: True/false logic defined by some rule that will give or not access to some feature/fix to the user.

Obs.: They can be used together.

## Cool Links

- https://continuousdelivery.com/;
- https://blog.caelum.com.br/integracao-continua-builds-rapidos-com-grids-e-paralelismo/;
- https://blog.caelum.com.br/integracao-continua-deploys-e-aprovacoes-sem-dores-de-cabeca-para-o-cliente/;
- https://blog.caelum.com.br/branches-e-integracao-continua-o-problema-de-feature-branches/;
- https://martinfowler.com/delivery.html;
- https://www.thoughtworks.com/pt/continuous-integration;
- https://www.casadocodigo.com.br/products/livro-devops;
- https://www.amazon.com.br/DevOps-Handbook-World-Class-Reliability-Organizations-ebook/dp/B01M9ASFQ3/;
- https://martinfowler.com/bliki/FrequencyReducesDifficulty.html;
- https://12factor.net/pt_br/.