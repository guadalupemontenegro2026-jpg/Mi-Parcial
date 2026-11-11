for ($i = 1; $i -le 3; $i++) {
    
    $horaActual = Get-Date
    Write-Host "Intento $i ($horaActual)"

    Test-Connection -ComputerName 8.8.8.8 -Count 1

    if ($i % 2 -eq 0) {
        Write-Host "Vuelta par: conexion estable."
    } else {
        Write-Host "Vuelta impar: enviando paquete."
    }

    Start-Sleep -Seconds 1
}

Write-Host "Monitoreo finalizado con exito."
Read-Host "Presione enter para salir"