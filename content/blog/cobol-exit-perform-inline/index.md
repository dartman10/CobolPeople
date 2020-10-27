---
title: EXIT PERFORM
date: "2020-10-24T22:12:03.284Z"
description: "COBOL : EXIT PERFORM"
---


**Why use EXIT PERFORM?**

MOVE 'HELLNO' TO WS-SEARCH-VALUE
MOVE 0 TO WS-INDEX
PERFORM 999999999 TIMES  *> Endless loop. Inline perform.
  ADD 1 TO WS-INDEX
  IF WS-INDEX > WS-ARRAY-SIZE *> If array subscript is greater than array size - will cause overflow.
    EXIT PERFORM              *> Exit inline perform
  END-IF
  IF WS-ARRAY(WS-INDEX) = WS-SEARCH-VALUE   *> If value of array element is equal to search text
    DISPLAY "Value found!"
  END-IF
  IF WS-ARRAY(WS-INDEX) = SPACES   *> If array element is empty - no more values to check. Stop looping.
    DISPLAY "Reached end of array! Value not found!"
    EXIT PERFORM              *> Exit inline perform
  END-IF
END-PERFORM
