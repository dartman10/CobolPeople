---
title: EXIT PERFORM
date: "2020-10-24T22:12:03.284Z"
description: "When to use COBOL EXIT PERFORM"
---


**When to use EXIT PERFORM?**

    MOVE 'WIDGET' TO WS-SEARCH-VALUE  
    MOVE 0 TO WS-INDEX  
    PERFORM 999999999 TIMES  *> Endless loop. Inline perform.
      ADD 1 TO WS-INDEX  
      IF WS-INDEX > WS-ARRAY-SIZE *> Avoid array overflow  
        EXIT PERFORM              *> Exit inline perform  
      END-IF  
      IF WS-ARRAY(WS-INDEX) = WS-SEARCH-VALUE *> Search text  
        DISPLAY "Value found!"  
        EXIT PERFORM  *> Mission accomplished. Stop looping.
      END-IF  
      IF WS-ARRAY(WS-INDEX) = SPACES *> No more values  
        DISPLAY "Reached end of array values. None found."  
        EXIT PERFORM              *> Exit inline perform  
      END-IF  
    END-PERFORM  
