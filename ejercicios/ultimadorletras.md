## Taller 02 de septiembre de 2022

Hacer un programa en Visual Basic, que permita separar las dos ultimas letras del nombre

´´´´

    Sub ultimador()


        For a = 2 To 21
            nom = lista.Cells(a, 1)
            ult = Len(nom) - 1
            lista.Cells(a, 2) = Mid(nom, ult, 2)
        Next a
        
    End Sub


´´´´