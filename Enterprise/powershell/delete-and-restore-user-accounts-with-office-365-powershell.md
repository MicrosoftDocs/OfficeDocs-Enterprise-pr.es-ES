---
title: Eliminar cuentas de usuario con PowerShell de Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 01/03/2019
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- PowerShell
- Ent_Office_Other
- O365ITProTrain
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: Obtenga información sobre cómo usar PowerShell de Office 365 para eliminar cuentas de usuario de Office 365.
ms.openlocfilehash: 0b882f3bdf9070c83baffaca65a7c80c98cd4ed9
ms.sourcegitcommit: 15db0f1e5f8036e46063662d7df22387906f8ba7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/04/2019
ms.locfileid: "27546471"
---
# <a name="delete-user-accounts-with-office-365-powershell"></a><span data-ttu-id="5e9ac-103">Eliminar cuentas de usuario con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="5e9ac-103">Delete and restore user accounts with Office 365 PowerShell</span></span>

<span data-ttu-id="5e9ac-104">**Resumen**: Obtenga información sobre cómo usar PowerShell de Office 365 para eliminar cuentas de usuario de Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e9ac-104">**Summary:**  Learn how to use Office 365 PowerShell to delete and restore Office 365 user accounts.</span></span>
  
<span data-ttu-id="5e9ac-105">Puede usar PowerShell de Office 365 para eliminar una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="5e9ac-105">You can use the Office 365 admin center to create a new user account.</span></span>

   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="5e9ac-106">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="5e9ac-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="5e9ac-107">Primero, [conéctese a su inquilino de Office 365](connect-to-office-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="5e9ac-107">First, [connect to your Office 365 tenant](connect-to-office-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="5e9ac-108">Después de haberse conectado, use la sintaxis siguiente para eliminar una cuenta de usuario individual:</span><span class="sxs-lookup"><span data-stu-id="5e9ac-108">After you have connected, use the following syntax to remove an individual user account:</span></span>
  
```
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="5e9ac-109">Este ejemplo elimina la cuenta de usuario fabricec@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5e9ac-109">This example removes the user account fabricec@litwareinc.com.</span></span>
  
```
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="5e9ac-110">El parámetro **ObjectID** en el cmdlet **Remove-AzureAD** acepta tanto el nombre de inicio de sesión en la cuenta, también conocido como nombre principal de usuario, o la ID de objeto de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="5e9ac-110">The **-ObjectID** parameter in the **Remove-AzureAD** cmdlet accepts either the account name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="5e9ac-111">Para mostrar el nombre de cuenta según el nombre de usuario, use los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5e9ac-111">To display the account name based on the user's name, use the following commands:</span></span>
  
```
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="5e9ac-112">Este ejemplo muestra el nombre de cuenta para el usuario llamado Caleb Sills.</span><span class="sxs-lookup"><span data-stu-id="5e9ac-112">This example displays the account name for the user named Caleb Sills.</span></span>
  
```
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="5e9ac-113">Para eliminar una cuenta según el nombre para mostrar del usuario, use los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5e9ac-113">To remove an account based on the user's name, use the following commands:</span></span>
  
```
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="5e9ac-114">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e9ac-114">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

<span data-ttu-id="5e9ac-p101">Al eliminar una cuenta de usuario con el Módulo Microsoft Azure Active Directory para Windows PowerShell, esta no se elimina de forma permanente. Puede restaurar la cuenta de usuario eliminada durante los siguientes 30 días.</span><span class="sxs-lookup"><span data-stu-id="5e9ac-p101">When you delete a user account with the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted. You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="5e9ac-117">Primero, [conéctese a su inquilino de Office 365](connect-to-office-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5e9ac-117">First, [connect to your Office 365 tenant](connect-to-office-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


<span data-ttu-id="5e9ac-118">Para eliminar una cuenta de usuario, utilice la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="5e9ac-118">To delete a user account, use the following syntax:</span></span>
  
```
Remove-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="5e9ac-119">Este ejemplo elimina la cuenta de usuario BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5e9ac-119">This example deletes the user account BelindaN@litwareinc.com.</span></span>
  
```
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="5e9ac-120">Para restaurar una cuenta de usuario eliminada dentro del periodo de gracia de 30 días, utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e9ac-120">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="5e9ac-121">Este ejemplo restaura la cuenta eliminada BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5e9ac-121">This example restores the deleted account BelindaN@litwareinc.com.</span></span>
  
```
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

 <span data-ttu-id="5e9ac-122">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="5e9ac-122">**Notes:**</span></span>
  
- <span data-ttu-id="5e9ac-123">Para ver la lista de usuarios eliminados que pueden restaurarse, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="5e9ac-123">To see the list of deleted users that can be restored, run the following command:</span></span>
    
  ```
  Get-MsolUser -All -ReturnDeletedUsers
  ```

- <span data-ttu-id="5e9ac-124">Si otra cuenta usa el nombre principal de usuario original de la cuenta de usuario, use el parámetro _NewUserPrincipalName_ en vez de _UserPrincipalName_ para especificar un nombre principal de usuario al restaurar la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="5e9ac-124">If the user account's original user principal name is used by another account, use the  _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="5e9ac-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e9ac-125">See also</span></span>

[<span data-ttu-id="5e9ac-126">Administrar licencias y cuentas de usuario con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="5e9ac-126">Manage user accounts and licenses with Office 365 PowerShell</span></span>](manage-user-accounts-and-licenses-with-office-365-powershell.md)
  
[<span data-ttu-id="5e9ac-127">Administrar Office 365 con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="5e9ac-127">Manage Office 365 with Office 365 PowerShell</span></span>](manage-office-365-with-office-365-powershell.md)
  
[<span data-ttu-id="5e9ac-128">Introducción a PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="5e9ac-128">Getting started with Office 365 PowerShell</span></span>](getting-started-with-office-365-powershell.md)

