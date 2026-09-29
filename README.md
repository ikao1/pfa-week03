# pfa-week03
Assignment 3

# Building Simulator

## 1. Ten Lines, in Plain English

**Line 13:**
```python
import maya.cmds as cmds
```
It's a way to shorten the code because we're already in Maya and it becomes redundant to keep writing maya and it's more use to use other descriptors with a cmds.

---

**Line 21:**
```python
BUILDING_TYPES = {
```
This creates a rulebook for building types like min and max floors, height and the different options for customization.

---

**Line 24:**
```python
"min_floors": 20,
```
This is the lowest amount of floor the skyscraper option has. The GUI will have a min stop at 20.

---

**Line 27:**
```python
"floor_height": 3.5,
```
Each floor height is 3.5 Maya units tall. The script can use this information and increase the amount of floors to create the actual building height.

---

**Line 115:**
```python
def safe_cmds_call(func):
```
This is a function to check the options can pass before running the code.

---

**Line 122:**
```python
invalid = set(kwargs.keys()) - valid
```
List of invalid codes and compare with flagged codes and only let in the ones not in the list.

---

**Line 124:**
```python
raise TypeError(
```
It's a line that stops the script from continuing when flagged codes are found and it prevents Maya from crashing becuase of it.

---

**Line 128:**
```python
return func(*args, **kwargs)
```
Any flagged code that passeds can now run with the original context of the whole code.

---

**Line 636:**
```python
for floor in range(num_floors):
```
The script goes through each floor so the windows can be placed on each floor at the correct height position.

---

**Line 639:**
```python
for w in range(windows_per_floor):
```
This creates a window position to allow for a window plane the building floor.

---

## 2. Three Real Commits

1. **"Add building simulator with flag validation and multiple building types"** — Initial commit of the full script with skyscraper, high-rise apartment, and low-rise apartment support.

2. **"Add README with tool overview and setup instructions"** — Created README explaining what the tool does, how to run it in Maya, and what dependencies it needs.

3. **"Document ten-line walkthrough, loop analysis, and hand-edited line"** — Added the reading assignment sections: plain English explanations, loop paragraph, and the hand-changed line.

---

## 3. One Paragraph on the Loop

The main loop in this tool is the nested `for` loop starting at line 636. The outer loop iterates over each floor of the building (from `0` to `num_floors - 1`). Inside that, a second loop iterates over each window position on the current floor (from `0` to `windows_per_floor - 1`). Together, these loops create window planes on all four walls of every floor — front, back, left, and right. There is also a separate loop at line 587 that repeats the entire building creation process for however many buildings the user requested in the "Number of Buildings" slider. Without these loops, the script would only create one floor with one window, or one building total.

---

## 4. The Line You Changed by Hand

```python
backgroundColor=(0.2, 0.7, 0.2)
```

This line sets the "Generate Buildings" button to a green color so it stands out from the "Clear All" button and is easy to find in the UI.
