All gherkins world has been translated.

For instance in french : 

* Scenario - Scénario

* Scenario Outline - Plan du scénario or Plan du Scénario

* Then - Alors

* When - Quand

* AND - Et que

* BUT - Mais que

and so on...


***
You can find all translation of Gherkin here: https://github.com/cucumber/gherkin3/blob/master/gherkin-languages.json
***

**To see Listing the available languages**

`cucumber --i18n help`

**Listing the keywords of a particular language**

`cucumber --i18n <langauge_code>`

`cucumber --i18n fr`

Of course, for Java, you'll need a full command line: 

`java -cp "jars/*" cucumber.api.cli.Main --i18n fr `

(where "jars/*" is the folder that your Cucumber/Gherkin jars are located) 

A # language: header on the first line of a feature file tells Cucumber what spoken language to use - for example # language: fr for French. If you omit this header, Cucumber will default to English (en).

**JSON data for French Language:**

`fr: {`

`and: [`

`"* ",`

`"Et que ",`

`"Et qu'",`

`"Et "`

`],`

`background: [`

`"Contexte"`

`],`

`but: [`

`"* ",`

`"Mais que ",`

`"Mais qu'",`

`"Mais "`

`],`
`examples: [`

`"Exemples"`

`],`

`feature: [`

`"Fonctionnalité"`

`],`


`given: [`

`"* ",`

`"Soit ",`

`"Etant donné que ",`

`"Etant donné qu'",`

`"Etant donné ",`

`"Etant donnée ",`

`"Etant donnés ",`

`"Etant données ",`

`"Étant donné que ",`

`"Étant donné qu'",`

`"Étant donné ",`

`"Étant donnée ",`

`"Étant donnés ",`

`"Étant données "`

`],`

`name: "French",`

`native: "français",`

`scenario: [`

`"Scénario"`

`],`

`scenarioOutline: [`

`"Plan du scénario",`

`"Plan du Scénario"`

`],`

`then: [`

`"* ",`

`"Alors "`

`],`

`when: [`

`"* ",`

`"Quand ",`

`"Lorsque ",`

`"Lorsqu'"`

`]`

`},`

This wiki is the result of a discuss on [stackoverflow](http://stackoverflow.com/questions/34257188/where-are-the-translations-in-cucumber-gherkin/34263505#34263505)
Thanks to [Aravin](http://stackoverflow.com/users/3058254/aravin) and [Seb Rose](http://stackoverflow.com/users/12405/seb-rose)