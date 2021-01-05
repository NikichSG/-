Function Nikich$(X&)
    Dim n1&, n2&, A(), j&, U&, Y&
    j = 0
    Select Case X
        Case 0 To 3, 5, 7
        Nikich = "Prime"
        Exit Function
    End Select
    Do While X Mod 2 = 0
        ReDim Preserve A(j)
        A(j) = 2
        X = X / 2
        j = j + 1
    Loop
    Do While X Mod 3 = 0
        ReDim Preserve A(j)
        A(j) = 3
        X = X / 3
        j = j + 1
    Loop
    U = X \ 4
    n1 = 5
    n2 = 7
    Do While n1 < U
        Y = X
        Do While X Mod n1 = 0
            ReDim Preserve A(j)
            A(j) = n1
            X = X / n1
            j = j + 1
        Loop
        Do While X Mod n2 = 0
            ReDim Preserve A(j)
            A(j) = n2
            X = X / n2
            j = j + 1
        Loop
        U = X \ n2
        n1 = n1 + 6
        n2 = n1 + 2
    Loop
    If j = 0 Then
        Nikich = "Prime"
    Else
        If X <> 1 Then
            ReDim Preserve A(j)
            A(j) = X
        End If
        Nikich = Join(A, "*")
    End If
End Function

//MCH_F
//За основу взял алгоритм Аткина
