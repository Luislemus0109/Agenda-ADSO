## Taller 26 de agosto de 2022

Hacer un programa en Visual Basic, que permita calcular el valor a pagar por impuesto anual de una empresa.

´´´´
    
    Sub impuesto_empresa()

    ing_anual = InputBox("Ingrese su ingreso anual: ")

    If ing_anual >= 0 And ing_anual < 1000 Then
        MsgBox "No paga impuesto"
    Else
        If ing_anual >= 1001 And ing_anual < 10000 Then
            aum_imp = ing_anual * 0.05
            MsgBox "Impuesto a pagar: " & aum_imp
        Else
            If ing_anual >= 10001 And ing_anual < 100000 Then
                aum_imp = ing_anual * 0.1
                MsgBox "Impuesto a pagar: " & aum_imp
            Else
                If ing_anual >= 100001 And ing_anual < 1000000 Then
                    aum_imp = ing_anual * 0.15
                    MsgBox "Impuesto a pagar: " & aum_imp
                Else
                    If ing_anual >= 1000001 And ing_anual < 10000000 Then
                        aum_imp = ing_anual * 0.2
                        MsgBox "Impuesto a pagar: " & aum_imp
                    Else
                        If ing_anual > 10000001 Then
                            aum_imp = ing_anual * 0.25
                            MsgBox "Impuesto a pagar: " & aum_imp
                        Else
                            MsgBox "No se puede"    
                        End If
                         
                    End If
                        
                End If
            
            End If

        End If

    End If

    End Sub
´´´´
