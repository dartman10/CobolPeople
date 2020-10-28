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
      IF WS-INDEX > WS-ARRAY-SIZE *> Avoid array overflow  
        EXIT PERFORM              *> Exit inline perform  
      END-IF  
      IF WS-ARRAY(WS-INDEX) = WS-SEARCH-VALUE *> Search text  
        DISPLAY "Value found!"  
      END-IF  
      IF WS-ARRAY(WS-INDEX) = SPACES *> No more values  
        DISPLAY "Reached end of array! Value not found!"  
        EXIT PERFORM              *> Exit inline perform  
      END-IF  
    END-PERFORM  
