---
title: DATE YYYYMMDD
date: "2020-10-29T22:12:03.284Z"
description: "Using DATE YYYYMMDD"
---
**How to use DATE YYYYMMDD**

    WORKING-STORAGE SECTION.
    01 WS-DATE PIC X(8).

    PROCEDURE DIVISION.
      ACCEPT WS-DATE FROM DATE YYYYMMDD
      DISPLAY 'Current date ='
              WS-DATE(1:4) '-'
              WS-DATE(5:2) '-'
              WS-DATE(7:2)
      GOBACK.

***Tags : COBOL DATE YYYYMMDD***
