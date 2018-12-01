Sub chekingCells()
Range("d2").Select
Dim ss As String
Range("c1").End(xlDown).Select
ActiveCell.Offset(0, 1).Select
Dim fillcell As String
fillcell = ActiveCell.Address
'Range("d2:" & fillcell & "").FillDown
'Selection.AutoFill Destination:=Range("D2:" & fillcell & ""), Type:=xlFillDefault
Range("a1").End(xlDown).Select
Dim Name As String
ActiveCell.Offset(1, 0).Select
Name = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Phoneno As String
Phoneno = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Mailid As String
Mailid = ActiveCell.Address
Range("d2").Formula = "=countif(a2:c2," & Name & ")+countif(a2:c2," & Phoneno & ")+countif(a2:c2," & Mailid & ")"
Range("D2").Select
Selection.AutoFill Destination:=Range("D2:" & fillcell & ""), Type:=xlFillDefault
Range("D2:" & fillcell & "").Select
'fill the color
'Selection.FormatConditions.Add Type:=xlExpression, Formula1:="=$D2>0"
'    Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
 '   With Selection.FormatConditions(1).Interior
 '       .PatternColorIndex = xlAutomatic
 '       .Color = 255
 '       .TintAndShade = 0
 '   End With
 '   Selection.FormatConditions(1).StopIfTrue = False
End Sub



=A1:A2=$H2



------------------------

2nd requirment

---

Option Explicit

Sub Macrof2222()
'
' Macrof2222 Macro
'

'
    'Range("F1").Select
    'ActiveCell.FormulaR1C1 = "type below text"
    Dim countingdata As Integer
    Dim i As Integer
    Dim cell1 As String
    Dim cell2 As String
    Dim cell3 As String
    Range("g2").Formula = "=counta(a1:a7)"
    Range("g2").Select
    countingdata = ActiveCell.Value
    'Range("F2").Select
    Range("a1").End(xlDown).Select
    ActiveCell.Offset(1, 0).Select
    cell1 = ActiveCell.Address
    For i = 1 To countingdata
    Selection.FormatConditions.Add Type:=xlExpression, Formula1:= _
        "=$A" & i & "=" & cell1 & " "
    Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
    With Selection.FormatConditions(1).Interior
        .PatternColorIndex = xlAutomatic
        .Color = 65535
        .TintAndShade = 0
    End With
    Selection.FormatConditions(1).StopIfTrue = False
    Next
    ActiveCell.Offset(0, 1).Select
    cell2 = ActiveCell.Address
    For i = 1 To countingdata
    Selection.FormatConditions.Add Type:=xlExpression, Formula1:= _
        "=$B" & i & "=" & cell2 & " "
    Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
    With Selection.FormatConditions(1).Interior
        .PatternColorIndex = xlAutomatic
        .Color = 65535
        .TintAndShade = 0
    End With
    Selection.FormatConditions(1).StopIfTrue = False
    Next
    ActiveCell.Offset(0, 1).Select
    cell3 = ActiveCell.Address
    
End Sub
---------------
Option Explicit

Sub Macrof2222()
'
' Macrof2222 Macro
'

'
    'Range("F1").Select
    'ActiveCell.FormulaR1C1 = "type below text"
    Dim countingdata As Integer
    Dim i As Integer
    Dim cell1 As String
    Dim cell2 As String
    Dim cell3 As String
    Range("g2").Formula = "=counta(a1:a7)"
    Range("g2").Select
    countingdata = ActiveCell.Value
    'Range("F2").Select
    'A column cheking
    Range("A1").End(xlDown).Select
    ActiveCell.Offset(1, 0).Select
    cell1 = ActiveCell.Address
    For i = 1 To countingdata
    Selection.FormatConditions.Add Type:=xlExpression, Formula1:= _
        "=$A" & i & "=" & cell1 & " "
    Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
    With Selection.FormatConditions(1).Interior
        .PatternColorIndex = xlAutomatic
        .Color = 65535
        .TintAndShade = 0
    End With
    Selection.FormatConditions(1).StopIfTrue = False
    Next
    'B column cheking
    Range("g3").Formula = "=counta(B1:B7)"
    Range("g3").Select
    countingdata = ActiveCell.Value
    Range("B1").End(xlDown).Select
    ActiveCell.Offset(1, 0).Select
    cell2 = ActiveCell.Address
    For i = 1 To countingdata
    Selection.FormatConditions.Add Type:=xlExpression, Formula1:= _
        "=$B" & i & "=" & cell2 & " "
    Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
    With Selection.FormatConditions(2).Interior
        .PatternColorIndex = xlAutomatic
        .Color = 65500
        .TintAndShade = 0
    End With
    Selection.FormatConditions(1).StopIfTrue = False
    Next

End Sub
------


Option Explicit

Sub Macrof2222()
'
' Macrof2222 Macro
'

'
    'Range("F1").Select
    'ActiveCell.FormulaR1C1 = "type below text"
    Dim countingdata As Integer
    Dim i As Integer
    Dim cell1 As String
    Dim cell2 As String
    Dim cell3 As String
    Dim data As String
    Range("a1").End(xlDown).Select
    ActiveCell.Offset(0, 0).Select
    data = ActiveCell.Address
    Range("g2").Formula = "=counta(a1:" & data & ")"
    Range("g2").Select
    countingdata = ActiveCell.Value
    'Range("F2").Select
    'A column cheking
    Range("A1").End(xlDown).Select
    ActiveCell.Offset(1, 0).Select
    cell1 = ActiveCell.Address
    For i = 1 To countingdata
    Selection.FormatConditions.Add Type:=xlExpression, Formula1:= _
        "=$A" & i & "=" & cell1 & " "
    Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
    With Selection.FormatConditions(1).Interior
        .PatternColorIndex = xlAutomatic
        .Color = 65535
        .TintAndShade = 0
    End With
    Selection.FormatConditions(1).StopIfTrue = False
    Next
    'B column cheking
    Range("g3").Formula = "=counta(B1:B7)"
    Range("g3").Select
    countingdata = ActiveCell.Value
    Range("B1").End(xlDown).Select
    ActiveCell.Offset(1, 0).Select
    cell2 = ActiveCell.Address
    For i = 1 To countingdata
    Selection.FormatConditions.Add Type:=xlExpression, Formula1:= _
        "=$B" & i & "=" & cell2 & " "
    Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
    With Selection.FormatConditions(2).Interior
        .PatternColorIndex = xlAutomatic
        .Color = 65500
        .TintAndShade = 0
    End With
    Selection.FormatConditions(2).StopIfTrue = False
    Next

End Sub

------------------

perfectly working code:-
---

Option Explicit

Sub MacroA()
'
' Macrof2222 Macro
'

'
    'Range("F1").Select
    'ActiveCell.FormulaR1C1 = "type below text"
    Dim countingdataA As Integer
    Dim i As Integer
    Dim cell1 As String
    Dim dataA As String
    
    'A column cheking
    
    Range("A1").End(xlDown).Select
    ActiveCell.Offset(0, 0).Select
    dataA = ActiveCell.Address
    Range("g2").Formula = "=counta(A1:" & dataA & ")"
    Range("g2").Select
    countingdataA = ActiveCell.Value
    'Range("F2").Select
    Range("A1").End(xlDown).Select
    ActiveCell.Offset(1, 0).Select
    cell1 = ActiveCell.Address
    For i = 1 To countingdataA
    Selection.FormatConditions.Add Type:=xlExpression, Formula1:= _
        "=$A" & i & "=" & cell1 & " "
    Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
    With Selection.FormatConditions(1).Interior
        .PatternColorIndex = xlAutomatic
        .Color = 65535
        .TintAndShade = 0
    End With
    Selection.FormatConditions(1).StopIfTrue = False
    Next
    
    'B column cheking
    Dim countingdataB As Integer
    Dim cell2 As String
    Dim dataB As String
    Range("B1").End(xlDown).Select
    ActiveCell.Offset(0, 0).Select
    dataB = ActiveCell.Address
    Range("g3").Formula = "=counta(B1:" & dataB & ")"
    Range("g3").Select
    countingdataB = ActiveCell.Value
    Range("B1").End(xlDown).Select
    ActiveCell.Offset(1, 0).Select
    cell2 = ActiveCell.Address
    For i = 1 To countingdataB
    Selection.FormatConditions.Add Type:=xlExpression, Formula1:= _
        "=$B" & i & "=" & cell2 & " "
    Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
    With Selection.FormatConditions(1).Interior
        .PatternColorIndex = xlAutomatic
        .Color = 65500
        .TintAndShade = 0
    End With
    Selection.FormatConditions(1).StopIfTrue = False
    Next
    
    
    'C column cheking
    Dim countingdataC As Integer
    Dim dataC As String
    Dim cell3 As String
    Range("C1").End(xlDown).Select
    ActiveCell.Offset(0, 0).Select
    dataC = ActiveCell.Address
    Range("g4").Formula = "=counta(C1:" & dataC & ")"
    Range("g4").Select
    countingdataC = ActiveCell.Value
    Range("C1").End(xlDown).Select
    ActiveCell.Offset(1, 0).Select
    cell3 = ActiveCell.Address
    For i = 1 To countingdataC
    Selection.FormatConditions.Add Type:=xlExpression, Formula1:= _
        "=$C" & i & "=" & cell3 & " "
    Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
    With Selection.FormatConditions(1).Interior
        .PatternColorIndex = xlAutomatic
        .Color = 65400
        .TintAndShade = 0
    End With
    Selection.FormatConditions(1).StopIfTrue = False
    Next

End Sub


colors macrocode:-
---
Option Explicit

Sub Macrocolor()
'
' Macrocolor Macro
'

'
    Range("J9").Select
    With Selection.Font
        .Color = -16776961
        .TintAndShade = 0
    End With
    Range("J9").Select
    With Selection.Interior
        .Pattern = xlSolid
        .PatternColorIndex = xlAutomatic
        .Color = 255
        .TintAndShade = 0
        .PatternTintAndShade = 0
    End With
    Range("J10").Select
    With Selection.Font
        .Color = -16727809
        .TintAndShade = 0
    End With
    Range("J10").Select
    With Selection.Interior
        .Pattern = xlSolid
        .PatternColorIndex = xlAutomatic
        .Color = 49407
        .TintAndShade = 0
        .PatternTintAndShade = 0
    End With
    Range("J11").Select
    With Selection.Interior
        .Pattern = xlSolid
        .PatternColorIndex = xlAutomatic
        .Color = 5296274
        .TintAndShade = 0
        .PatternTintAndShade = 0
    End With
    With Selection.Interior
        .Pattern = xlSolid
        .PatternColorIndex = xlAutomatic
        .Color = 15773696
        .TintAndShade = 0
        .PatternTintAndShade = 0
    End With
    With Selection.Interior
        .Pattern = xlSolid
        .PatternColorIndex = xlAutomatic
        .ThemeColor = xlThemeColorAccent2
        .TintAndShade = 0.399975585192419
        .PatternTintAndShade = 0
    End With
    Range("J12").Select
    With Selection.Interior
        .Pattern = xlSolid
        .PatternColorIndex = xlAutomatic
        .ThemeColor = xlThemeColorLight2
        .TintAndShade = 0.399975585192419
        .PatternTintAndShade = 0
    End With
    Range("J13").Select
    With Selection.Interior
        .Pattern = xlSolid
        .PatternColorIndex = xlAutomatic
        .Color = 10498160
        .TintAndShade = 0
        .PatternTintAndShade = 0
    End With
    Range("J15").Select
End Sub

==============

Sub MacroNew()
'
' MacroNew Macro
'

'
    Range("A4:C4").Select
    Selection.Copy
    Range("A10:C10").Select
    ActiveSheet.Paste
    ActiveSheet.Paste
    Application.CutCopyMode = False
    Range("A11").Select
    ActiveCell.FormulaR1C1 = "kesava"
    Range("A11").Select
    Selection.ClearContents
    Range("B11").Select
    Selection.FormatConditions.Delete
    ActiveCell.FormulaR1C1 = "880138342"
    Range("B11").Select
    ActiveCell.FormulaR1C1 = "8801384532"
    Range("A11").Select
End Sub



=IF(ISBLANK($F6),0,SEARCH($F6,$A1&$B1&$C1))


=IF(ISBLANK($F$6),0,SEARCH($F$6,F6&G6&H6&K6))


=$F$6

=IF(ISBLANK($F5),0,SEARCH($F5,$A1&$B1&$C1))
======================


Sub MacroA()
'
' Macrof2222 Macro
'

'
    'Range("F1").Select
    'ActiveCell.FormulaR1C1 = "type below text"
    Dim countingdataA As Integer
    Dim i As Integer
    Dim cell1 As String
    Dim dataA As String
    
    'A column cheking
    
    Range("A1").End(xlDown).Select
    ActiveCell.Offset(0, 0).Select
    dataA = ActiveCell.Address
    Range("g3").Formula = "=counta(A2:" & dataA & ")"
    Range("g3").Select
    countingdataA = ActiveCell.Value
    'Range("F2").Select
    Range("A2").End(xlDown).Select
    'Selection.Copy
    ActiveCell.Offset(1, 0).Select
    cell1 = ActiveCell.Address
    For i = 2 To countingdataA
    Selection.FormatConditions.Add Type:=xlExpression, Formula1:= _
        "=$A" & i & "=" & cell1 & " "
    Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
    With Selection.FormatConditions(1).Interior
        .PatternColorIndex = xlAutomatic
        .Color = 255
        .TintAndShade = 0
        .PatternTintAndShade = 0
    End With
    Selection.FormatConditions(1).StopIfTrue = False
    Next
    
    'B column cheking
    Dim countingdataB As Integer
    Dim cell2 As String
    Dim dataB As String
    Range("B2").End(xlDown).Select
    ActiveCell.Offset(0, 0).Select
    dataB = ActiveCell.Address
    Range("g4").Formula = "=counta(B2:" & dataB & ")"
    Range("g4").Select
    countingdataB = ActiveCell.Value
    Range("B2").End(xlDown).Select
    ActiveCell.Offset(1, 0).Select
    cell2 = ActiveCell.Address
    For i = 2 To countingdataB
    Selection.FormatConditions.Add Type:=xlExpression, Formula1:= _
        "=$B" & i & "=" & cell2 & " "
    Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
    With Selection.FormatConditions(1).Interior
        .PatternColorIndex = xlAutomatic
        .Color = 15773696
        .TintAndShade = 0
        .PatternTintAndShade = 0
    End With
    Selection.FormatConditions(1).StopIfTrue = False
    Next
    
    
    'C column cheking
    Dim countingdataC As Integer
    Dim dataC As String
    Dim cell3 As String
    Range("C2").End(xlDown).Select
    ActiveCell.Offset(0, 0).Select
    dataC = ActiveCell.Address
    Range("g5").Formula = "=counta(C2:" & dataC & ")"
    Range("g5").Select
    countingdataC = ActiveCell.Value
    Range("C2").End(xlDown).Select
    ActiveCell.Offset(1, 0).Select
    cell3 = ActiveCell.Address
    For i = 2 To countingdataC
    Selection.FormatConditions.Add Type:=xlExpression, Formula1:= _
        "=$C" & i & "=" & cell3 & " "
    Selection.FormatConditions(Selection.FormatConditions.Count).
	SetFirstPriority
    With Selection.FormatConditions(1).Interior
        .PatternColorIndex = xlAutomatic
        .Color = 65400
        .TintAndShade = 0
    End With
    Selection.FormatConditions(1).StopIfTrue = False
    Next

End Sub
================
set myrange = thisworkbook.workshets("sheet1").usedRange

for each cell in myrange.cells

if cell.value = country


=========================


=SEARCH($F$6,$A1&$B1&$C1)

=$A$1:$C$4,$F$6

======================
working script to search all cells 

Option Explicit

Sub Macrosearchingdata()
'
' Macrosearchingdata Macro
'

'
    Range("A1:A2").Select
    Range(Selection, Selection.End(xlDown)).Select
    Range(Selection, Selection.End(xlToRight)).Select
    Selection.FormatConditions.Add Type:=xlExpression, Formula1:= _
        "=SEARCH($F$6,$A1&$B1&$C1)"
    Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
    With Selection.FormatConditions(1).Interior
        .PatternColorIndex = xlAutomatic
        .ThemeColor = xlThemeColorAccent4
        .TintAndShade = 0.799981688894314
    End With
    Selection.FormatConditions(1).StopIfTrue = False
    Range("F6").Select
    ActiveCell.FormulaR1C1 = "raj"
    Range("F6").Select
    ActiveCell.FormulaR1C1 = "kumar"
    Range("F6").Select
    Selection.ClearContents
    ActiveCell.FormulaR1C1 = "kesava"
    Range("F6").Select
    Selection.ClearContents
    ActiveCell.FormulaR1C1 = "hindu"
    Range("F6").Select
    Selection.ClearContents
    Range("F6").Select
    ActiveCell.FormulaR1C1 = "RAJ"
    Range("F6").Select
    Selection.ClearContents
    ActiveCell.FormulaR1C1 = "kumar"
    Range("F6").Select
    Selection.ClearContents
End Sub
====================
sample working code:
---

Sub test()
 Range(Selection, Selection.End(xlDown)).Select
    Range(Selection, Selection.End(xlToRight)).Select
    Selection.FormatConditions.Add Type:=xlExpression, Formula1:= _
        "=IF(ISBLANK($A$9),0,SEARCH($A$9,$A1&$B1&$C1))"
    Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
    With Selection.FormatConditions(1).Interior
        .PatternColorIndex = xlAutomatic
        .ThemeColor = xlThemeColorAccent4
        .TintAndShade = 0.799981688894314
    End With
    Selection.FormatConditions(1).StopIfTrue = False
    'Range("A9").Select
    'ActiveCell.FormulaR1C1 = $A9
End Sub

============================

working code:-
----
Sub Macrosearchingdata()
'
' Macrosearchingdata Macro
'
' Range("A1").End(xlDown).Select
    Dim countingdataA As Integer
    Dim i As Integer
    Dim cell1 As String
    Dim dataA As String
    Range("A1").End(xlDown).Select
    ActiveCell.Offset(0, 0).Select
    dataA = ActiveCell.Address
    Range("g3").Formula = "=counta(A2:" & dataA & ")"
    Range("g3").Select
    countingdataA = ActiveCell.Value
    Range("A2").End(xlDown).Select
    'Range("A2").End(xlToRight).Select
    'Selection.Copy
    ActiveCell.Offset(1, 0).Select
    cell1 = ActiveCell.Address
    'Range("A2:C5").End(xlDown).Select
    'Range("A2:C5").End(xlToRight).Select
    'Range(Selection, Selection.End(xlDown)).Select
    'Range(Selection, Selection.End(xlToRight)).Select
    Selection.FormatConditions.Add Type:=xlExpression, Formula1:= _
        "=IF(ISBLANK(" & cell1 & "),0,SEARCH(" & cell1 & ",$A2&$B2&$C2))"
    Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
    With Selection.FormatConditions(1).Interior
        .PatternColorIndex = xlAutomatic
        .Color = 255
        .TintAndShade = 0
        .PatternTintAndShade = 0
    End With
    Selection.FormatConditions(1).StopIfTrue = False
    End Sub
=========================================

It will display dialog box
------

Private Sub Worksheet_SelectionChange(ByVal Target As Range)
If Application.CountIf(Range("A:A"), Target) > 1 Then
MsgBox "Duplicate data!", vbCritical, "Remove Data"
Target.Value = ""
End If
If Application.CountIf(Range("A:A"), Target) > 1 Then
MsgBox "Duplicate data!", vbCritical, "Remove Data"
Target.Value = ""
End If
End Sub


===================================

working code
---

Sub chekingCells()
Range("d2").Select
Dim ss As String
Range("c1").End(xlDown).Select
ActiveCell.Offset(0, 1).Select
'ActiveCell.Offset(1, 0).Select
Dim fillcell As String
fillcell = ActiveCell.Address
'Range("d2:" & fillcell & "").FillDown
'Selection.AutoFill Destination:=Range("D2:" & fillcell & ""), Type:=xlFillDefault
Range("a1").End(xlDown).Select
Dim Name As String
ActiveCell.Offset(1, 0).Select
Name = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Phoneno As String
Phoneno = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Mailid As String
Mailid = ActiveCell.Address
Range("d2").Formula = "=countif(a2:c2," & Name & ")+countif(a2:c2," & Phoneno & ")+countif(a2:c2," & Mailid & ")"
Range("D2").Select
Selection.AutoFill Destination:=Range("D2:" & fillcell & ""), Type:=xlFillDefault
Range("D2:" & fillcell & "").Select

Range("g3").Formula = "=counta(D2:" & fillcell & ")"
Range("g3").Select

Dim countingdata As Integer
countingdata = ActiveCell.Value
Dim x As Integer
    
'fill the color
'Selection.FormatConditions.Add Type:=xlExpression, Formula1:="=$D2>0"
   'Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
    For x = 2 To countingdata
        If Range("$D" & x & " ").Value > 0 Then
            MsgBox "value Already exists in row " & x & ""
        End If
    Next

         'MsgBox "data already exists"
    'With Selection.FormatConditions(1).Interior
     '   .PatternColorIndex = xlAutomatic
      '  .Color = 15773696
       ' .TintAndShade = 0
    'End With
    'Selection.FormatConditions(1).StopIfTrue = False
End Sub

==========================

working one:-
---

Sub chekingCells()
Dim countingdata As Integer
 Dim dataC As String
Range("a2").End(xlDown).Select
ActiveCell.Offset(0, 0).Select
dataC = ActiveCell.Address
Range("g5").Formula = "=counta(a1:" & dataC & ")"
Range("g5").Select
countingdata = ActiveCell.Value
Range("d2").Select
Dim ss As String
Range("c1").End(xlDown).Select
ActiveCell.Offset(0, 1).Select
ActiveCell.Offset(1, 0).Select
Dim fillcell As String
fillcell = ActiveCell.Address
'Range("d2:" & fillcell & "").FillDown
'Selection.AutoFill Destination:=Range("D2:" & fillcell & ""), Type:=xlFillDefault
Range("a1").End(xlDown).Select
Dim Name As String
ActiveCell.Offset(1, 0).Select
Name = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Phoneno As String
Phoneno = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Mailid As String
Mailid = ActiveCell.Address
Range("d2").Formula = "=countif(a2:c2," & Name & ")+countif(a2:c2," & Phoneno & ")+countif(a2:c2," & Mailid & ")"
Range("D2").Select
Selection.AutoFill Destination:=Range("D2:" & fillcell & ""), Type:=xlFillDefault
Range("D2:" & fillcell & "").Select

Dim x As Integer
    
'fill the color
'Selection.FormatConditions.Add Type:=xlExpression, Formula1:="=$D2>0"
   'Selection.FormatConditions(Selection.FormatConditions.Count).SetFirstPriority
    For x = 2 To countingdata
        If Range("$D" & x & " ").Value > 0 Then
            MsgBox "value Already exists in row " & x & ""
            'Range("a" & x & ":d" & x & " ").Interior.Color = vbGreen
        End If
    Next

         'MsgBox "data already exists"
    'With Selection.FormatConditions(1).Interior
     '   .PatternColorIndex = xlAutomatic
      '  .Color = 15773696
       ' .TintAndShade = 0
    'End With
    'Selection.FormatConditions(1).StopIfTrue = False
End Sub
=====================


Range("A1").Select
Range("A1").End(xlDown).Select
ActiveCell.Offset(1, 0).Activate
ActiveCell.Select
Dim address As String
address = ActiveCell.address
Range("d2").Formula = "=countif(a2:c2,a3)+countif(a2:c2,b3)+countif(a2:c2,c3)"
If Range("d2").Value > 0 Then
    MsgBox "duplicate value"
 End If
 'Selection.AutoFill Destination:=Range("D2:" & fillcell & ""), Type:=xlFillDefault

============================== 
Sub sample()
Range("A1").Select
Range("A1").End(xlDown).Select
ActiveCell.Select
Dim address As String
address = ActiveCell.address
Range("g5").Formula = "=counta(a1:" & address & ")"
Range("g5").Select
Range("d2").Formula = "=countif(a2:c2,a4)+countif(a2:c2,b4)+countif(a2:c2,c4)"
If Range("d2").Value > 0 Then
    MsgBox "duplicate value"
 End If
Range("A1").Select
Range("A1").End(xlDown).Select
ActiveCell.Offset(1, 0).Activate
End Sub
==============================

Option Explicit
Sub chekingDuplicates()
Dim countingdata As Integer
Dim rowend As String
'Dim Target As Range
Range("a2").End(xlDown).Select
ActiveCell.Offset(0, 0).Select
rowend = ActiveCell.Address
Range("g5").Formula = "=counta(a1:" & rowend & ")"
Range("g5").Select
countingdata = ActiveCell.Value
Range("d2").Select
Dim ss As String
Range("c1").End(xlDown).Select
ActiveCell.Offset(0, 1).Select
'ActiveCell.Offset(1, 0).Select
Dim fillcell As String
fillcell = ActiveCell.Address
'Range("a1").End(xlDown).Select
Dim Name As String
'ActiveCell.Offset(1, 0).Select
Range(" " & rowend & " ").Select
'ActiveCell.Offset(1, 0).Select
ActiveCell.Select
Name = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Phoneno As String
Phoneno = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Mailid As String
Mailid = ActiveCell.Address
Range("d2").Formula = "=countif(a2:c2," & Name & ")+countif(a2:c2," & Phoneno & ")+countif(a2:c2," & Mailid & ")"
Range("D2").Select
Selection.AutoFill Destination:=Range("D2:" & fillcell & ""), Type:=xlFillDefault
Range("D2:" & fillcell & "").Select

Dim x As Integer
        For x = 2 To countingdata
        If Range("$D" & x & " ").Value > 0 Then
            MsgBox "value Already exists in row " & x & ""
            'Range("a" & x & ":d" & x & " ").Interior.Color = vbGreen
        End If
    Next
End Sub
===============================

Sub chekingDuplicates()
Dim countingdata As Integer
Dim rowend As String
'Dim Target As Range
Dim activevalueName As String
activevalueName = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim activephone As String
activephone = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim activemailid As String
activemailid = ActiveCell.Address

Range("a2").End(xlDown).Select
ActiveCell.Offset(0, 0).Select
rowend = ActiveCell.Address
Range("g5").Formula = "=counta(a1:" & rowend & ")"
Range("g5").Select
countingdata = ActiveCell.Value
Range("d2").Select
Dim ss As String
Range("c1").End(xlDown).Select
ActiveCell.Offset(0, 1).Select
'ActiveCell.Offset(1, 0).Select
Dim fillcell As String
fillcell = ActiveCell.Address
'Range("a1").End(xlDown).Select
Dim Name As String
'ActiveCell.Offset(1, 0).Select
Range(" " & rowend & " ").Select
'ActiveCell.Offset(1, 0).Select
ActiveCell.Select
'Name = ActiveCell.Address
'ActiveCell.Offset(0, 1).Select
'Dim Phoneno As String
'Phoneno = ActiveCell.Address
'activeCell.Offset(0, 1).Select
'Dim Mailid As String
'Mailid = ActiveCell.Address
Range("d2").Formula = "=countif(a2:c2," & activevalueName & ")+countif(a2:c2," & activephone & ")+countif(a2:c2," & activemailid & ")"
Range("D2").Select
Selection.AutoFill Destination:=Range("D2:" & fillcell & ""), Type:=xlFillDefault
Range("D2:" & fillcell & "").Select

Dim x As Integer
        For x = 2 To countingdata
        If Range("$D" & x & " ").Value > 0 Then
            MsgBox "value Already exists in row " & x & ""
            'Range("a" & x & ":d" & x & " ").Interior.Color = vbGreen
        End If
    Next
End Sub


================================


perfectly working macro (29-11-2018) ---> now working
---

Option Explicit

' name of the macro "duplicatesDetector"
' use to identify the duplicate values
' shortcut key ctrl+shift+A
' First to select cell then run the macro

Sub duplicatesDetector()
Dim countOfvalues As Integer
Dim rows As String

Dim Name As String
Name = ActiveCell.address
ActiveCell.Offset(0, 1).Select
Dim Phoneno As String
Phoneno = ActiveCell.address
ActiveCell.Offset(0, 1).Select
Dim Emailid As String
Emailid = ActiveCell.address

Range("a2").End(xlDown).Select
ActiveCell.Offset(0, 0).Select
rows = ActiveCell.address
Range("g5").Formula = "=counta(a1:" & rows & ")"
Range("g5").Select
countOfvalues = ActiveCell.Value
Range("d2").Select
Dim ss As String
Range("c1").End(xlDown).Select
ActiveCell.Offset(0, 1).Select

Dim fillcell As String
fillcell = ActiveCell.address

Range(" " & rows & " ").Select

ActiveCell.Select
Range("d2").Formula = "=countif(a2:c2," & Name & ")+countif(a2:c2," & Phoneno & ")+countif(a2:c2," & Emailid & ")"
Range("D2").Select
Range("D2:D" & countOfvalues - 1 & "").FillDown


Dim x As Integer
        For x = 2 To countOfvalues
        If Range("$D" & x & " ").Value > 0 Then
            MsgBox "value Already exists in row " & x & ""
        End If
    Next
 Range(" " & rows & " ").Select
ActiveCell.Offset(1, 0).Select
    
End Sub


-------------

Testing macro
---

Option Explicit
Sub sample()
Dim rows As Integer
Dim Destination As Range
Range("A1").Select
Range("A1").End(xlDown).Select
ActiveCell.Offset(1, 0).Activate
ActiveCell.Select
Dim address As String
address = ActiveCell.address
Range("g5").Formula = "=counta(a1:" & address & ")"
rows = Range("g5").Value
Range("d2").Formula = "=countif(a2:c2,a" & rows & ")+countif(a2:c2,b" & rows & ")+countif(a2:c2,c" & rows & ")"
Range("d2").Select
'Range("d2:" & rows & "").
Dim x As Integer
For x = 2 To rows
If Range("d" & x & " ").Value > 0 Then
    MsgBox "duplicate value Already exists in row " & x & ""
    Range("A1").Select
    Range("A1").End(xlDown).Select
 Else
    Range("A1").Select
    Range("A1").End(xlDown).Select
    ActiveCell.Offset(1, 0).Activate
 End If
Next
End Sub

=====================================
working code [29-11-2018]

Option Explicit


' name of the macro "duplicatesDetector"
' use to identify the duplicate values
' shortcut key ctrl+shift+A
' First to select cell then run the macro

Sub duplicateDetectorwithcolor()
Dim countOfvalues As Integer
Dim rows As String

Dim Name As String
Name = ActiveCell.address
ActiveCell.Offset(0, 1).Select
Dim Phoneno As String
Phoneno = ActiveCell.address
ActiveCell.Offset(0, 1).Select
Dim Emailid As String
Emailid = ActiveCell.address

'range("a2:c9").

Range("a2").End(xlDown).Select
ActiveCell.Offset(0, 0).Select
rows = ActiveCell.address
Range("g5").Formula = "=counta(a1:" & rows & ")"
Range("g5").Select
countOfvalues = ActiveCell.Value
Range("d2").Select
Dim ss As String
Range("c1").End(xlDown).Select
ActiveCell.Offset(0, 1).Select
Range("$D$2:$D$" & countOfvalues + 10 & "").Clear

'Dim fillcell As String
'fillcell = ActiveCell.address

Range(" " & rows & " ").Select
ActiveCell.Select
Range("d2").Formula = "=countif(a2:c2," & Name & ")+countif(a2:c2," & Phoneno & ")+countif(a2:c2," & Emailid & ")"
Range("D2").Select
' If any problem try to remove "-1" other add "-1"

Range("D2:D" & countOfvalues & "").FillDown
Range("$F$2:$F$" & countOfvalues + 10 & "").Clear
Range("$E$2:$E$" & countOfvalues + 5 & "").Clear

Dim x As Integer
        For x = 2 To countOfvalues
        If Range("$D" & x & " ").Value > 0 Then
            Range("$F" & x & " ").Select
             Range("$F" & x & " ").Value = 1
            'MsgBox "value Already exists in row " & x & ""
           ' .EntireRow.Interior.ColorIndex = 8
          ' Range("$D" & x & "").EntireRow.Interior.ColorIndex = 8
           
        End If
       ' Range("$E" & countOfvalues & "").Formula = "=sum(F1:F" & countOfvalues - 1 & ")"
      Range("e" & x & " ").Formula = "=sum(F2:F" & x & ")"
      'Range("e2:e" & countOfvalues & "").FillDown
    Next
    For x = 2 To countOfvalues
    If Range("$E" & x & "").Value > 1 Then
        selection.Interior.Color = xlNone
        Range("$E" & x & "").EntireRow.Interior.ColorIndex = 8
    End If
    Next
    
     'Range("e2").End(xlDown).Formula
     'Range("$E" & countOfvalues & "").Formula = "=sum(F1:F" & countOfvalues - 1 & ")"
      Range(" " & rows & " ").Select
ActiveCell.Offset(1, 0).Select
    
End Sub
=========================

perfectly working code[29-11-2018]
---
Option Explicit


' name of the macro "duplicatesDetector"
' use to identify the duplicate values
' shortcut key ctrl+1
' First to select cell then run the macro

Sub duplicateDetectorwithcolor()
Dim countOfvalues As Integer
Dim rows As String

Dim Name As String
Name = ActiveCell.address
ActiveCell.Offset(0, 1).Select
Dim Phoneno As String
Phoneno = ActiveCell.address
ActiveCell.Offset(0, 1).Select
Dim Emailid As String
Emailid = ActiveCell.address

Range("a2:z500").ClearFormats

Range("a2").End(xlDown).Select
ActiveCell.Offset(0, 0).Select
rows = ActiveCell.address
Range("g5").Formula = "=counta(a1:" & rows & ")"
Range("g5").Select
countOfvalues = ActiveCell.Value
Range("d2").Select
Dim ss As String
Range("c1").End(xlDown).Select
ActiveCell.Offset(0, 1).Select
Range("$D$2:$D$" & countOfvalues + 10 & "").Clear

'Dim fillcell As String
'fillcell = ActiveCell.address

Range(" " & rows & " ").Select
ActiveCell.Select
Range("d2").Formula = "=countif(a2:c2," & Name & ")+countif(a2:c2," & Phoneno & ")+countif(a2:c2," & Emailid & ")"
Range("D2").Select
' If any problem try to remove "-1" other add "-1"

Range("D2:D" & countOfvalues & "").FillDown
Range("$h$2:$h$" & countOfvalues + 10 & "").Clear
Range("$E$2:$E$" & countOfvalues + 5 & "").Clear

Dim x As Integer
        For x = 2 To countOfvalues
        If Range("$D" & x & " ").Value > 0 Then
            Range("$h" & x & " ").Select
             Range("$h" & x & " ").Value = 1
            'MsgBox "value Already exists in row " & x & ""
           ' .EntireRow.Interior.ColorIndex = 8
          ' Range("$D" & x & "").EntireRow.Interior.ColorIndex = 8
           
        End If
       ' Range("$E" & countOfvalues & "").Formula = "=sum(F1:F" & countOfvalues - 1 & ")"
      Range("e" & x & " ").Formula = "=sum(h2:h" & x & ")"
      'Range("e2:e" & countOfvalues & "").FillDown
    Next
    For x = 2 To countOfvalues
    If Range("$E" & x & "").Value > 1 Then
        selection.Interior.Color = xlNone
        Range("$A" & x & ":$E" & x & " ").Cells.Interior.ColorIndex = 8
    End If
    Next
      Range(" " & rows & " ").Select
ActiveCell.Offset(1, 0).Select
    
End Sub


===================

Option Explicit


' name of the macro "duplicatesDetector"
' use to identify the duplicate values
' shortcut key ctrl+l
' First to select cell then run the macro

Sub duplicateDetectorwithcolor()
Dim countOfvalues As Integer
Dim rows As String

Dim Name As String
Name = ActiveCell.address
ActiveCell.Offset(0, 1).Select
Dim Phoneno As String
Phoneno = ActiveCell.address
ActiveCell.Offset(0, 1).Select
Dim Emailid As String
Emailid = ActiveCell.address

Range("a2:z500").ClearFormats

Range("a2").End(xlDown).Select
ActiveCell.Offset(0, 0).Select
rows = ActiveCell.address
Range("h5").Formula = "=counta(a1:" & rows & ")"
Range("h5").Select
countOfvalues = ActiveCell.Value
Range("d2").Select
Dim ss As String
Range("c1").End(xlDown).Select
ActiveCell.Offset(0, 1).Select
Range("$D$2:$D$" & countOfvalues + 10 & "").Clear

'Dim fillcell As String
'fillcell = ActiveCell.address

Range(" " & rows & " ").Select
ActiveCell.Select
Range("d2").Formula = "=countif(a2:c2," & Name & ")+countif(a2:c2," & Phoneno & ")+countif(a2:c2," & Emailid & ")"
Range("D2").Select
' If any problem try to remove "-1" other add "-1"

Range("D2:D" & countOfvalues & "").FillDown
Range("$k$2:$k$" & countOfvalues + 10 & "").Clear
Range("$E$2:$E$" & countOfvalues + 5 & "").Clear

Dim x As Integer
        For x = 2 To countOfvalues
        If Range("$D" & x & " ").Value > 0 Then
            Range("$k" & x & " ").Select
             Range("$k" & x & " ").Value = 1
            'MsgBox "value Already exists in row " & x & ""
           ' .EntireRow.Interior.ColorIndex = 8
          ' Range("$D" & x & "").EntireRow.Interior.ColorIndex = 8
           
        End If
       ' Range("$E" & countOfvalues & "").Formula = "=sum(F1:F" & countOfvalues - 1 & ")"
      Range("e" & x & " ").Formula = "=sum(k2:k" & x & ")"
      'Range("e2:e" & countOfvalues & "").FillDown
    Next
    For x = 2 To countOfvalues
    If Range("$E" & x & "").Value > 1 Then
        selection.Interior.Color = xlNone
        Range("$A" & x & ":$E" & x & " ").Cells.Interior.ColorIndex = 8
    End If
    Next
      Range(" " & rows & " ").Select
ActiveCell.Offset(1, 0).Select
    
End Sub
=================
selected rows count:-
---

Private Sub CommandButton3_Click()

On Error GoTo ER
    ActiveSheet.Unprotect Password:="password"
    Selection.UnMerge
    Selection.Sort _
        Key1:=Range("C14"), Order1:=xlAscending
    Selection.Sort _
        Key1:=Range("A14"), Order1:=xlAscending, _
        Key2:=Range("B14"), Order2:=xlAscending, _
        Key3:=Range("F14"), Order3:=xlAscending
GoTo skip 'no error
ER:
ErrorMessage = MsgBox("An error has occurred.  Your operation has been canceled.", vbOKOnly, "JE Form - Sort Error")
skip:
    Dim q As Long
    Dim r As Long
    q = ActiveCell.Row
    r = Selection.Rows.Count
        ActiveCell.Resize(r).EntireRow.Activate
        Range(Cells(q, 11), Cells(q + r - 1, 13)).Merge True
        Range(Cells(q, 14), Cells(q + r - 1, 16)).Merge True
        Cells(14, 1).Activate
    ActiveSheet.Protect Password:="password"
End Sub

==============
perfectly working code [30-11-2018]
---


Option Explicit


' name of the macro "duplicatesDetector"
' use to identify the duplicate values
' shortcut key ctrl+l
' First to select cell then run the macro

Sub duplicateDetectorwithcolor(data)
Dim countOfvalues As Integer
Dim rows As String
Dim MNo As String
'MNo = ActiveCell.Address
Range("a" & data & " ").Select
MNo = Range("A" & data & " ").Address
ActiveCell.Offset(0, 1).Select
Dim DB As String
DB = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Name As String
Name = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Phoneno As String
Phoneno = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim mobile2 As String
mobile2 = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Emailid As String
Emailid = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim status As String
status = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim remarks As String
remarks = ActiveCell.Address

'cleaning the formatte
'Range("a2:z500").ClearFormats

'counting rows
Range("a2").End(xlDown).Select
ActiveCell.Offset(0, 0).Select
rows = ActiveCell.Address
Range("l2").Formula = "=counta(a1:" & rows & ")"
Range("l2").Select
countOfvalues = ActiveCell.Value
Range("i2").Select

'go to the end of the H column and move onestep right
Range("H1").End(xlDown).Select
ActiveCell.Offset(0, 1).Select
' cleaing the "I" column format
Range("$i$2:$i$" & countOfvalues + 30 & "").Clear

'Dim fillcell As String
'fillcell = ActiveCell.address

Range(" " & rows & " ").Select
ActiveCell.Select
'Range("i2").Formula = "=countif(a2:c2," & Name & ")+countif(a2:c2," & Phoneno & ")+countif(a2:c2," & Emailid & ")"
Range("i2").Formula = "=countif(a2:h2," & Phoneno & ")"
Range("i2").Select
' If any problem try to remove "-1" other add "-1"

Range("i2:i" & countOfvalues & "").FillDown
Range("$n$2:$n$" & countOfvalues + 30 & "").Clear
'Range("$j$2:$j$" & countOfvalues + 30 & "").Clear

Dim x As Integer
        For x = 2 To countOfvalues
        If Range("$i" & x & " ").Value > 0 Then
           Range("$n" & x & " ").Select
            Range("$n" & x & " ").Value = 1
            Range("j" & x & " ").Formula = "=sum(n2:n" & x & ")"
       
            'Range("$A" & x & ":$h" & x & " ").Cells.Interior.ColorIndex = 8
           
        End If
       ' Range("$E" & countOfvalues & "").Formula = "=sum(F1:F" & countOfvalues - 1 & ")"
        
      'Range("e2:e" & countOfvalues & "").FillDown
    Next
    For x = 2 To countOfvalues
    If Range("$j" & x & "").Value > 1 Then
        Selection.Interior.Color = xlNone
        Range("$A" & x & ":$h" & x & " ").Cells.Interior.ColorIndex = 8
    End If
   Next
      Range(" " & rows & " ").Select
ActiveCell.Offset(1, 0).Select
    
End Sub

Sub GetActiveCellRowNumber()

  'MsgBox ActiveCell.row
  
  'MsgBox Selection.rows.Count
 
    Dim activeRow As Long
    Dim NoOfRow As Long
    Dim x As Long
    Dim lessRow As Long
    Dim rowRange As Long
    Dim AddressofRow1 As String
    Dim AddressofRow2 As String
    'Selection.Interior.Color = xlNone
    
    'cleaning the formatte
    Range("a2:z500").ClearFormats
   
    activeRow = ActiveCell.roW
    Range("$j$2:$j$" & activeRow + 30 & "").Clear
    'AddressofRow1 = Range("$D" & activeRow & " ").Value
    NoOfRow = Selection.rows.Count
        ActiveCell.Resize(NoOfRow).EntireRow.Activate
    lessRow = NoOfRow - 1
    rowRange = lessRow + activeRow
     For x = activeRow To rowRange
     Call duplicateDetectorwithcolor(x)
     'Range("$a & x & ").Select
     'AddressofRow2 = Range("$a & x & ").Select
    'AddressofRow2 = Range("$D" & x & " ").Value
 Next
End Sub

=================
perfectly working macro for nikias:-[30-11-2018]
---

Option Explicit


' name of the macro "duplicatesDetector"
' use to identify the duplicate values
' shortcut key ctrl+l
' First to select cell then run the macro

Sub GetActiveCellRowNumber(data)
Dim countOfvalues As Integer
Dim transfer As String
Dim rows As String
Dim MNo As String
Range("a" & data & " ").Select
MNo = Range("A" & data & " ").Address
ActiveCell.Offset(0, 1).Select
Dim DB As String
DB = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Name As String
Name = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Phoneno As String
Phoneno = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim mobile2 As String
mobile2 = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Emailid As String
Emailid = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim status As String
status = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim remarks As String
remarks = ActiveCell.Address

'cleaning the formatte
'Range("a2:z500").ClearFormats

'counting rows
Range("a2").End(xlDown).Select
ActiveCell.Offset(0, 0).Select
rows = ActiveCell.Address
Range("l2").Formula = "=counta(a1:" & rows & ")"
Range("l2").Select
countOfvalues = ActiveCell.Value
Range("i2").Select

'go to the end of the H column and move onestep right
Range("H1").End(xlDown).Select
ActiveCell.Offset(0, 1).Select
' cleaing the "I" column format
Range("$i$2:$i$" & countOfvalues + 30 & "").Clear

'Dim fillcell As String
'fillcell = ActiveCell.address

Range(" " & rows & " ").Select
ActiveCell.Select
'Range("i2").Formula = "=countif(a2:c2," & Name & ")+countif(a2:c2," & Phoneno & ")+countif(a2:c2," & Emailid & ")"
Range("i2").Formula = "=countif(a2:h2," & Phoneno & ")"
Range("i2").Select
' If any problem try to remove "-1" other add "-1"

Range("i2:i" & countOfvalues & "").FillDown
Range("$n$2:$n$" & countOfvalues + 30 & "").Clear
'Range("$j$2:$j$" & countOfvalues + 30 & "").Clear

Dim x As Integer
        For x = 2 To countOfvalues
        If Range("$i" & x & " ").Value > 0 Then
           Range("$n" & x & " ").Select
            Range("$n" & x & " ").Value = 1
            Range("m" & x & " ").Formula = "=sum(n2:n" & x & ")"
            transfer = Range("m" & x & " ").Address
             Range("j" & x & " ") = Range("m" & x & " ").Value
                          
             
            'Range("$A" & x & ":$h" & x & " ").Cells.Interior.ColorIndex = 8
           
        End If
       ' Range("$E" & countOfvalues & "").Formula = "=sum(F1:F" & countOfvalues - 1 & ")"
        
      'Range("e2:e" & countOfvalues & "").FillDown
    Next
    For x = 2 To countOfvalues
    If Range("$j" & x & "").Value > 1 Then
        Selection.Interior.Color = xlNone
        Range("$A" & x & ":$h" & x & " ").Cells.Interior.ColorIndex = 8
        Range("$j" & x & " ").Cells.Interior.ColorIndex = 15
    End If
   Next
      Range(" " & rows & " ").Select
ActiveCell.Offset(1, 0).Select
    
End Sub


Sub duplicateDetectorwithcolor()

  ' defining variables
    Dim activeRow As Long
    Dim NoOfRow As Long
    Dim x As Long
    Dim lessRow As Long
    Dim rowRange As Long
    Dim AddressofRow1 As String
    Dim AddressofRow2 As String
   
    
    'cleaning the formatte
    Range("a2:z500").ClearFormats
   
    activeRow = ActiveCell.roW
    
    'clean the column j
    Range("$m$2:$m$" & activeRow + 30 & "").Clear
    Range("$j$2:$j$" & activeRow + 30 & "").Clear
    ' adding color for p4
    Range("$p4").Cells.Interior.ColorIndex = 15
    
    'AddressofRow1 = Range("$D" & activeRow & " ").Value
    NoOfRow = Selection.rows.Count
        ActiveCell.Resize(NoOfRow).EntireRow.Activate
    lessRow = NoOfRow - 1
    rowRange = lessRow + activeRow
     For x = activeRow To rowRange
     
     ' calling GetActiveCellRowNumber function
     Call GetActiveCellRowNumber(x)
 Next
End Sub

=================
working macro formated perfectly-[30-11-2018]
---

Option Explicit


' name of the macro "duplicatesDetector"
' use to identify the duplicate values
' shortcut key ctrl+l
' First to select cell then run the macro

Sub GetActiveCellRowNumber(data)
Dim countOfvalues As Integer
Dim transfer As String
Dim rows As String
Dim MNo As String
Range("a" & data & " ").Select
MNo = Range("A" & data & " ").Address
ActiveCell.Offset(0, 1).Select
Dim DB As String
DB = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Name As String
Name = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Phoneno As String
Phoneno = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim mobile2 As String
mobile2 = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim Emailid As String
Emailid = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim status As String
status = ActiveCell.Address
ActiveCell.Offset(0, 1).Select
Dim remarks As String
remarks = ActiveCell.Address

'counting rows
Range("a2").End(xlDown).Select
ActiveCell.Offset(0, 0).Select
rows = ActiveCell.Address
Range("l2").Formula = "=counta(a1:" & rows & ")"
Range("l2").Select
countOfvalues = ActiveCell.Value
Range("i2").Select

'go to the end of the H column and move onestep right
Range("H1").End(xlDown).Select
ActiveCell.Offset(0, 1).Select
' cleaing the "I" column format
Range("$i$2:$i$" & countOfvalues + 30 & "").Clear

'Dim fillcell As String
'fillcell = ActiveCell.address

Range(" " & rows & " ").Select
ActiveCell.Select

Range("i2").Formula = "=countif(a2:h2," & Phoneno & ")"
Range("i2").Select
' If any problem try to remove "-1" other add "-1"

Range("i2:i" & countOfvalues & "").FillDown
Range("$n$2:$n$" & countOfvalues + 30 & "").Clear

Dim x As Integer
        For x = 2 To countOfvalues
        If Range("$i" & x & " ").Value > 0 Then
           Range("$n" & x & " ").Select
            Range("$n" & x & " ").Value = 1
            Range("m" & x & " ").Formula = "=sum(n2:n" & x & ")"
            transfer = Range("m" & x & " ").Address
             Range("j" & x & " ") = Range("m" & x & " ").Value
        End If
    Next
    For x = 2 To countOfvalues
    If Range("$j" & x & "").Value > 1 Then
        Selection.Interior.Color = xlNone
        Range("$A" & x & ":$h" & x & " ").Cells.Interior.ColorIndex = 8
        Range("$j" & x & " ").Cells.Interior.ColorIndex = 15
    End If
   Next
      Range(" " & rows & " ").Select
      ActiveCell.Offset(1, 0).Select
    
End Sub


Sub duplicateDetectorwithcolor()

  ' defining variables
    Dim activeRow As Long
    Dim NoOfRow As Long
    Dim x As Long
    Dim lessRow As Long
    Dim rowRange As Long
    Dim AddressofRow1 As String
    Dim AddressofRow2 As String
   
    
    'cleaning the formatte
    Range("a2:z500").ClearFormats
   
    activeRow = ActiveCell.roW
    
    'clean the column j
    Range("$m$2:$m$" & activeRow + 30 & "").Clear
    Range("$j$2:$j$" & activeRow + 30 & "").Clear
    ' adding color for p4
    Range("$p4").Cells.Interior.ColorIndex = 15
    
    'AddressofRow1 = Range("$D" & activeRow & " ").Value
    NoOfRow = Selection.rows.Count
        ActiveCell.Resize(NoOfRow).EntireRow.Activate
    lessRow = NoOfRow - 1
    rowRange = lessRow + activeRow
     For x = activeRow To rowRange
     
     ' calling GetActiveCellRowNumber function
     Call GetActiveCellRowNumber(x)
 Next
End Sub








