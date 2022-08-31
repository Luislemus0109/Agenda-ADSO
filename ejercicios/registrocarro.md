## Taller 29 de agosto de 2022

Hacer un programa en Visual Basic, que permita registra los datos ingresados por el cliente y mostrarlos en otra hoja.

´´´´

    Sub save()
        fila = datos.Cells(1, 8)
        datos.Cells(fila, 2) = registro.Cells(5, 4)
        datos.Cells(fila, 3) = registro.Cells(7, 4)
        datos.Cells(fila, 4) = registro.Cells(9, 4)
        datos.Cells(fila, 5) = registro.Cells(11, 4)
        MsgBox "Datos Guardados"
        datos.Cells(1, 8) = fila + 1
        
    End Sub

    Sub clear()
        registro.Cells(5, 4).ClearContents
        registro.Cells(7, 4).ClearContents
        registro.Cells(9, 4).ClearContents
        registro.Cells(11, 4).ClearContents
    End Sub



´´´´
