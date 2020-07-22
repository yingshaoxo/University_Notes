# Script for ChaoXing

## Get questions from website

```python
from auto_everything.web import Selenium
from auto_everything.base import IO
import json
import os

my_selenium = Selenium("https://google.com", headless=False)
d = my_selenium.driver

problems = []

for file_name in [name for name in os.listdir(".") if ".html" in name]:
    d.get(f"file:///home/yingshaoxo/Documents/Fucking%20Document/{file_name}")

    xpath = """//*[@id="ZyBottom"]//div[contains(@class, 'TiMu')]"""
    elements = my_selenium.wait_until_exists(xpath)

    for block in elements:
        title = ""
        choices = ""

        title = block.find_elements_by_class_name("Zy_TItle")[0].find_element_by_class_name("clearfix").text
        print(title)
        try: 
            choices = "\n".join([one.find_element_by_tag_name("a").text.replace("\n", "") for one in block.find_elements_by_tag_name("li")])
            print(choices)
        except Exception as e:
            print(e)
        print('--'*10)

        problem = {
                "title": title,
                "choices": choices
        }
        problems.append(problem)

d.quit()
io = IO()
text = json.dumps(problems)
io.write("4.json", text)
```

## Generate txt file

```python
from auto_everything.base import IO
import json
import os

io = IO()
text = ""

for file_name in [name for name in os.listdir(".") if ".json" in name]:
    problems = json.loads(io.read(file_name))
    for problem in problems:
        single = False
        if problem.get("choices") != None:
            if problem["choices"].strip() == "":
                single = True
        else:
            single = True

        if single == True:
            question = problem.get("title").strip()
            #print(question)
            text += question + "\n"
        else:
            question = problem.get("title").strip()
            choices = problem.get("choices").strip()
            alphabet = list("ABCDEFGHIJKLMNOPQRSTUVWXYZ")
            new_choices = ""
            for index, one in enumerate(choices.split("\n")):
                prefix = alphabet[index] + ". "
                one = prefix + one
                new_choices += one + "\n"
            #print(question)
            text += question + "\n"
            #print(new_choices)
            text += new_choices + "\n"
        #print()
        text += "\n\n"

print(text)
io.write("final.txt", text)
```

## Add them all togather

```python
from auto_everything.web import Selenium
from auto_everything.base import IO
import json
import os

my_selenium = Selenium("https://google.com", headless=False)
d = my_selenium.driver

text = ""

for file_name in [name for name in os.listdir(".") if ".html" in name]:
    d.get(f"file:///home/yingshaoxo/Documents/Fucking%20Document/LTE/{file_name}")

    xpath = """//*[@id="ZyBottom"]//div[contains(@class, 'TiMu')]"""
    elements = my_selenium.wait_until_exists(xpath)

    problems = []

    for block in elements:
        title = ""
        choices = ""

        title = block.find_elements_by_class_name("Zy_TItle")[0].find_element_by_class_name("clearfix").text
        print(title)
        try:
            choices = "\n".join([one.find_element_by_tag_name("a").text.replace("\n", "") for one in block.find_elements_by_tag_name("li")])
            print(choices)
        except Exception as e:
            print(e)
        print('--'*10)

        problem = {
            "title": title,
            "choices": choices
        }
        problems.append(problem)

    text += "\n"*3 + "---" * 20 + "\n" + file_name + "\n" + "---" * 20 + "\n"*3

    for problem in problems:
        single = False
        if problem.get("choices") != None:
            if problem["choices"].strip() == "":
                single = True
        else:
            single = True

        if single == True:
            question = problem.get("title").strip()
            # print(question)
            text += question + "\n"
        else:
            question = problem.get("title").strip()
            choices = problem.get("choices").strip()
            alphabet = list("ABCDEFGHIJKLMNOPQRSTUVWXYZ")
            new_choices = ""
            for index, one in enumerate(choices.split("\n")):
                prefix = alphabet[index] + ". "
                one = prefix + one
                new_choices += one + "\n"
            # print(question)
            text += question + "\n"
            # print(new_choices)
            text += new_choices + "\n"
        # print()
        text += "\n\n"


d.quit()

print(text)
io = IO()
io.write("final.txt", text)
```

