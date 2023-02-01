---
layout: post
title: Cómo limpiar Windows de bloatware
teaser: /assets/images/teaser/miniatura-windows.jpg
categories: blog
---
Hoy os traigo un post rápido sobre cómo quitar las aplicaciones innecesarias que nos instala Windows 10 por defecto, que por suerte se pueden borrar facilmente.
Usando powershell

Ve introduciendo uno a uno estos comandos en la aplicación «Windows Powershell». En teoría los puedes meter todos del tirón, pero yo que tu iría poco a poco, seleccionando qué quieres borrar, y qué no.
```
Get-AppxPackage -name "Microsoft.ZuneMusic" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.Music.Preview" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.XboxGameCallableUI" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.XboxIdentityProvider" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.BingTravel" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.BingHealthAndFitness" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.BingFoodAndDrink" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.People" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.BingFinance" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.3DBuilder" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.BingNews" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.XboxApp" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.BingSports" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.WindowsCamera" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.Getstarted" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.Office.OneNote" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.WindowsMaps" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.MicrosoftSolitaireCollection" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.MicrosoftOfficeHub" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.BingWeather" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.BioEnrollment" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.Windows.Photos" | Remove-AppxPackage
Get-AppxPackage -name "Microsoft.WindowsPhone" | Remove-AppxPackage
Get-AppxPackage -Name king.com.CandyCrushSaga
```