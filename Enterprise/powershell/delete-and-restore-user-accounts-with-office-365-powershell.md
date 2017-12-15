---
title: Eliminar y restaurar cuentas de usuario con PowerShell de Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- DecEntMigration
- PowerShell
- Ent_Office_Other
- O365ITProTrain
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: Aprenda a utilizar Office 365 PowerShell para eliminar y restaurar cuentas de usuario de Office 365.
ms.openlocfilehash: 8404395ea9594cea1a2e772cecbeb011756b7754
ms.sourcegitcommit: d31cf57295e8f3d798ab971d405baf3bd3eb7a45
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="delete-and-restore-user-accounts-with-office-365-powershell"></a><span data-ttu-id="5e8d2-103">Eliminar y restaurar cuentas de usuario con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="5e8d2-103">Delete and restore user accounts with Office 365 PowerShell</span></span>

<span data-ttu-id="5e8d2-104">**Resumen:**  Aprenda a utilizar Office 365 PowerShell para eliminar y restaurar cuentas de usuario de Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e8d2-104">**Summary:**  Learn how to use Office 365 PowerShell to delete and restore Office 365 user accounts.</span></span>
  
<span data-ttu-id="5e8d2-p101">Al utilizar PowerShell de Office 365 para eliminar una cuenta de usuario, esta no se elimina de forma permanente. Puede restaurar la cuenta de usuario eliminada durante los siguientes 30 días.</span><span class="sxs-lookup"><span data-stu-id="5e8d2-p101">When you use Office 365 PowerShell to delete a user account, the account isn't permanently deleted. You can restore the deleted user account within 30 days.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="5e8d2-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="5e8d2-107">Before you begin</span></span>

- <span data-ttu-id="5e8d2-p102">Los procedimientos de este tema requieren conectarse a PowerShell de Office 365. Para obtener instrucciones, vea [Conectarse a PowerShell de Office 365](connect-to-office-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5e8d2-p102">The procedures in this topic require you to connect to Office 365 PowerShell. For instructions, see [Connect to Office 365 PowerShell](connect-to-office-365-powershell.md).</span></span>
    
- <span data-ttu-id="5e8d2-110">Si utiliza el cmdlet **Get-MsolUser** sin utilizar el _-todos los_ parámetro, se devuelven sólo las primeras 500 cuentas.</span><span class="sxs-lookup"><span data-stu-id="5e8d2-110">If you use the **Get-MsolUser** cmdlet without using the _-All_ parameter, only the first 500 accounts are returned.</span></span>
    
## <a name="use-office-365-powershell-to-block-access-to-individual-user-accounts"></a><span data-ttu-id="5e8d2-111">Usar PowerShell de Office 365 para bloquear el acceso a cuentas de usuario individuales</span><span class="sxs-lookup"><span data-stu-id="5e8d2-111">Use Office 365 PowerShell to block access to individual user accounts</span></span>
<span data-ttu-id="5e8d2-112"><a name="ShortVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="5e8d2-112"><a name="ShortVersion"> </a></span></span>

<span data-ttu-id="5e8d2-113">Para eliminar una cuenta de usuario, utilice la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="5e8d2-113">To delete a user account, use the following syntax:</span></span>
  
```
Remove-MsolUser -UserPrincipalName <Account>
```

<span data-ttu-id="5e8d2-114">Este ejemplo elimina la cuenta de usuario BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5e8d2-114">This example deletes the user account BelindaN@litwareinc.com.</span></span>
  
```
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="5e8d2-115">Para restaurar una cuenta de usuario eliminada dentro del periodo de gracia de 30 días, utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e8d2-115">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```
Restore-MsolUser -UserPrincipalName <Account>
```

<span data-ttu-id="5e8d2-116">Este ejemplo restaura la cuenta eliminada BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5e8d2-116">This example restores the deleted account BelindaN@litwareinc.com.</span></span>
  
```
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

 <span data-ttu-id="5e8d2-117">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="5e8d2-117">**Notes:**</span></span>
  
- <span data-ttu-id="5e8d2-118">Para ver la lista de usuarios eliminados que pueden restaurarse, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="5e8d2-118">To see the list of deleted users that can be restored, run the following command:</span></span>
    
  ```
  Get-MsolUser -All -ReturnDeletedUsers
  ```

- <span data-ttu-id="5e8d2-119">Si otra cuenta usa el nombre principal de usuario original de la cuenta de usuario, use el parámetro  _NewUserPrincipalName_ en vez de _UserPrincipalName_ para especificar un nombre principal de usuario al restaurar la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="5e8d2-119">If the user account's original user principal name is used by another account, use the  _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>
    
## <a name="use-the-azure-active-directory-v2-powershell-module-to-remove-a-user-account"></a><span data-ttu-id="5e8d2-120">Usar el módulo de PowerShell Azure Active Directory V2 para eliminar una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="5e8d2-120">Use the Azure Active Directory V2 PowerShell module to remove a user account</span></span>
<span data-ttu-id="5e8d2-121"><a name="ShortVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="5e8d2-121"><a name="ShortVersion"> </a></span></span>

<span data-ttu-id="5e8d2-p103">Para usar el cmdlet **Remove-AzureADUser** desde el módulo de Active Directory V2 PowerShell de Azure, debe conectarse primero a su suscripción. Para las instrucciones, vea [Conectar con el módulo de Active Directory V2 PowerShell de Azure](https://go.microsoft.com/fwlink/?linkid=842218).</span><span class="sxs-lookup"><span data-stu-id="5e8d2-p103">To use the **Remove-AzureADUser** cmdlet from the Azure Active Directory V2 PowerShell module, you must first connect to your subscription. For the instructions, see [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218).</span></span>
  
<span data-ttu-id="5e8d2-124">Después de haberse conectado, use la sintaxis siguiente para eliminar una cuenta de usuario individual:</span><span class="sxs-lookup"><span data-stu-id="5e8d2-124">After you have connected, use the following syntax to remove an individual user account:</span></span>
  
```
Remove-AzureADUser -ObjectID <Account>
```

<span data-ttu-id="5e8d2-125">Este ejemplo elimina la cuenta de usuario fabricec@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5e8d2-125">This example removes the user account fabricec@litwareinc.com.</span></span>
  
```
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="5e8d2-126">El parámetro **ObjectID** en el cmdlet **Remove-AzureAD** acepta tanto el nombre de cuenta, también conocido como nombre principal de usuario, o la ID de objeto de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="5e8d2-126">The **-ObjectID** parameter in the **Remove-AzureAD** cmdlet accepts either the account name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="5e8d2-127">Para mostrar el nombre de cuenta según el nombre de usuario, use los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5e8d2-127">To display the account name based on the user's name, use the following commands:</span></span>
  
```
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="5e8d2-128">Este ejemplo muestra el nombre de cuenta para el usuario llamado Caleb Sills.</span><span class="sxs-lookup"><span data-stu-id="5e8d2-128">This example displays the account name for the user named Caleb Sills.</span></span>
  
```
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="5e8d2-129">Para eliminar una cuenta según el nombre de usuario, use los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5e8d2-129">To remove an account based on the user's name, use the following commands:</span></span>
  
```
$userName="<User name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="see-also"></a><span data-ttu-id="5e8d2-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e8d2-130">See also</span></span>
<span data-ttu-id="5e8d2-131"><a name="SeeAlso"> </a></span><span class="sxs-lookup"><span data-stu-id="5e8d2-131"><a name="SeeAlso"> </a></span></span>

<span data-ttu-id="5e8d2-132">Consulte estos temas adicionales acerca de cómo administrar usuarios con Office 365 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5e8d2-132">See these additional topics about managing users with Office 365 PowerShell:</span></span>
  
- [<span data-ttu-id="5e8d2-133">Crear cuentas de usuario con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="5e8d2-133">Create user accounts with Office 365 PowerShell</span></span>](create-user-accounts-with-office-365-powershell.md)
    
- [<span data-ttu-id="5e8d2-134">Bloquear cuentas de usuario con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="5e8d2-134">Block user accounts with Office 365 PowerShell</span></span>](block-user-accounts-with-office-365-powershell.md)
    
- [<span data-ttu-id="5e8d2-135">Asignar licencias a cuentas de usuario con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="5e8d2-135">Assign licenses to user accounts with Office 365 PowerShell</span></span>](assign-licenses-to-user-accounts-with-office-365-powershell.md)
    
- [<span data-ttu-id="5e8d2-136">Eliminar licencias de cuentas de usuario con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="5e8d2-136">Remove licenses from user accounts with Office 365 PowerShell</span></span>](remove-licenses-from-user-accounts-with-office-365-powershell.md)
    
<span data-ttu-id="5e8d2-137">Para obtener más información sobre los cmdlets que se usan en estos procedimientos, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="5e8d2-137">For more information about the cmdlets that are used in these procedures, see the following topics:</span></span>
  
- [<span data-ttu-id="5e8d2-138">Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="5e8d2-138">Get-MsolUser</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=691543)
    
- [<span data-ttu-id="5e8d2-139">Remove-MsolUser</span><span class="sxs-lookup"><span data-stu-id="5e8d2-139">Remove-MsolUser</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=691636)
    
- [<span data-ttu-id="5e8d2-140">Restore-MsolUser</span><span class="sxs-lookup"><span data-stu-id="5e8d2-140">Restore-MsolUser</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=691637)
    
- [<span data-ttu-id="5e8d2-141">New-AzureADUsuario</span><span class="sxs-lookup"><span data-stu-id="5e8d2-141">New-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/new-azureaduser?view=azureadps-2.0)
    
