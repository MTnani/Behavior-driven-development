# Behavior-driven-development (BDD)

In software engineering, behavior-driven development (BDD) is an agile software development process that encourages collaboration among developers, quality assurance testers, and customer representatives in a software project. It encourages teams to use conversation and concrete examples to formalize a shared understanding of how the application should behave. It emerged from test-driven development (TDD). Behavior-driven development combines the general techniques and principles of TDD with ideas from domain-driven design and object-oriented analysis and design to provide software development and management teams with shared tools and a shared process to collaborate on software development.

Although BDD is principally an idea about how software development should be managed by both business interests and technical insight, the practice of BDD does assume the use of specialized software tools to support the development process.[5] Although these tools are often developed specifically for use in BDD projects, they can be seen as specialized forms of the tooling that supports test-driven development. The tools serve to add automation to the ubiquitous language that is a central theme of BDD.

BDD is largely facilitated through the use of a simple domain-specific language (DSL) using natural-language constructs (e.g., English-like sentences) that can express the behaviour and the expected outcomes. Test scripts have long been a popular application of DSLs with varying degrees of sophistication. BDD is considered an effective technical practice especially when the "problem space" of the business problem to solve is complex.

## History
Behavior-driven development is an extension of test-driven development, a development process that makes use of a simple DSL. These DSLs convert structured natural language statements into executable tests. The result is a closer relationship to acceptance criteria for a given function and the tests used to validate that functionality. As such it is a natural extension of TDD testing in general.

BDD focuses on:<br>

Where to start in the process<br>
What to test and what not to test<br>
How much to test in one go<br>
What to call the tests<br>
How to understand why a test fails<br>
<br>

At its heart, BDD is about rethinking the approach to unit testing and acceptance testing in order to avoid issues that naturally arise. For example, BDD suggests that unit test names be whole sentences starting with a conditional verb ("should" in English for example) and should be written in order of business value. Acceptance tests should be written using the standard agile framework of a user story: "Being a [role/actor/stakeholder] I want a [feature/capability] yielding a [benefit]". Acceptance criteria should be written in terms of scenarios and implemented in classes: Given [initial context], when [event occurs], then [ensure some outcomes] .

Starting from this point, many people developed BDD frameworks over a period of years, finally framing it in terms of a communication and collaboration framework for developers, QA and non-technical or business participants in a software project. During the "Agile specifications, BDD and Testing eXchange" in November 2009 in London, Dan North gave the following description of BDD:

BDD is a second-generation, outside-in, pull-based, multiple-stakeholder, multiple-scale, high-automation, agile methodology. It describes a cycle of interactions with well-defined outputs, resulting in the delivery of working, tested software that matters.

During an interview with Dan North at GOTO Conference in 2013, Liz defined BDD as:

It's using examples to talk through how an application behaves... And having conversations about those examples.

## Principles of BDD
Test-driven development is a software-development methodology which essentially states that for each unit of software, a software developer must:

define a test set for the unit first;<br>
make the tests fail;<br>
then implement the unit;<br>
finally verify that the implementation of the unit makes the tests succeed.<br>
This definition is rather non-specific in that it allows tests in terms of high-level software requirements, low-level technical details or anything in between. One way of looking at BDD therefore, is that it is a continued development of TDD which makes more specific choices than TDD.

Behavior-driven development specifies that tests of any unit of software should be specified in terms of the desired behavior of the unit. Borrowing from agile software development the "desired behavior" in this case consists of the requirements set by the business — that is, the desired behavior that has business value for whatever entity commissioned the software unit under construction. Within BDD practice, this is referred to as BDD being an "outside-in" activity.

#### Behavioral specifications
Following this fundamental choice, a second choice made by BDD relates to how the desired behavior should be specified. In this area BDD chooses to use a semi-formal format for behavioral specification which is borrowed from user story specifications from the field of object-oriented analysis and design. The scenario aspect of this format may be regarded as an application of Hoare logic to behavioral specification of software units using the domain-specific language of the situation.

BDD specifies that business analysts and developers should collaborate in this area and should specify behavior in terms of user stories, which are each explicitly written down in a dedicated document. Each user story should, in some way, follow the following structure: 

#### Title 
An explicit title.<br>

#### Narrative
A short introductory section with the following structure:<br>

As a: the person or role who will benefit from the feature;<br>
I want: the feature;<br>
so that: the benefit or value of the feature.<br>

#### Acceptance criteria
A description of each specific scenario of the narrative with the following structure:<br>

Given: the initial context at the beginning of the scenario, in one or more clauses;<br>
When: the event that triggers the scenario;<br>
Then: the expected outcome, in one or more clauses.<br>

BDD does not have any formal requirements for exactly how these user stories must be written down, but it does insist that each team using BDD come up with a simple, standardized format for writing down the user stories which includes the elements listed above.

#### myFirstTest.feature
Feature:<br>
In order to keep my product stable<br>
As a developer or product manager<br>
I want to make sure that everything works as expected

Scenario: Check title of website after search<br>
Given I open the url "http://google.com"<br>
When I set "WebdriverIO" to the inputfield "#lst-ib"<br>
And I press "Enter"<br>
Then I expect that the title is "WebdriverIO - Google Search"<br>

Scenario: Another test
    Given ...
