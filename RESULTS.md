# UI lab results
Tool parts that I chose: Robot and Cypress

## Part 0
- Step 0.1, Chrome version: 157.0.8103.78 (Official Build) (arm64) 
- Step 0.3, ChromeDriver version: ChromeDriver 157.0.8103.78 (4b3d0dabb8250b6f152d2d85d79e7706e309d087-refs/branch-heads/8103@{#1573})
- Step 0.4, locator of Pizza, Please!: $x("//button[normalize-space()='Pizza, Please!']")
- Step 0.4, locator of Excluded tools: $x("//select[option[normalize-space()='Knife']]")
- Step 0.4, locator of Must be vegetarian: $x("//label[normalize-space()='Must be vegetarian']/preceding-sibling::input")
- Step 0.4, locator of Custom Pizza Name: $$("input#pizza-name")
- Step 0.5, pizza name, tool and calories of the run by hand:
| Step | Actual result | Pass or fail | |------|---------------|--------------| |1||| |2||| |3||| |4||| |5||| |6||| |7|||

## Part 3: Robot Framework
- robot --version:
- Step 3.2, failure message for the wrong title:
- Step 3.8, run 1, result, elapsed time and pizza name: - Step 3.8, run 2, result, elapsed time and pizza name:

## Part 4: Cypress
- node --version, npm --version and npx cypress version:
- Step 4.3, failure message for the wrong title:
- Step 4.6, tool and calories in the answer of POST /api/pizza: - Step 4.7, the line of the admin list that shows your pizza:
- Step 4.8, run 1, result, duration and pizza name:
- Step 4.8, run 2, result, duration and pizza name:
- Step 4.9 (optional), browser and result:

## Part B 
1.