## Taller 29 de agosto de 2022

Hacer un programa en Visual Basic, que permita registra los datos ingresados por el cliente y mostrarlos en un listado.

´´´´

    Sub registrar()

    cont = 3
        
        For i = 1 To 10
            nom = InputBox("Ingrese su nombre:")
            datos.Cells(cont, 2) = nom
            cont = cont + 1
        Next i
        
    End Sub


´´´´
