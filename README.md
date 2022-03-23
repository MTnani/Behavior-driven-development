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
<code>I</code> want to make sure that everything works as expected

<code>Scenario1</code>: Check title of website after search<br>
<code>Given</code>I open the url "http://google.com"<br>
<code>When</code>  I set "WebdriverIO" to the inputfield "#lst-ib"<br>
<code>And</code> I press "Enter"<br>
<code>Then</code>  I expect that the title is "WebdriverIO - Google Search"<br>

<code>Scenario2</code>: Another test<br>
<code>Given</code>  ...

#### Feature: Sample Snippets test
    As a developer
    I should be able to use given text snippets

    #@Isolate
    Scenario: open URL
        Given the page url is not "http://guinea-pig.webdriver.io/"
        And   I open the url "http://guinea-pig.webdriver.io/"
        Then  I expect that the url is "http://guinea-pig.webdriver.io/"
        And   I expect that the url is not "http://google.com"

    Scenario: open sub page of weburl
        Given the page url is not "http://guinea-pig.webdriver.io/two.html"
        And   I open the url "http://guinea-pig.webdriver.io/"
        Then  I expect that the url is "http://guinea-pig.webdriver.io/"
        And   I expect that the url is not "http://google.com"

    Scenario: click on link
        Given the title is not "two"
        And   I open the url "http://guinea-pig.webdriver.io/"
        When  I click on the link "two"
        Then  I expect that the title is "two"

    Scenario: click on button
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the element ".btn1_clicked" is not displayed
        When  I click on the button ".btn1"
        Then  I expect that element ".btn1_clicked" is displayed

    Scenario: double click on a button
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the element ".btn1_dblclicked" is not displayed
        When  I doubleclick on the element ".btn1"
        Then  I expect that element ".btn1_dblclicked" is displayed

    Scenario: click on element
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the element ".btn1_clicked" is not displayed
        When  I click on the element ".btn1"
        Then  I expect that element ".btn1_clicked" is displayed

    Scenario: add value to an input element
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the element "//html/body/section/form/input[1]" not contains the text "abc"
        When  I add "bc" to the inputfield "//html/body/section/form/input[1]"
        Then  I expect that element "//html/body/section/form/input[1]" contains the text "abc"

    Scenario: set value to an input element
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the element "//html/body/section/form/input[1]" not contains the text "bc"
        When  I set "bc" to the inputfield "//html/body/section/form/input[1]"
        Then  I expect that element "//html/body/section/form/input[1]" contains the text "bc"

    Scenario: clear value of input element
        Given I open the url "http://guinea-pig.webdriver.io/"
        When  I set "test" to the inputfield "//html/body/section/form/input[1]"
        And   I clear the inputfield "//html/body/section/form/input[1]"
        Then  I expect that element "//html/body/section/form/input[1]" not contains any text

    Scenario: drag n drop
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the element ".searchinput" not contains the text "Dropped!"
        When  I drag element "#overlay" to element ".red"
        Then  I expect that element ".searchinput" contains the text "Dropped!"

    Scenario: wait for element
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   there is no element ".lateElem" on the page
        Then  I wait on element ".lateElem" for 5000ms to be displayed

    Scenario: wait for element using default wait time
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   there is no element ".lateElem" on the page
        Then  I wait on element ".lateElem" to be displayed

    Scenario: pause
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   there is no element ".lateElem" on the page
        When  I pause for 3000ms
        Then  I expect that element ".lateElem" is displayed

    Scenario: query title
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the title is "WebdriverJS Testpage"
        And   the title is not "Other title"
        Then  I expect that the title is "WebdriverJS Testpage"
        And   I expect that the title is not "Other title"

    Scenario: check visibility
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the element ".btn1" is displayed
        And   the element ".btn1_clicked" is not displayed
        Then  I expect that element ".btn1" is displayed
        And   I expect that element ".btn1_clicked" is not displayed

    Scenario: compare texts
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the element "#secondPageLink" contains the same text as element "#secondPageLink"
        And   the element "#secondPageLink" contains not the same text as element "#githubRepo"
        Then  I expect that element "#secondPageLink" contains the same text as element "#secondPageLink"
        And   I expect that element "#secondPageLink" not contains the same text as element "#githubRepo"

    Scenario: check text content
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the element "#secondPageLink" contains the text "two"
        And   the element "#secondPageLink" not contains the text "andere linktext"
        Then  I expect that element "#secondPageLink" contains the text "two"
        And   I expect that element "#secondPageLink" not contains the text "anderer linktext"

    Scenario: check input content
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the element "//html/body/section/form/input[1]" contains the text "a"
        And   the element "//html/body/section/form/input[1]" not contains the text "aa"
        Then  I expect that element "//html/body/section/form/input[1]" contains the text "a"
        And   I expect that element "//html/body/section/form/input[1]" not contains the text "aa"

    Scenario: check attribute
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the attribute "data-foundby" from element "#newWindow" is "partial link text"
        And   the attribute "data-foundby" from element "#newWindow" is not "something else"
        Then  I expect that the attribute "data-foundby" from element "#newWindow" is "partial link text"
        And   I expect that the attribute "data-foundby" from element "#newWindow" is not "something else"

    Scenario: check css attribute
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the css attribute "background-color" from element ".red" is "rgba(255,0,0,1)"
        And   the css attribute "background-color" from element ".red" is not "rgba(0,255,0,1)"
        Then  I expect that the css attribute "background-color" from element ".red" is "rgba(255,0,0,1)"
        And   I expect that the css attribute "background-color" from element ".red" is not "rgba(0,255,0,1)"

    Scenario: check width and height
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the element ".red" is 102px broad
        And   the element ".red" is 102px tall
        And   the element ".red" is not 103px broad
        And   the element ".red" is not 103px tall
        Then  I expect that element ".red" is 102px broad
        And   I expect that element ".red" is 102px tall
        And   I expect that element ".red" is not 103px broad
        And   I expect that element ".red" is not 103px tall

    # For some reason this test is failing when running it in the Travis VM
    @Pending
    Scenario: check offset
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the element ".red" is positioned at 15px on the x axis
        And   the element ".red" is positioned at 242px on the y axis
        And   the element ".red" is not positioned at 16px on the x axis
        And   the element ".red" is not positioned at 243px on the y axis
        Then  I expect that element ".red" is positioned at 15px on the x axis
        And   I expect that element ".red" is positioned at 242px on the y axis
        And   I expect that element ".red" is not positioned at 16px on the x axis
        And   I expect that element ".red" is not positioned at 243px on the y axis

    Scenario: check selected
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the checkbox ".checkbox_notselected" is not checked
        When  I click on the element ".checkbox_notselected"
        Then  I expect that checkbox ".checkbox_notselected" is checked

    # This will fail in PhantoJS due to a security warning
    @Pending
    Scenario: set / read cookie
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the cookie "test" does not exist
        When  I set a cookie "test" with the content "test123"
        Then  I expect that cookie "test" exists
        And   I expect that cookie "test" contains "test123"
        And   I expect that cookie "test" not contains "test1234"

    # This will fail in PhantoJS due to a security warning
    @Pending
    Scenario: delete cookie
        Given I open the url "http://guinea-pig.webdriver.io/"
        And   the cookie "test" does exist
        When  I delete the cookie "test"
        Then  I expect that cookie "test" not exists
        
  #### List of predefined steps


#### Given steps
I open the (url|site) "([^"]*)?"<br>
Open a site in the current browser window/tab<br>

the element "([^"]*)?" is( not)* displayed<br>
Check the (in)visibility of an element<br>

the element "([^"]*)?" is( not)* enabled<br>
Check if an element is (not) enabled<br>

the element "([^"]*)?" is( not)* selected<br>
Check if an element is (not) selected<br>

the checkbox "([^"]*)?" is( not)* checked<br>
Check if a checkbox is (not) checked<br>

there is (an|no) element "([^"]*)?" on the page<br>
Check if an element (does not) exist<br>

the title is( not)* "([^"]*)?"<br>
Check the title of the current browser window/tab<br>

the element "([^"]*)?" contains( not)* the same text as element "([^"]*)?"<br>
Compare the text of two elements<br>

the (button|element) "([^"]*)?"( not)* contains the text "([^"]*)?"<br>
Check if an element contains the given text<br>

the (button|element) "([^"]*)?"( not)* contains any text<br>
Check if an element does not contain any text<br>

the (button|element) "([^"]*)?" is( not)* empty<br>
Check if an element is empty<br>

the page url is( not)* "([^"]*)?"<br>
Check the url of the current browser window/tab<br>

the( css)* attribute "([^"]*)?" from element "([^"]*)?" is( not)* "([^"]*)?"<br>
Check the value of an element's (css) attribute<br>

the cookie "([^"]*)?" contains( not)* the value "([^"]*)?"<br>
Check the value of a cookie<br>

the cookie "([^"]*)?" does( not)* exist<br>
Check the existence of a cookie<br>

the element "([^"]*)?" is( not)* ([\d]+)px (broad|tall)<br>
Check the width/height of an element<br>

the element "([^"]*)?" is( not)* positioned at ([\d]+)px on the (x|y) axis<br>
Check the position of an element<br>

I have a screen that is ([\d]+) by ([\d]+) pixels<br>
Set the browser size to a given size<br>

I have closed all but the first (window|tab)<br>
Close all but the first browser window/tab<br>

a (alertbox|confirmbox|prompt) is( not)* opened<br>
Check if a modal is opened<br>

#### Then steps
I expect that the title is( not)* "([^"]*)?"<br>
Check the title of the current browser window/tab<br>

I expect that element "([^"]*)?" does( not)* appear exactly "([^"]*)?" times<br>
Checks that the element is on the page a specific number of times<br>

I expect that element "([^"]*)?" is( not)* visible<br>
Check if a certain element is visible<br>

I expect that element "([^"]*)?" becomes( not)* visible<br>
Check if a certain element becomes visible<br>

I expect that element "([^"]*)?" is( not)* within the viewport<br>
Check if a certain element is within the current viewport<br>

I expect that element "([^"]*)?" does( not)* exist<br>
Check if a certain element exists<br>

I expect that element "([^"]*)?"( not)* contains the same text as element "([^"]*)?"<br>
Compare the text of two elements<br>

I expect that (button|element) "([^"]*)?"( not)* contains the text "([^"]*)?"<br>
Check if an element or input field contains the given text<br>

I expect that (button|element) "([^"]*)?"( not)* contains any text<br>
Check if an element or input field contains any text<br>

I expect that (button|elementelement) "([^"]*)?" is( not)* empty<br>
Check if an element or input field is empty<br>

I expect that the url is( not)* "([^"]*)?"<br>
Check if the the URL of the current browser window/tab is a certain string<br>

I expect that the path is( not)* "([^"]*)?"<br>
Check if the path of the URL of the current browser window/tab is a certain string<br>

I expect the url to( not)* contain "([^"]*)?"<br>
Check if the URL of the current browser window/tab contains a certain string<br>

I expect that the( css)* attribute "([^"]*)?" from element "([^"]*)?" is( not)* "([^"]*)?"<br>
Check the value of an element's (css) attribute<br>

I expect that checkbox "([^"]*)?" is( not)* checked<br>
Check if a check-box is (not) checked<br>

I expect that element "([^"]*)?" is( not)* selected<br>
Check if an element is (not) selected<br>

I expect that element "([^"]*)?" is( not)* enabled<br>
Check if an element is (not) enabled<br>

I expect that cookie "([^"]*)?"( not)* contains "([^"]*)?"<br>
Check if a cookie with a certain name contains a certain value<br>

I expect that cookie "([^"]*)?"( not)* exists
Check if a cookie with a certain name exist<br>

I expect that element "([^"]*)?" is( not)* ([\d]+)px (broad|tall)<br>
Check the width/height of an element<br>

I expect that element "([^"]*)?" is( not)* positioned at ([\d]+)px on the (x|y) axis<br>
Check the position of an element<br>

I expect that element "([^"]*)?" (has|does not have) the class "([^"]*)?"<br>
Check if an element has a certain class<br>

I expect a new (window|tab) has( not)* been opened<br>
Check if a new window/tab has been opened<br>

I expect the url "([^"]*)?" is opened in a new (tab|window)<br>
Check if a URL is opened in a new browser window/tab<br>

I expect that element "([^"]*)?" is( not)* focused<br>
Check if an element has the focus<br>

I wait on element "([^"]*)?"( for (\d+)ms)*( to( not)* (be checked|be enabled|be selected|be visible|contain a text|contain a value|exist))*<br>
Wait for an element to be checked, enabled, selected, visible, contain a certain value or text or to exist<br>

I expect that a (alertbox|confirmbox|prompt) is( not)* opened<br>
Check if a modal is opened<br>

I expect that a (alertbox|confirmbox|prompt)( not)* contains the text "$text"<br>
Check the text of a modal<br>

#### When steps
I (click|doubleclick) on the (link|button|element) "([^"]*)?"<br>
(Double)click a link, button or element<br>

I (add|set) "([^"]*)?" to the inputfield "([^"]*)?"<br>
Add or set the content of an input field<br>

I clear the inputfield "([^"]*)?"<br>
Clear an input field<br>

I drag element "([^"]*)?" to element "([^"]*)?"<br>
Drag an element to another element<br>

I submit the form "([^"]*)?"<br>
Submit a form<br>

I pause for (\d+)ms<br>
Pause for a certain number of milliseconds<br>

I set a cookie "([^"]*)?" with the content "([^"]*)?"<br>
Set the content of a cookie with the given name to the given string<br>

I delete the cookie "([^"]*)?"<br>
Delete the cookie with the given name<br>

I press "([^"]*)?"<br>
Press a given key. You’ll find all supported characters here. To do that, the value has to correspond to a key from the table.<br>

I (accept|dismiss) the (alertbox|confirmbox|prompt)<br>
Accept or dismiss a modal window<br>I enter "([^"]*)?" into the prompt<br>

I enter "([^"]*)?" into the promptEnter a given text into a modal prompt<br>
Enter a given text into a modal prompt<br>

I scroll to element "([^"]*)?"<br>
Scroll to a given element<br>

I close the last opened (window|tab)<br>
Close the last opened browser window/tab<br>

I focus the last opened (window|tab)<br>
Focus the last opened browser window/tab<br>

I log in to site with username "([^"]*)?" and password "([^"]*)?"<br>
Login to a site with the given username and password<br>

I select the (\d+)(st|nd|rd|th) option for element "([^"]*)?"<br>
Select an option based on it's index<br>

I select the option with the (name|value|text) "([^"]*)?" for element "([^"]*)?"<br>
Select an option based on its name, value or visible text<br>

I move to element "([^"]*)?"( with an offset of (\d+),(\d+))<br>
Move the mouse by an (optional) offset of the specified element<br>
