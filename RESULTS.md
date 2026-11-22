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

| Step | Actual result | Pass or fail | 
|------|---------------|--------------| 
| 1 | The heading reads Looking to break out of your pizza routine? |pass | 
| 2 | Max Calories per Slice, Excluded tools, Must be vegetarian and Custom Pizza Name appear | pass | 
| 3 | The fields show the values| pass | 
| 4 | The answer shows the pizza name (random name), a tool other than Knife (Pizza cutter), and 600 or fewer calories per slic (375) | pass | 
|5 | The page says Please log in first. | pass | 
|6 | The page shows Latest pizza recommendations | pass | 
|7| The line shows the pizza "random name (tool=Pizza cutter, ingredients_number=5)" | pass |

## Part 3: Robot Framework
- robot --version: Robot Framework 7.5.1 (Python 3.14.7 on darwin)
- Step 3.2, failure message for the wrong title: The Web Form Opens :: Open the web form and check its title.   | FAIL |
Title should have been 'Web Form' but was 'Web form'.
- Step 3.8, run 1, result, elapsed time and pizza name: 
    - 1 test, 1 passed, 0 failed 
    - 00:00:11.982 
    - Lab Pizza 20261123-005324
- Step 3.8, run 2, result, elapsed time and pizza name:
    - 1 test, 1 passed, 0 failed
    - 00:00:09.489
    - Lab Pizza 20261123-005938

## Part 4: Cypress
- node --version, npm --version and npx cypress version:
    - node: v24.21.0
    - npm: 11.19.0
    - cypress: cypress@16.2.1
- Step 4.3, failure message for the wrong title: AssertionError: Timed out retrying after 10000ms: expected 'Web form' to equal 'Web Form'
- Step 4.6, tool and calories in the answer of POST /api/pizza: Pizza cutter, 325
- Step 4.7, the line of the admin list that shows your pizza: Lab Pizza 20261123-021011 (tool=Pizza cutter, ingredients_number=5) (newest)
- Step 4.8, run 1, result, duration and pizza name: All specs passed!, 00:14, Lab Pizza 20261123-023005
- Step 4.8, run 2, result, duration and pizza name: All specs passed!, 00:13, Lab Pizza 20261123-023930
- Step 4.9 (optional), browser and result:

## Part B

1. The three number boxes of QuickPizza all share the id `floating_filled`. I think the page give each box its own id, so a tester can write a easier locator such as `id:max-calories`s.

2. It check the consistency or if the data saved correctly from both side. There could be a fault where the data shows on the recommend page and the one in the admin is different. For example, showing a different tool. 

3. A check can maybe add `expect(response.body.vegetarian).to.be.true`. Another source can be to have a fixed list of meat ingredients and check that none appears.

4. In Robot Framework I had to write the waits myself, Cypress waited by itself so Cypress was quicker to write. QP-01 is all in one  file and not need ChromeDriver, while Robot Framework needed it and a resource file and  environment variable. Cypress gave a video of the run too.

5. I would choose Cypress because I did not have to write a wait. The video and Command Log also make it easy to understand and find the cause of a fail.

6. In Robot Framework, if QuickPizza changed the calories box, I then can change only that one variable line in the resource file. The keywords Turn On Advanced and Fill In The Pizza Request use the variable, so they would pick up the new locator, and the test file would not change at all.

7. Cypress clears cookies before each test, so if there is a second test, the browser can land on a different server whose admin list does not contain the new pizza. Having one test keeps the same cookie and same server, so can see the correct pizza.