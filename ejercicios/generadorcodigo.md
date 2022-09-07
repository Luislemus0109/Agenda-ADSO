## Taller 2 de septiembre

~~~

    Sub ultimador()


        For a = 2 To 21
            nom = lista.Cells(a, 1)
            año = Str(lista.Cells(a, 2))
            mun = lista.Cells(a, 3)
            ultmun = Len(mun) - 1
            lista.Cells(a, 4) = Mid(año, 1, 3) & Mid(mun, ultmun, 2) & Mid(nom, 1, 2)
        Next a
        
    End Sub

    Sub borrar()
        For b = 2 To 21
        lista.Cells(b, 4).ClearContents
        Next b
        
    End Sub

~~~
