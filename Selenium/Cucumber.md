- Feature file- we defines test cases or scenarios here. Collection of scenarios is called feature file. Given ,when then
- Step definition file- where you have core logic and connect it to feature file
- Test Runner- trigger file to run your feature file
- AbstractTestNGCucumberTests class is used by testrunnerNG file compatible with cucumber.
- Given
- When- It is used for action items
- Difference between Background and hooks?
    - Background will be run before every scenario but will be valid in that feature only.
    - Before(hook) will be run before every scenario but will be valid in all the feature files. You can run it for specific scenarios by using tags.
    - Priority-: Before-\>background-\>Scenario-\>After
    - After- runs at the end of each scenario

@CucumberOptions(features="src/test/java/features",dryRun=true,  
glue="stepDefinitions",monochrome=true ,tags="@Smoke or @Regression",plugin= {"pretty","html:target/cucumber.html","json:target/cucumber.json"})

- Plugin- shows what kind of reporting we can generate.
- dryRun=true will check if all the scenarios have their step definitions. It is similar like compiling.