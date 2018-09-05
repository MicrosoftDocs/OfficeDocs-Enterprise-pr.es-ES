---
title: Usar los cmdlets de PowerShell de implementación centralizada para administrar complementos
ms.author: twerner
author: twernermsft
manager: scotv
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 94f4e86d-b8e5-42dd-b558-e6092f830ec9
description: Use los cmdlets de PowerShell de implementación centralizado que le ayudarán a implementar y administrar complementos de Office para su organización de Office 365.
ms.openlocfilehash: f15bd1048d9240a125a1ae8245c773d83c6c935d
ms.sourcegitcommit: 69d60723e611f3c973a6d6779722aa9da77f647f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22542727"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a><span data-ttu-id="50ea5-103">Usar los cmdlets de PowerShell de implementación centralizada para administrar complementos</span><span class="sxs-lookup"><span data-stu-id="50ea5-103">Use the Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>

<span data-ttu-id="50ea5-p101">Como un administrador de Office 365, puede implementar los complementos de Office a los usuarios a través de la implementación centralizada de la característica (vea [Administrar la implementación de complementos de Office 365 en el centro de administración de Office 365](https://support.office.com/article/737e8c86-be63-44d7-bf02-492fa7cd9c3f)). Además de la implementación de complementos de Office mediante el centro de administración de Office 365, también puede usar Microsoft PowerShell. [Descargar](https://go.microsoft.com/fwlink/p/?linkid=850850) los cmdlets de PowerShell de implementación centralizada desde Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="50ea5-p101">As an Office 365 admin, you can deploy Office add-ins to users via the Centralized Deployment feature (see [Manage deployment of Office 365 add-ins in the Office 365 admin center](https://support.office.com/article/737e8c86-be63-44d7-bf02-492fa7cd9c3f)). In addition to deploying Office add-ins via the Office 365 admin center, you can also use Microsoft PowerShell. [Download](https://go.microsoft.com/fwlink/p/?linkid=850850) the Centralized Deployment PowerShell cmdlets from the Microsoft Download Center.</span></span> 
  
## <a name="what-do-you-want-to-do"></a><span data-ttu-id="50ea5-107">¿Qué desea hacer?</span><span class="sxs-lookup"><span data-stu-id="50ea5-107">What do you want to do?</span></span>

[<span data-ttu-id="50ea5-108">Conectarse con sus credenciales de administrador</span><span class="sxs-lookup"><span data-stu-id="50ea5-108">Connect using your admin credentials</span></span>](use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md#BKMK_Connect)
  
[<span data-ttu-id="50ea5-109">Cargar un complemento de manifiesto</span><span class="sxs-lookup"><span data-stu-id="50ea5-109">Upload an add-in manifest</span></span>](use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md#BKMK_UploadManifest)
  
[<span data-ttu-id="50ea5-110">Cargar un complemento de la tienda Office</span><span class="sxs-lookup"><span data-stu-id="50ea5-110">Upload an add-in from the Office Store</span></span>](use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md#BKMK_UploadAddin)
  
[<span data-ttu-id="50ea5-111">Obtener detalles de un complemento</span><span class="sxs-lookup"><span data-stu-id="50ea5-111">Get details of an add-in</span></span>](use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md#BKMK_GetDetails)
  
[<span data-ttu-id="50ea5-112">Activar o desactivar un complemento</span><span class="sxs-lookup"><span data-stu-id="50ea5-112">Turn on or turn off an add-in</span></span>](use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md#BKMK_TurnOnOff)
  
[<span data-ttu-id="50ea5-113">Agregar o quitar usuarios de un complemento</span><span class="sxs-lookup"><span data-stu-id="50ea5-113">Add or remove users from an add-in</span></span>](use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md#BKMK_AddRemove)
  
[<span data-ttu-id="50ea5-114">Actualizar un complemento</span><span class="sxs-lookup"><span data-stu-id="50ea5-114">Update an add-in</span></span>](use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md#BKMK_UpdateAddin)
  
[<span data-ttu-id="50ea5-115">Eliminación de un complemento</span><span class="sxs-lookup"><span data-stu-id="50ea5-115">Delete an add-in</span></span>](use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md#BKMK_Delete)
  
[<span data-ttu-id="50ea5-116">Obtener ayuda detallada para cada cmdlet</span><span class="sxs-lookup"><span data-stu-id="50ea5-116">Get detailed help for each cmdlet</span></span>](use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md#BKMK_GetHelp)
  
## <a name="connect-using-your-admin-credentials"></a><span data-ttu-id="50ea5-117">Conectarse con sus credenciales de administrador</span><span class="sxs-lookup"><span data-stu-id="50ea5-117">Connect using your admin credentials</span></span>
<span data-ttu-id="50ea5-118"><a name="BKMK_Connect"> </a></span><span class="sxs-lookup"><span data-stu-id="50ea5-118"></span></span>

<span data-ttu-id="50ea5-119">Antes de que puede usar los cmdlets de implementación centralizado, tiene que iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="50ea5-119">Before you can use the Centralized Deployment cmdlets, you need to sign in.</span></span>
  
1. <span data-ttu-id="50ea5-120">Inicie PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50ea5-120">Start PowerShell.</span></span>
    
2. <span data-ttu-id="50ea5-p102">Conectarse a PowerShell con sus credenciales de administrador de empresa. Ejecute el siguiente cmdlet.</span><span class="sxs-lookup"><span data-stu-id="50ea5-p102">Connect to PowerShell by using your company admin credentials. Run the following cmdlet.</span></span>
    
  ```
  Connect-OrganizationAddInService
  ```

3. <span data-ttu-id="50ea5-p103">En la página **Especificar credenciales** , escriba sus credenciales de administrador global de Office 365. Como alternativa, puede escribir sus credenciales directamente en el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="50ea5-p103">In the **Enter Credentials** page, enter your Office 365 global admin credentials. Alternately, you can enter your credentials directly into the cmdlet.</span></span> 
    
    <span data-ttu-id="50ea5-125">Ejecute el siguiente cmdlet que especifica la compañía credenciales de administrador como un objeto PSCredential.</span><span class="sxs-lookup"><span data-stu-id="50ea5-125">Run the following cmdlet specifying your company admin credentials as a PSCredential object.</span></span>
    
  ```
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> <span data-ttu-id="50ea5-126">Para obtener más información acerca del uso de PowerShell, vea [Connect to Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848585).</span><span class="sxs-lookup"><span data-stu-id="50ea5-126">For more information about using PowerShell, see [Connect to Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848585).</span></span> 
  
## <a name="upload-an-add-in-manifest"></a><span data-ttu-id="50ea5-127">Cargar un complemento de manifiesto</span><span class="sxs-lookup"><span data-stu-id="50ea5-127">Upload an add-in manifest</span></span>
<span data-ttu-id="50ea5-128"><a name="BKMK_UploadManifest"> </a></span><span class="sxs-lookup"><span data-stu-id="50ea5-128"></span></span>

<span data-ttu-id="50ea5-p104">Ejecute el cmdlet New-OrganizationAdd de entrada para cargar un manifiesto de complemento desde una ruta de acceso, que puede ser una ubicación de archivo o la dirección URL. En el ejemplo siguiente se muestra una ubicación de archivos para el valor del parámetro _ManifestPath_ .</span><span class="sxs-lookup"><span data-stu-id="50ea5-p104">Run the New-OrganizationAdd-In cmdlet to upload an add-in manifest from a path, which can be either a file location or URL. The following example shows a file location for the value of the  _ManifestPath_ parameter.</span></span> 
  
```
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

<span data-ttu-id="50ea5-p105">También puede ejecutar el cmdlet New-OrganizationAdd de entrada para cargar un complemento y asignar a usuarios o grupos de directamente mediante el parámetro _Members_ , tal como se muestra en el siguiente ejemplo. Separe las direcciones de correo electrónico de miembros con una coma.</span><span class="sxs-lookup"><span data-stu-id="50ea5-p105">You can also run the New-OrganizationAdd-In cmdlet to upload an add-in and assign it to users or groups directly by using the  _Members_ parameter, as shown in the following example. Separate the email addresses of members with a comma.</span></span> 
  
```
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a><span data-ttu-id="50ea5-133">Cargar un complemento de la tienda Office</span><span class="sxs-lookup"><span data-stu-id="50ea5-133">Upload an add-in from the Office Store</span></span>
<span data-ttu-id="50ea5-134"><a name="BKMK_UploadAddin"> </a></span><span class="sxs-lookup"><span data-stu-id="50ea5-134"></span></span>

<span data-ttu-id="50ea5-135">Ejecute el cmdlet New-OrganizationAddIn para cargar un manifiesto de la tienda Office.</span><span class="sxs-lookup"><span data-stu-id="50ea5-135">Run the New-OrganizationAddIn cmdlet to upload a manifest from the Office Store.</span></span>
  
<span data-ttu-id="50ea5-136">En el siguiente ejemplo, el cmdlet New-OrganizationAddIn especifica el idtema para un complemento para un mercado de ubicación y el contenido de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="50ea5-136">In the following example, the New-OrganizationAddIn cmdlet specifies the AssetId for an add-in for a United States location and content market.</span></span>
  
```
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

<span data-ttu-id="50ea5-p106">Para determinar el valor para el parámetro _idtema_ , puede copiarlo desde la dirección URL de la tienda de Office página Web para el complemento AssetIds siempre comienzan con "WA" seguido de un número. Por ejemplo, en el ejemplo anterior, el origen para el valor idtema de WA104099688 es la dirección URL de página Web de almacén de Office para el complemento: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688).</span><span class="sxs-lookup"><span data-stu-id="50ea5-p106">To determine the value for the  _AssetId_ parameter, you can copy it from the URL of the Office Store webpage for the add-in. AssetIds always begin with "WA" followed by a number. For example, in the previous example, the source for the AssetId value of WA104099688 is the Office Store webpage URL for the add-in: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688).</span></span>
  
<span data-ttu-id="50ea5-p107">Los valores para el parámetro de _Configuración regional_ y el parámetro _ContentMarket_ son idénticos e indican el país o región que está intentando instalar el complemento de. El formato es en-US, fr-FR. y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="50ea5-p107">The values for the  _Locale_ parameter and the  _ContentMarket_ parameter are identical and indicate the country/region you're trying to install the add-in from. The format is en-US, fr-FR. and so forth.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="50ea5-143">Complementos cargados desde el almacén de Office se actualizarán automáticamente dentro de unos días de la última actualización que están disponibles en la tienda de Office.</span><span class="sxs-lookup"><span data-stu-id="50ea5-143">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="get-details-of-an-add-in"></a><span data-ttu-id="50ea5-144">Obtener detalles de un complemento</span><span class="sxs-lookup"><span data-stu-id="50ea5-144">Get details of an add-in</span></span>
<span data-ttu-id="50ea5-145"><a name="BKMK_GetDetails"> </a></span><span class="sxs-lookup"><span data-stu-id="50ea5-145"></span></span>

<span data-ttu-id="50ea5-146">Ejecute el cmdlet Get-OrganizationAddIn tal y como se muestra a continuación obtener detalles de todos los complementos cargados en el inquilino, incluido identificador del producto. de un complemento</span><span class="sxs-lookup"><span data-stu-id="50ea5-146">Run the Get-OrganizationAddIn cmdlet as shown below to get details of all add-ins uploaded to the tenant, included an add-in's product ID.</span></span>
  
```
Get-OrganizationAddIn
```

<span data-ttu-id="50ea5-147">Ejecute el cmdlet Get-OrganizationAddIn con un valor para el parámetro _ProductId_ especificar el complemento que desea recuperar detalles para.</span><span class="sxs-lookup"><span data-stu-id="50ea5-147">Run the Get-OrganizationAddIn cmdlet with a value for the  _ProductId_ parameter to specify which add-in you want to retrieve details for.</span></span> 
  
```
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<span data-ttu-id="50ea5-148">Para obtener detalles completos de todos los complementos además de los grupos y usuarios asignados, canalizar la salida del cmdlet Get-OrganizationAddIn al cmdlet Format-List, tal como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="50ea5-148">To get full details of all the add-ins plus the assigned users and groups, pipe the output of the Get-OrganizationAddIn cmdlet to the Format-List cmdlet, as shown in the following example.</span></span>
  
```
Get-OrganizationAddIn |Format-List
```

## <a name="turn-on-or-turn-off-an-add-in"></a><span data-ttu-id="50ea5-149">Activar o desactivar un complemento</span><span class="sxs-lookup"><span data-stu-id="50ea5-149">Turn on or turn off an add-in</span></span>
<span data-ttu-id="50ea5-150"><a name="BKMK_TurnOnOff"> </a></span><span class="sxs-lookup"><span data-stu-id="50ea5-150"></span></span>

<span data-ttu-id="50ea5-151">Para desactivar un complemento por lo que los usuarios y grupos que se asignan a esta ya no tendrá acceso, ejecute el cmdlet Set-OrganizationAddIn con el parámetro _ProductId_ y el parámetro _Enabled_ se establece en `$false`, tal como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="50ea5-151">To turn off an add-in so users and groups that are assigned to it will no longer have access, run the Set-OrganizationAddIn cmdlet with the  _ProductId_ parameter and the  _Enabled_ parameter set to  `$false`, as shown in the following example.</span></span>
  
```
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

<span data-ttu-id="50ea5-152">Para volver a activar un complemento, ejecute el cmdlet mismo con el parámetro _Enabled_ se establece en `$true`.</span><span class="sxs-lookup"><span data-stu-id="50ea5-152">To turn an add-in back on, run the same cmdlet with the  _Enabled_ parameter set to  `$true`.</span></span>
  
```
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a><span data-ttu-id="50ea5-153">Agregar o quitar usuarios de un complemento</span><span class="sxs-lookup"><span data-stu-id="50ea5-153">Add or remove users from an add-in</span></span>
<span data-ttu-id="50ea5-154"><a name="BKMK_AddRemove"> </a></span><span class="sxs-lookup"><span data-stu-id="50ea5-154"></span></span>

<span data-ttu-id="50ea5-p108">Para agregar usuarios y grupos a un complemento específico, ejecute el cmdlet Set-OrganizationAddInAssignments con los parámetros de _ProductId_, _Agregar_y _miembros_ . Separe las direcciones de correo electrónico de miembros con una coma.</span><span class="sxs-lookup"><span data-stu-id="50ea5-p108">To add users and groups to a specific add-in, run the Set-OrganizationAddInAssignments cmdlet with the  _ProductId_,  _Add_, and  _Members_ parameters. Separate the email addresses of members with a comma.</span></span> 
  
```
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="50ea5-157">Para quitar usuarios y grupos, ejecute el cmdlet mismo mediante el parámetro _Quitar_ .</span><span class="sxs-lookup"><span data-stu-id="50ea5-157">To remove users and groups, run the same cmdlet using the  _Remove_ parameter.</span></span> 
  
```
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="50ea5-158">Para asignar un complemento a todos los usuarios en el inquilino, ejecute el cmdlet mismo mediante el parámetro _AssignToEveryone_ con el valor establecido `$true`.</span><span class="sxs-lookup"><span data-stu-id="50ea5-158">To assign an add-in to all users on the tenant, run the same cmdlet using the  _AssignToEveryone_ parameter with the value set to  `$true`.</span></span>
  
```
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

<span data-ttu-id="50ea5-159">Para no asignar un complemento para todos los usuarios y volver a los asignado previamente a los usuarios y grupos, puede ejecutar el cmdlet mismo y desactivar el parámetro _AssignToEveryone_ estableciendo su valor en `$false`.</span><span class="sxs-lookup"><span data-stu-id="50ea5-159">To not assign an add-in to everyone and revert to the previously assigned users and groups, you can run the same cmdlet and turn off the  _AssignToEveryone_ parameter by setting its value to  `$false`.</span></span>
  
```
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a><span data-ttu-id="50ea5-160">Actualizar un complemento</span><span class="sxs-lookup"><span data-stu-id="50ea5-160">Update an add-in</span></span>
<span data-ttu-id="50ea5-161"><a name="BKMK_UpdateAddin"> </a></span><span class="sxs-lookup"><span data-stu-id="50ea5-161"></span></span>

<span data-ttu-id="50ea5-162">Para actualizar un complemento de un manifiesto, ejecute el cmdlet Set-OrganizationAddIn con el _ProductId_, _ManifestPath_y parámetros de _Configuración regional_ , como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="50ea5-162">To update an add-in from a manifest, run the Set-OrganizationAddIn cmdlet with the  _ProductId_,  _ManifestPath_, and  _Locale_ parameters, as shown in the following example.</span></span> 
  
```
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> <span data-ttu-id="50ea5-163">Complementos cargados desde el almacén de Office se actualizarán automáticamente dentro de unos días de la última actualización que están disponibles en la tienda de Office.</span><span class="sxs-lookup"><span data-stu-id="50ea5-163">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="delete-an-add-in"></a><span data-ttu-id="50ea5-164">Eliminación de un complemento</span><span class="sxs-lookup"><span data-stu-id="50ea5-164">Delete an add-in</span></span>
<span data-ttu-id="50ea5-165"><a name="BKMK_Delete"> </a></span><span class="sxs-lookup"><span data-stu-id="50ea5-165"></span></span>

<span data-ttu-id="50ea5-166">Para eliminar un complemento, ejecute el cmdlet Remove-OrganizationAddIn con el parámetro _ProductId_ , tal como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="50ea5-166">To delete an add-in, run the Remove-OrganizationAddIn cmdlet with the  _ProductId_ parameter, as shown in the following example.</span></span> 
  
```
Remove-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

## <a name="get-detailed-help-for-each-cmdlet"></a><span data-ttu-id="50ea5-167">Obtener ayuda detallada para cada cmdlet</span><span class="sxs-lookup"><span data-stu-id="50ea5-167">Get detailed help for each cmdlet</span></span>
<span data-ttu-id="50ea5-168"><a name="BKMK_GetHelp"> </a></span><span class="sxs-lookup"><span data-stu-id="50ea5-168"></span></span>

<span data-ttu-id="50ea5-p109">Puede buscar en la ayuda detallada para cada cmdlet mediante el cmdlet Get-help. Por ejemplo, el siguiente cmdlet proporciona información detallada sobre el cmdlet Remove-OrganizationAddIn.</span><span class="sxs-lookup"><span data-stu-id="50ea5-p109">You can look at detailed help for each cmdlet by using the Get-help cmdlet. For example, the following cmdlet provides detailed information about the Remove-OrganizationAddIn cmdlet.</span></span>
  
```
Get-help Remove-OrganizationAddIn -Full
```

