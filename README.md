# KarateTest
Karate Test Tool – Basic API Testing
Before we can check out some of the testing moves you can perform with Karate, we need to have a project set up.

The easiest way to do this is to create a new project based on the Karate Maven archetype using Maven. I’ll assume you already have Java and Maven installed. If not, check out my videos on How to Install Java and How to Install Maven.

Set Up your Karate REST Test Project
1. Start up your favorite IDE. (I’ll be using Eclipse for this example.)
2. Go to File>New>Maven Project and take the defaults on first screen.
3. Under New Maven Project, create a click on Add Archetype
4. Enter the following info:

Archetype Group Id= com.intuit.karate
ArchetypeArtifactId= karate-archetype
ArchetypeVersion=0.2.7
5. Click OK.
6. It should find the Karate-archetype. Click on Next.
7. On the next screen, enter:

GroupId=com.testtalks.karatedemo
ArtifactId=karatedemo
Existing Java CucumberJVM Maven Projects
If you have an existing CucumberJVM Maven project, all you need to do is add the following dependency in your pom.xml file:

<dependency>
    <groupId>com.intuit.karate</groupId>
    <artifactId>karate-junit4</artifactId>
    <version>0.2.7</version>
    <scope>test</scope>
</dependency>
Once you have your project set up, we can begin coding your REST test API in Java.

We’ll be using Jenkins as the test application. Jenkins comes with a nice REST API that we can easily interact with as an example to test JSON.

Create your First Rest API Test using Karate
1. Under src/test/java, create a new file called Jenkins.feature
2. Enter the following:

Feature: Demo Karate against Jenkins
Scenario: Verify that Jenkins is up and running
Given url 'http://localhost:8080/api/json?pretty=true'
When method get
Then status 200
And match response.jobs[*].name contains ['JoeProject1']
Click Run.

Your test should pass.

Karate Rest Test Tool – No Code Required!
What’s cool about Karate is that unlike most BDD frameworks (Cucumber, JBehave and SpecFlow), you don’t need to write step definitions. The reason for that is that Karate has already created all the step definitions you need in order to get started with JSON, HTTP or XML.

You don’t even need to write Java code! You can create your API test in a BDD syntax without the overhead of writing any code to implement your scenarios.

Rest API Test Tool Using CucumberJVM
Since Karate’s REST test tool is built on top of Cucumber-JVM, you can run your tests, view reports and leverage any other Cucumber functionality just as with any standard Java project.

In addition, the “Getting Started” guide for Karate recommends using jUnit — NOT TestNG — since things like dynamic tables, data-driven testing and tag groups are already built in.

Is Karate Better Than Rest-Assured?
I’m just getting started with Karate myself, but as you can see in the video I was able to navigate pretty easily with zero prior knowledge of it.  Its too early for me to really compare Karate vs Rest-Assured. I’m also a big believer in that there is not better tool its more what tool is better for your team. I know that the creator of Karate Peter has an awesome comparison of the two.  What do you think?
