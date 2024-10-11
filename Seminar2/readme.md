## Session 2: Quantum Algorithms and AI
### Date: October 17, 2024
### Time: 10:00 AM
### Place: : Toyota Room, Flarsheim Hall
### Topics: 
- Quantum Speedup and AI  
- Grover's Algorithm  
- Quantum Fourier Transform (QFT)  
- Quantum Algorithms in AI  


### Additional Materials
#### Grover's algorithm Implementation on IBM Quantum Composer
https://quantum.ibm.com/composer/files/new?initial=N4IgdghgtgpiBcICyBPABAMwJYCcDOALmgMa7ECuWBIANCAI4R5QIgDyACgKIByAigEEAykjQAmAHQAGANwAdMFjDEANuQAmMNHIYwVWAEYBGCUuI75YejhgBzNPQDaYgLqXiN%2B8WduFCm3gwRPSWABYOMmhR0VEA9LFoQuQADjA4yQD2eFRYGWBoGRjiAHpiaIQQBDB4CgYQODhYaRFxCWw4EKpaGBk4aAA%2BUkYAfAoAHg6OUm4xMfGT0wC8g8NoALRrq05L-SMKxABeCy40k0YzszHjx5GXaPPbLotG65tRj8tSo2B1DU19IVaaAAIlgMBhyNk8mg2KkOgRegpwiFrijlEdHqcnOdLBM0cjLL9Gs1AUCkDAmOQbGgCKEtPRyAYqDUwLBKdTHutVt5ppY2XgqfTHOcuSRhb4wLQQJo8B4sMkCLlJYgBGgAEJ6FTlAiVOAAXyAA
#### Play with Grover's Algorithm on WolframAlpha:
Cell[BoxData[
 TagBox[
  StyleBox[
   DynamicModuleBox[{$CellContext`k$$ = 0, $CellContext`m$$ = 
    1, $CellContext`n$$ = 2, Typeset`show$$ = True, 
    Typeset`bookmarkList$$ = {}, Typeset`bookmarkMode$$ = "Menu", 
    Typeset`animator$$, Typeset`animvar$$ = 1, Typeset`name$$ = 
    "\"untitled\"", Typeset`specs$$ = {{{
       Hold[$CellContext`n$$], 2, "number of qubits: n"}, 2, 4, 1}, {{
       Hold[$CellContext`k$$], 0, "hidden item: k"}, 
      Dynamic[
       Range[0, 2^$CellContext`n$$ - 1]]}, {{
       Hold[$CellContext`m$$], 1, "number of iterations: m"}, 
      Dynamic[
       Range[1, 
        Ceiling[(Pi/4)/ArcSin[1/(2^$CellContext`n$$)^Rational[1, 2]]]]]}}, 
    Typeset`size$$ = {600., {196.5, 201.5}}, Typeset`update$$ = 0, 
    Typeset`initDone$$, Typeset`skipInitDone$$ = False, $CellContext`n$602$$ =
     0}, 
    DynamicBox[Manipulate`ManipulateBoxes[
     1, StandardForm, 
      "Variables" :> {$CellContext`k$$ = 0, $CellContext`m$$ = 
        1, $CellContext`n$$ = 2}, "ControllerVariables" :> {
        Hold[$CellContext`n$$, $CellContext`n$602$$, 0]}, 
      "OtherVariables" :> {
       Typeset`show$$, Typeset`bookmarkList$$, Typeset`bookmarkMode$$, 
        Typeset`animator$$, Typeset`animvar$$, Typeset`name$$, 
        Typeset`specs$$, Typeset`size$$, Typeset`update$$, Typeset`initDone$$,
         Typeset`skipInitDone$$}, 
      "Body" :> (
       If[$CellContext`k$$ > 2^$CellContext`n$$ - 1, $CellContext`k$$ = 0]; 
       If[$CellContext`m$$ > 
         Ceiling[(Pi/4)/ArcSin[
           1/(2^$CellContext`n$$)^Rational[1, 2]]], $CellContext`m$$ = 
         1]; $CellContext`mat00 = $CellContext`matModel[$CellContext`n$$, \
$CellContext`k$$, $CellContext`m$$]; $CellContext`mat01 = \
$CellContext`matModel[$CellContext`n$$, $CellContext`k$$, 
          2]; $CellContext`vec00 = Abs[
          $CellContext`finalVec[$CellContext`n$$, $CellContext`mat00]]; \
$CellContext`maxProb = Max[$CellContext`vec00]; $CellContext`pos = Flatten[
          Position[$CellContext`vec00, $CellContext`maxProb]]; Column[{
          Text[
           Row[{"optimal number of iterations:  ", 
             Style[
              Dynamic[
               Floor[(Pi/4)/ArcSin[1/(2^$CellContext`n$$)^Rational[1, 2]]]], 
              Red, Bold, 14]}]], 
          If[$CellContext`m$$ <= 2, 
           Show[
            $CellContext`circuit[$CellContext`mat00], Epilog -> Flatten[
              Table[{{Dashed, 
                 
                 Line[{{0.1 + 0.8 $CellContext`jj, 0.05}, {
                   0.1 + 0.8 $CellContext`jj, -0.05 - 
                    0.1 $CellContext`n$$}}]}, {Dashed, 
                 
                 Line[{{0.4 + 0.8 $CellContext`jj, 0.05}, {
                   0.4 + 0.8 $CellContext`jj, -0.05 - 
                    0.1 $CellContext`n$$}}]}}, {$CellContext`jj, 
                0, $CellContext`m$$ - 1}], 1], ImageSize -> {600, 180}], 
           Show[
            $CellContext`circuit[$CellContext`mat01], Epilog -> Flatten[
              Table[{{Dashed, 
                 
                 Line[{{0.1 + 0.8 $CellContext`jj, 0.05}, {
                   0.1 + 0.8 $CellContext`jj, -0.05 - 
                    0.1 $CellContext`n$$}}]}, {Dashed, 
                 
                 Line[{{0.4 + 0.8 $CellContext`jj, 0.05}, {
                   0.4 + 0.8 $CellContext`jj, -0.05 - 
                    0.1 $CellContext`n$$}}]}}, {$CellContext`jj, 0, 1}], 1], 
            ImageSize -> {600, 180}]], 
          ListPlot[
           
           Table[{$CellContext`j, 
             Part[$CellContext`vec00, $CellContext`j]^2}, {$CellContext`j, 
             Length[$CellContext`vec00]}], PlotStyle -> {
             PointSize[0.02], Red}, Filling -> Axis, FillingStyle -> Red, 
           Ticks -> {
             Table[{$CellContext`j, 
               ToString[$CellContext`j - 1]}, {$CellContext`j, 
               Length[$CellContext`vec00]}], Automatic}, AxesLabel -> {
             Which[$CellContext`n$$ == 2, 
              Style[
               Row[{"|", 
                 Style["x", Italic], "\[RightAngleBracket] \[Congruent] |", 
                 Subscript[
                  Style["b", Italic], 1], ",", 
                 Subscript[
                  Style["b", Italic], 2], "\[RightAngleBracket]"}], 
               12], $CellContext`n$$ == 3, 
              Style[
               Row[{"|", 
                 Style["x", Italic], "\[RightAngleBracket] \[Congruent] |", 
                 Subscript[
                  Style["b", Italic], 1], ",", 
                 Subscript[
                  Style["b", Italic], 2], ",", 
                 Subscript[
                  Style["b", Italic], 3], "\[RightAngleBracket]"}], 
               12], $CellContext`n$$ == 4, 
              Style[
               Row[{"|", 
                 Style["x", Italic], "\[RightAngleBracket] \[Congruent] |", 
                 Subscript[
                  Style["b", Italic], 1], ",", 
                 Subscript[
                  Style["b", Italic], 2], ",", 
                 Subscript[
                  Style["b", Italic], 3], ",", 
                 Subscript[
                  Style["b", Italic], 4], "\[RightAngleBracket]"}], 12]], 
             Style["P", Italic]}, AspectRatio -> 1/4, 
           PlotRange -> {-0.1, 1.1}, PlotLabel -> 
           Style["Probability distribution in the final state", 14], 
           ImageSize -> {400 + 50 ($CellContext`n$$ - 2), 150}, 
           BaseStyle -> {12}, AxesOrigin -> {0.5, 0}], 
          Text[
           Style[
            Row[{"Probability takes a maximum ", 
              Style["P", Italic], (" = " <> ToString[
                 N[$CellContext`maxProb, 2]]) <> " for ", 
              Style["x", Italic], " =" <> StringReplace[
                ToString[$CellContext`pos - 1], {"{" -> " ", "}" -> " "}]}], 
            Bold, 14]]}, Spacings -> {Automatic, 1}, Alignment -> Center]), 
      "Specifications" :> {{{$CellContext`n$$, 2, "number of qubits: n"}, 2, 
         4, 1}, {{$CellContext`k$$, 0, "hidden item: k"}, 
         Dynamic[
          Range[0, 2^$CellContext`n$$ - 1]]}, {{$CellContext`m$$, 1, 
          "number of iterations: m"}, 
         Dynamic[
          Range[1, 
           Ceiling[(Pi/4)/ArcSin[1/(2^$CellContext`n$$)^Rational[1, 2]]]]]}}, 
      "Options" :> {
       ControlType -> Setter, TrackedSymbols -> Manipulate, 
        AutorunSequencing -> {1}}, 
      "DefaultOptions" :> {ControllerLinking -> True}],
     ImageSizeCache->{646., {266.6875, 272.3125}},
     SingleEvaluation->True],
    Deinitialization:>None,
    DynamicModuleValues:>{},
    Initialization:>({$CellContext`mat00 = {{
         "H", "X", "C", "X", "H", "X", "C", "X", "H"}, {
         "H", "X", "C", "X", "H", "X", "Z", "X", "H"}, {
         "H", 1, "N", 1, 1, 1, 1, 1, 1}}, $CellContext`matModel[
         Pattern[$CellContext`n, 
          Blank[]], 
         Pattern[$CellContext`k, 
          Blank[]], 
         Pattern[$CellContext`iteration, 
          Blank[]]] := Nest[Join[#, 
          $CellContext`matGrover[$CellContext`n, $CellContext`k], 2]& , 
         $CellContext`initialMat[$CellContext`n], $CellContext`iteration], \
$CellContext`matGrover[
         Pattern[$CellContext`n, 
          Blank[]], 
         Pattern[$CellContext`k, 
          Blank[]]] := Join[
         $CellContext`oracle[$CellContext`n, $CellContext`k], 
         $CellContext`matW[$CellContext`n], 2], $CellContext`oracle[
         Pattern[$CellContext`n, 
          Blank[]], 
         Pattern[$CellContext`k, 
          Blank[]]] := If[0 <= $CellContext`k <= 2^$CellContext`n - 1, 
         Transpose[{
           Append[
            ReplaceAll[
             IntegerDigits[$CellContext`k, 2, $CellContext`n], 0 -> "X"], 1], 
           
           Append[
            Table["C", {$CellContext`n}], "N"], 
           Append[
            ReplaceAll[
             IntegerDigits[$CellContext`k, 2, $CellContext`n], 0 -> "X"], 
            1]}]], $CellContext`matW[
         Pattern[$CellContext`n, 
          Blank[]]] := Append[
         Append[
          Table[{"H", "X", "C", "X", "H"}, {$CellContext`n - 1}], {
          "H", "X", "Z", "X", "H"}], {1, 1, 1, 1, 1}], $CellContext`initialMat[
         Pattern[$CellContext`n, 
          Blank[]]] := 
       Table[{"H"}, {$CellContext`n + 1}], $CellContext`mat01 = {{
         "H", "X", "C", "X", "H", "X", "C", "X", "H", "X", "C", "X", "H", "X",
           "C", "X", "H"}, {
         "H", "X", "C", "X", "H", "X", "Z", "X", "H", "X", "C", "X", "H", "X",
           "Z", "X", "H"}, {
         "H", 1, "N", 1, 1, 1, 1, 1, 1, 1, "N", 1, 1, 1, 1, 1, 
          1}}, $CellContext`vec00 = {1, 0, 0, 0}, $CellContext`finalVec[
         Pattern[$CellContext`n, 
          Blank[]], 
         Pattern[$CellContext`mat, 
          Blank[]]] := (Take[#, {2, 
          Length[#], 2}]& )[
         Dot[
          $CellContext`matrixU[
           Join[$CellContext`mat, 
            Append[
             Table[{1}, {$CellContext`n}], {"H"}], 2]], 
          Table[
           
           If[$CellContext`j == 2, 1, 0], {$CellContext`j, 
            2^($CellContext`n + 1)}]]], $CellContext`matrixU[
         PatternTest[
          Pattern[$CellContext`mat, 
           Blank[]], MatrixQ]] := 
       Block[{$CellContext`matTransp, $CellContext`col, $CellContext`matU1}, \
$CellContext`matTransp = Transpose[$CellContext`mat]; $CellContext`col = 
          Length[$CellContext`matTransp]; $CellContext`matU1 = 
          If[$CellContext`col > 1, $CellContext`matU1 = Apply[Dot, 
              Reverse[
               Map[$CellContext`gateColumn[#]& , $CellContext`matTransp, 1]]], 
            $CellContext`gateColumn[$CellContext`matTransp]]; \
$CellContext`matU1], $CellContext`gateColumn[
         PatternTest[
          Pattern[$CellContext`col, 
           Blank[]], ListQ]] := 
       Block[{$CellContext`nq, $CellContext`p1, $CellContext`pc, \
$CellContext`matg}, $CellContext`nq = Length[$CellContext`col]; Which[
           And[
            MemberQ[$CellContext`col, "C"], 
            MemberQ[$CellContext`col, "N"]], $CellContext`p1 = Part[
              Position[$CellContext`col, "N"], 1, 1]; $CellContext`pc = 
            Flatten[
              
              Position[$CellContext`col, 
               "C"]]; $CellContext`matg = \
$CellContext`gateCN[$CellContext`nq, $CellContext`p1, $CellContext`pc], 
           And[
            MemberQ[$CellContext`col, "C"], 
            MemberQ[$CellContext`col, "Z"]], $CellContext`p1 = Part[
              Position[$CellContext`col, "Z"], 1, 1]; $CellContext`pc = 
            Flatten[
              
              Position[$CellContext`col, 
               "C"]]; $CellContext`matg = \
$CellContext`gateCZ[$CellContext`nq, $CellContext`p1, $CellContext`pc], 
           
           FreeQ[$CellContext`col, 
            "C"], $CellContext`matg = $CellContext`gateChoose[
              Part[$CellContext`col, 1]]; 
           Do[$CellContext`matg = ArrayFlatten[
               Outer[Times, $CellContext`matg, 
                $CellContext`gateChoose[
                 Part[$CellContext`col, $CellContext`j]]]], {$CellContext`j, 
              2, $CellContext`nq}]]; $CellContext`matg], $CellContext`gateCN[
         Pattern[$CellContext`n, 
          Blank[]], 
         Pattern[$CellContext`kn, 
          Blank[]], 
         PatternTest[
          Pattern[$CellContext`kc, 
           Blank[]], ListQ]] := 
       Block[{$CellContext`b1, $CellContext`u0, $CellContext`rules}, \
$CellContext`b1 = Table[
            
            IntegerDigits[$CellContext`j, 2, $CellContext`n], {$CellContext`j,
              0, 2^$CellContext`n - 1}]; $CellContext`rules = 
          Table[{FromDigits[
                ReplacePart[
                 Part[$CellContext`b1, $CellContext`j], $CellContext`kn -> 
                 Mod[Apply[Times, 
                    Part[$CellContext`b1, $CellContext`j, $CellContext`kc]] + 
                   Part[$CellContext`b1, $CellContext`j, $CellContext`kn], 
                   2]], 2] + 1, $CellContext`j} -> 
            1, {$CellContext`j, 2^$CellContext`n}]; $CellContext`u0 = 
          SparseArray[$CellContext`rules, {
            2^$CellContext`n, 
             2^$CellContext`n}]; $CellContext`u0], $CellContext`gateCZ[
         Pattern[$CellContext`n, 
          Blank[]], 
         Pattern[$CellContext`kn, 
          Blank[]], 
         PatternTest[
          Pattern[$CellContext`kc, 
           Blank[]], ListQ]] := 
       Block[{$CellContext`b1, $CellContext`u0, $CellContext`rules}, \
$CellContext`b1 = Table[
            
            IntegerDigits[$CellContext`j, 2, $CellContext`n], {$CellContext`j,
              0, 2^$CellContext`n - 1}]; $CellContext`rules = 
          Table[{$CellContext`j, $CellContext`j} -> If[Apply[Times, 
                Part[$CellContext`b1, $CellContext`j, $CellContext`kc]] == 
              1, (-1)^Part[$CellContext`b1, $CellContext`j, $CellContext`kn], 
              1], {$CellContext`j, 2^$CellContext`n}]; $CellContext`u0 = 
          SparseArray[$CellContext`rules, {
            2^$CellContext`n, 
             2^$CellContext`n}]; $CellContext`u0], $CellContext`gateChoose[
         Pattern[$CellContext`x, 
          Blank[]]] := Which[
         MatchQ[$CellContext`x, 1], $CellContext`matI, 
         MatchQ[$CellContext`x, "H"], $CellContext`matH, 
         MatchQ[$CellContext`x, "X"], $CellContext`matX, 
         MatchQ[$CellContext`x, 
          "Z"], $CellContext`matZ], $CellContext`matI = {{1, 0}, {0, 
        1}}, $CellContext`matH = {{1/Sqrt[2], 1/Sqrt[2]}, {
         1/Sqrt[2], -(1/Sqrt[2])}}, $CellContext`matX = {{0, 1}, {1, 
        0}}, $CellContext`matZ = {{1, 0}, {0, -1}}, $CellContext`maxProb = 
       1, $CellContext`pos = {1}, $CellContext`circuit[
         PatternTest[
          Pattern[$CellContext`x, 
           Blank[]], MatrixQ]] := 
       Block[{$CellContext`inputMat, $CellContext`matTransp, \
$CellContext`qubits, $CellContext`col, $CellContext`q1, $CellContext`obj, \
$CellContext`qubitIn, $CellContext`qubitOut, $CellContext`column, \
$CellContext`bit, $CellContext`q2, $CellContext`q3, $CellContext`q4, \
$CellContext`tof, $CellContext`n1, $CellContext`n2}, $CellContext`inputMat = \
$CellContext`x; $CellContext`qubits = 
          Length[$CellContext`inputMat]; $CellContext`col = Length[
            
            Part[$CellContext`inputMat, 
             1]]; $CellContext`q1 = $CellContext`qubits - 
           1; $CellContext`qubitIn = 
          Table["|0\[RightAngleBracket]", {$CellContext`j, \
$CellContext`qubits - 1}]; $CellContext`qubitIn = 
          Append[$CellContext`qubitIn, 
            "|1\[RightAngleBracket]"]; $CellContext`qubitOut = Table[
            Row[{"|", 
              Subscript[
               Style["b", Italic], $CellContext`j], 
              "\[RightAngleBracket]"}], {$CellContext`j, \
$CellContext`qubits}]; $CellContext`obj = Table[
            Text[
             
             Part[$CellContext`qubitIn, $CellContext`j + 
              1], {-0.05, (-0.1) $CellContext`j}], {$CellContext`j, 
             0, $CellContext`q1}]; $CellContext`obj = Join[$CellContext`obj, 
            Table[
             Text[
              Part[$CellContext`qubitOut, $CellContext`j + 1], {
              0.1 $CellContext`col + 
               0.05, (-0.1) $CellContext`j}], {$CellContext`j, 
              0, $CellContext`q1}]]; $CellContext`matTransp = 
          Transpose[$CellContext`inputMat]; 
         Do[$CellContext`column = 
            Part[$CellContext`matTransp, $CellContext`k2]; $CellContext`n1 = 
            0; If[
             FreeQ[$CellContext`column, "C"], $CellContext`n2 = 
             0, $CellContext`n2 = 1]; Do[$CellContext`bit = Which[
                MatchQ[
                 Part[$CellContext`column, $CellContext`k1], 1], 
                $CellContext`unit[$CellContext`k1, $CellContext`k2], 
                MatchQ[
                 Part[$CellContext`column, $CellContext`k1], "C"], 
                $CellContext`controlC[$CellContext`k1, $CellContext`k2], 
                MatchQ[
                 Part[$CellContext`column, $CellContext`k1], "N"], 
                $CellContext`targetN[$CellContext`k1, $CellContext`k2], 
                MatchQ[
                 Part[$CellContext`column, $CellContext`k1], "H"], 
                $CellContext`hadamardGate[$CellContext`k1, $CellContext`k2], 
                MatchQ[
                 Part[$CellContext`column, $CellContext`k1], "X"], 
                $CellContext`gateX[$CellContext`k1, $CellContext`k2], 
                MatchQ[
                 Part[$CellContext`column, $CellContext`k1], "Z"], 
                $CellContext`gateZ[$CellContext`k1, $CellContext`k2]]; \
$CellContext`obj = 
              Join[$CellContext`obj, {$CellContext`bit}], {$CellContext`k1, \
$CellContext`qubits}]; If[$CellContext`n2 == 1, Do[
               Which[
                And[$CellContext`n1 == 0, 
                 MemberQ[{"C", "N"}, 
                  
                  Part[$CellContext`column, $CellContext`k1]]], \
$CellContext`q2[$CellContext`n1] = $CellContext`k1; $CellContext`n1 = \
$CellContext`n1 + 1, 
                And[$CellContext`n1 == 0, 
                 MemberQ[{"Z"}, 
                  
                  Part[$CellContext`column, $CellContext`k1]]], \
$CellContext`q2[$CellContext`n1] = $CellContext`k1 + 
                  1/4; $CellContext`n1 = $CellContext`n1 + 1, 
                And[$CellContext`n1 > 0, 
                 MemberQ[{"C", "N"}, 
                  
                  Part[$CellContext`column, $CellContext`k1]]], \
$CellContext`q2[$CellContext`n1] = $CellContext`k1; $CellContext`n1 = \
$CellContext`n1 + 
                  1; $CellContext`q2[$CellContext`n1] = \
($CellContext`q2[$CellContext`n1 + 
                    1] = $CellContext`k1); $CellContext`n1 = $CellContext`n1 + 
                  1, 
                And[$CellContext`n1 > 0, 
                 MemberQ[{"Z"}, 
                  
                  Part[$CellContext`column, $CellContext`k1]]], \
$CellContext`q2[$CellContext`n1] = $CellContext`k1 - 1/
                  4; $CellContext`n1 = $CellContext`n1 + 
                  1; $CellContext`q2[$CellContext`n1] = \
($CellContext`q2[$CellContext`n1 + 1] = $CellContext`k1 + 
                   1/4); $CellContext`n1 = $CellContext`n1 + 
                  1], {$CellContext`k1, $CellContext`qubits}]; \
$CellContext`obj = Join[$CellContext`obj, 
                Table[
                 $CellContext`lineVert[
                  $CellContext`q2[$CellContext`i], 
                  $CellContext`q2[$CellContext`i + 
                   1], $CellContext`k2], {$CellContext`i, 0, $CellContext`n1, 
                  2}]]], {$CellContext`k2, $CellContext`col}]; Show[
           Graphics[$CellContext`obj], 
           PlotRange -> {{-0.12, 0.1 $CellContext`col + 
              0.12}, {(-0.1) $CellContext`qubits + 0.05, 0.05}}, AspectRatio -> 
           Automatic, Frame -> True, FrameTicks -> None]], 
       Attributes[Subscript] = {NHoldRest}, $CellContext`unit[
         Pattern[$CellContext`yy, 
          Blank[]], 
         Pattern[$CellContext`xx, 
          Blank[]]] := 
       Block[{$CellContext`x, $CellContext`y}, $CellContext`x = 
          0.1 ($CellContext`xx - 1); $CellContext`y = 
          0.1 (1 - $CellContext`yy); {
           
           Line[{{$CellContext`x, $CellContext`y}, {$CellContext`x + 
              0.1, $CellContext`y}}]}], $CellContext`controlC[
         Pattern[$CellContext`yy, 
          Blank[]], 
         Pattern[$CellContext`xx, 
          Blank[]]] := 
       Block[{$CellContext`x, $CellContext`y}, $CellContext`x = 
          0.1 ($CellContext`xx - 1); $CellContext`y = 
          0.1 (1 - $CellContext`yy); {{
            
            Line[{{$CellContext`x, $CellContext`y}, {$CellContext`x + 
               0.1, $CellContext`y}}]}, {
            PointSize[0.015], 
            
            Point[{$CellContext`x + 
              0.05, $CellContext`y}]}}], $CellContext`targetN[
         Pattern[$CellContext`yy, 
          Blank[]], 
         Pattern[$CellContext`xx, 
          Blank[]]] := 
       Block[{$CellContext`x, $CellContext`y}, $CellContext`x = 
          0.1 ($CellContext`xx - 1); $CellContext`y = 
          0.1 (1 - $CellContext`yy); {{
            
            Line[{{$CellContext`x, $CellContext`y}, {$CellContext`x + 
               0.1, $CellContext`y}}]}, {
            Thickness[0.005], 
            Circle[{$CellContext`x + 0.05, $CellContext`y}, 0.017]}, {
            
            Line[{{$CellContext`x + 0.05, $CellContext`y - 
               0.017}, {$CellContext`x + 0.05, $CellContext`y + 
               0.017}}]}}], $CellContext`hadamardGate[
         Pattern[$CellContext`yy, 
          Blank[]], 
         Pattern[$CellContext`xx, 
          Blank[]]] := 
       Block[{$CellContext`x, $CellContext`y}, $CellContext`x = 
          0.1 ($CellContext`xx - 1); $CellContext`y = 
          0.1 (1 - $CellContext`yy); {
           
           Line[{{$CellContext`x, $CellContext`y}, {$CellContext`x + 
              0.025, $CellContext`y}}], 
           
           Line[{{$CellContext`x + 0.075, $CellContext`y}, {$CellContext`x + 
              0.1, $CellContext`y}}], 
           
           Line[{{$CellContext`x + 0.025, $CellContext`y - 
              0.025}, {$CellContext`x + 0.025, $CellContext`y + 
              0.025}, {$CellContext`x + 0.075, $CellContext`y + 
              0.025}, {$CellContext`x + 0.075, $CellContext`y - 
              0.025}, {$CellContext`x + 0.025, $CellContext`y - 0.025}}], 
           Text[
            Style[
            "H", 16, Bold], {$CellContext`x + 0.05, $CellContext`y - 
             0.003}]}], $CellContext`gateX[
         Pattern[$CellContext`yy, 
          Blank[]], 
         Pattern[$CellContext`xx, 
          Blank[]]] := 
       Block[{$CellContext`x, $CellContext`y}, $CellContext`x = 
          0.1 ($CellContext`xx - 1); $CellContext`y = 
          0.1 (1 - $CellContext`yy); {
           
           Line[{{$CellContext`x, $CellContext`y}, {$CellContext`x + 
              0.025, $CellContext`y}}], 
           
           Line[{{$CellContext`x + 0.075, $CellContext`y}, {$CellContext`x + 
              0.1, $CellContext`y}}], 
           
           Line[{{$CellContext`x + 0.025, $CellContext`y - 
              0.025}, {$CellContext`x + 0.025, $CellContext`y + 
              0.025}, {$CellContext`x + 0.075, $CellContext`y + 
              0.025}, {$CellContext`x + 0.075, $CellContext`y - 
              0.025}, {$CellContext`x + 0.025, $CellContext`y - 0.025}}], 
           Text[
            Style[
            "X", 16, Bold], {$CellContext`x + 0.05, $CellContext`y - 
             0.003}]}], $CellContext`gateZ[
         Pattern[$CellContext`yy, 
          Blank[]], 
         Pattern[$CellContext`xx, 
          Blank[]]] := 
       Block[{$CellContext`x, $CellContext`y}, $CellContext`x = 
          0.1 ($CellContext`xx - 1); $CellContext`y = 
          0.1 (1 - $CellContext`yy); {
           
           Line[{{$CellContext`x, $CellContext`y}, {$CellContext`x + 
              0.025, $CellContext`y}}], 
           
           Line[{{$CellContext`x + 0.075, $CellContext`y}, {$CellContext`x + 
              0.1, $CellContext`y}}], 
           
           Line[{{$CellContext`x + 0.025, $CellContext`y - 
              0.025}, {$CellContext`x + 0.025, $CellContext`y + 
              0.025}, {$CellContext`x + 0.075, $CellContext`y + 
              0.025}, {$CellContext`x + 0.075, $CellContext`y - 
              0.025}, {$CellContext`x + 0.025, $CellContext`y - 0.025}}], 
           Text[
            Style[
            "Z", 16, Bold], {$CellContext`x + 0.05, $CellContext`y - 
             0.003}]}], $CellContext`lineVert[
         Pattern[$CellContext`yy1, 
          Blank[]], 
         Pattern[$CellContext`yy2, 
          Blank[]], 
         Pattern[$CellContext`xx, 
          Blank[]]] := 
       Block[{$CellContext`x, $CellContext`y1, $CellContext`y2}, \
$CellContext`x = 0.1 $CellContext`xx - 0.05; $CellContext`y1 = 
          0.1 (1 - $CellContext`yy1); $CellContext`y2 = 
          0.1 (1 - $CellContext`yy2); {
           
           Line[{{$CellContext`x, $CellContext`y1}, {$CellContext`x, \
$CellContext`y2}}]}], Attributes[PlotRange] = {ReadProtected}}; 
     Typeset`initDone$$ = True),
    SynchronousInitialization->True,
    UnsavedVariables:>{Typeset`initDone$$},
    UntrackedVariables:>{Typeset`size$$}], "Manipulate",
   Deployed->True,
   StripOnInput->False],
  Manipulate`InterpretManipulate[1]]], "Output",ExpressionUUID->"a47ab6b3-\
ea05-4b90-b08d-f339fe8ee0fe"]

