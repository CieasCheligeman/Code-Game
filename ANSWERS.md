# Dew Point: answer key

Use this to play straight through and watch the scenes: the camera flies to a new place in Tokyo before every question, and answering everything correctly ends with the fall from the sky.

- **Multiple choice:** the options are shuffled each time, so look for the answer **text** below, not a letter.
- **"Click the line" questions:** click the line with the number and code shown.
- Answer all 28 correctly to get the **Sunshine** ending (the full sky-fall and rainbow). Too many wrong answers floods Tokyo instead.


## Chapter I · The First Drop
File: `project#1.cpp`

**1. Dividing whole numbers**  
_Line 35 sets `F_TO_C` to `5.0 / 9.0`. Imagine the author had typed `5 / 9` instead, with no decimal points. What value would `F_TO_C` hold?_  
✅ `0`

**2. Reading an if condition**  
_The user types `1.5` for the humidity. Is the condition on line 50 true or false?_  
✅ False. 1.5 is not ≤ 1.0, and with AND one failing side is enough to make it false.

**3. Edge values and “nan”**  
_The user types exactly `0` for the humidity, then `C` and `20`. What happens?_  
✅ 0 passes the check, and the program prints `The dew point temperature is: nan`.

**4. Checking only the first letter**  
_A user types `Fish` as the temperature unit, and the program accepts it as Fahrenheit. Click the line that lets this happen._  
✅ Click **line 63**: `if ( temp_unit.substr(0,1) == "F" || temp_unit.substr(0,1) == "C" )`

**5. Keeping units consistent**  
_This part of the program runs when the user chose Fahrenheit. Lines 95 and 96 print two temperatures. Which one is printed in the wrong unit?_  
✅ The dew point (`final_ans`). It is still in Celsius, because only `temp` was converted back.

**6. if / else and return**  
_The user types `X` as the temperature unit. What does the program do?_  
✅ Prints “Please enter the right temperature unit, thanks.” and then the program ends.


## Chapter II · Bulk Rain
File: `project#2.cpp`

**7. When a reading loop stops**  
_When does this `while` loop stop repeating?_  
✅ When reading fails, which usually means there are no lines left in the file.

**8. Spaces left behind**  
_A line in the file is `7/4/2019 0.5 20 C Kepler`. The four `>>` reads take `7/4/2019`, `0.5`, `20` and `C`. What does `getline` then store in `dataOfname`?_  
✅ `" Kepler"`, with a space at the front

**9. Capital vs. small letters**  
_The user types a capital `S`, hoping to choose single entry. What happens?_  
✅ It prints “You choose to quit.” and the program ends.

**10. Code hidden inside another if**  
_A data line has the date `4/31/2019`. The year 2019 is valid, but April has no 31st. Does the program ever reach the month and day checks (lines 451–458) for this date?_  
✅ No. They are inside the year check’s braces, which only run when the year is invalid.

**11. A copy-paste slip**  
_April 30th is a real date, but this code would call it invalid. Click the line with the mistake._  
✅ Click **line 479**: `if ( !(dayOfDate > 0 && dayOfDate <= FEB_DAY_MAX) )`

**12. Averages and dividing by zero**  
_A file contains only Fahrenheit readings. What does the last line print as the Celsius average?_  
✅ `nan`, because the Celsius total and count both stay 0, and 0 ÷ 0 has no answer.

**13. Cutting out part of a text**  
_While reading `"12/25/2019"`, line 430 runs with `begin_date = 3` and `i = 5`. What does `substr(begin_date, i - 1)` return?_  
✅ `"25/2"`


## Chapter III · Parallel Rivers
File: `project3.cpp`

**14. Sharing a list with a function**  
_`uploadFile` adds new readings to the lists. `allDetails` only prints them. Why does only `allDetails` use `const`?_  
✅ `uploadFile` has to change the lists, so it can’t promise not to. `allDetails` only reads them, so it can make that promise.

**15. An if without braces**  
_For the date 7/4/2021 (bad year), the program also prints “4 is not a valid day”, but July 4th is fine. Click the line that runs even though it shouldn’t._  
✅ Click **line 244**: `cout << "\t" << d << " is not a valid day, please check." << endl;`

**16. Following a calculation**  
_The function runs with `temp = 68`, `rh = 0.5`, `unit = 'F'`. Follow the `else` part. What number does it return?_  
✅ `93.6`

**17. Whole-number variables**  
_For one reading, `dew_point_calculation` gives back `9.25429`. What value ends up in `dewPoint`?_  
✅ `9`

**18. Swapped names**  
_Before these lines run: `cRH = 0.5` (1 Celsius reading, so `cRHNum = 1`) and `fRH = 1.0` (2 Fahrenheit readings, so `fRHNum = 2`). What is `cRH` after these lines?_  
✅ `0.25`

**19. Tracing a loop**  
_The user types `x` (read on line 340), then `x`, then `x`, then a valid `U`. What does this function return?_  
✅ `'.'`, so the program quits even though U was a valid choice.

**20. Measuring success correctly**  
_A file has 3 valid readings, 1 in Celsius and 2 in Fahrenheit, and all 3 are saved. Which message does the upload end with?_  
✅ “NOTE: The data file has failed to load.”


## Chapter IV · The Shape of Weather
File: `Project4(Most challenging).cpp`

**21. private and public**  
_In `main` (outside the class) there is a reading called `w`. Which line would C++ refuse to accept?_  
✅ `int m = w.month;`

**22. What a copy contains**  
_`tester1` holds the date text `"7/4/2019"` in `dataOfDate`. After it is copied into the list, what is the copy’s `dataOfDate`?_  
✅ `"unknown"`

**23. A comment is not code**  
_A 68 °F reading shows a dew point of `9.25 F`, but 9.25 is really in Celsius. Click the line where the missing code should go._  
✅ Click **line 513**: `//transfer dew point back to fahrenheit unit.`

**24. Promises with const**  
_The printing code calls `rhsObj.getDewPoint()`. What would happen if the author deleted the word `const` from the end of `getDewPoint() const`?_  
✅ C++ would refuse to build the program: a reading that must not change would be using a function that made no promise.

**25. Copying an object onto itself**  
_What situation does `if ( this != &obj )` watch for?_  
✅ Copying a reading onto itself, as in `w = w;`

**26. Spread needs two values**  
_The file has exactly one Celsius reading: `20`. What is `cDeviation` after line 742?_  
✅ `nan`

**27. An answer that is never set**  
_Suppose the caller’s variable already holds `true`, and this record is invalid (so the `else` on line 490 runs). After the call, what does the caller’s variable hold?_  
✅ Still `true`. The `else` never sets `answer`, so a bad record looks valid.

**28. Why build a class**  
_Final question. What is the biggest benefit of the Project 4 version?_  
✅ Each reading stays in one piece, so its parts can never get out of step, and the code is simpler to write.


## Shortcuts for just watching

Add these to the end of the file's address in the browser (after `index.html`), then reload:

| Add to the URL | What you see |
|---|---|
| `#end=clear` | The ending, including the full fall from the sky |
| `#end=weathering` | The other good ending (the sea stays) |
| `#end=drowned` | The ending you get if Tokyo floods |
| `#ch=3` | Jump straight to Chapter III (use 1 to 4) |
| `#sky=12` | Freeze the sky-fall at 12 seconds (try 4, 12, 17, 22, 31) |
| `#cam=p2:q5` | View one question's camera spot (`p1` to `p4`, `card`, `lesson`, `q1`…) |
| `#2d` / `#3d` | Force the classic 2D scene or the 3D Tokyo for one visit (the **Graphics** switch on the title screen does this permanently) |
