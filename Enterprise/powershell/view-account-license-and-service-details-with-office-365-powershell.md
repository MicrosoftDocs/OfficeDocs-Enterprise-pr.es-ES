---
title: Ver los detalles del servicio y la licencia de la cuenta con PowerShell de Office 365
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
- PowerShell
- Ent_Office_Other
- LIL_Placement
- DecEntMigration
ms.assetid: ace07d8a-15ca-4b89-87f0-abbce809b519
description: "Explica cómo utilizar Office 365 PowerShell para determinar los servicios de Office 365 que se han asignado a los usuarios."
ms.openlocfilehash: 59a6444e0f6618fd837e8eae567661499e795c69
ms.sourcegitcommit: d31cf57295e8f3d798ab971d405baf3bd3eb7a45
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="view-account-license-and-service-details-with-office-365-powershell"></a><span data-ttu-id="e5a8c-103">Ver los detalles del servicio y la licencia de la cuenta con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="e5a8c-103">View account license and service details with Office 365 PowerShell</span></span>

<span data-ttu-id="e5a8c-104">**Resumen:** Explica cómo utilizar Office 365 PowerShell para determinar los servicios de Office 365 que se han asignado a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-104">**Summary:** Explains how to use Office 365 PowerShell to determine the Office 365 services that have been assigned to users.</span></span>
  
<span data-ttu-id="e5a8c-p101">Licencias de Office 365, desde planes de licencias (también llamados SKU o Office 365 planes) proporcionar a los usuarios acceso a los servicios de Office 365 definidos para dichos planes. Sin embargo, un usuario no puede tener acceso a todos los servicios que están disponibles en una licencia que está actualmente asignada a ellos. Puede utilizar Office 365 PowerShell para ver el estado de los servicios en las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p101">In Office 365, licenses from licensing plans (also called SKUs or Office 365 plans) give users access to the Office 365 services that are defined for those plans. However, a user might not have access to all the services that are available in a license that's currently assigned to them. You can use Office 365 PowerShell to view the status of services on user accounts.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="e5a8c-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="e5a8c-108">Before you begin</span></span>
<span data-ttu-id="e5a8c-109"><a name="RTT"> </a></span><span class="sxs-lookup"><span data-stu-id="e5a8c-109"></span></span>

- <span data-ttu-id="e5a8c-p102">Los procedimientos de este tema requieren conectarse a PowerShell de Office 365. Para obtener instrucciones, vea [Conectarse a PowerShell de Office 365](connect-to-office-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p102">The procedures in this topic require you to connect to Office 365 PowerShell. For instructions, see [Connect to Office 365 PowerShell](connect-to-office-365-powershell.md).</span></span>
    
- <span data-ttu-id="e5a8c-112">Utilice los comandos `Get-MsolAccountSku` y `(Get-MsolAccountSku | where {$_.AccountSkuId -eq '<AccountSkuId>'}).ServiceStatus` para encontrar la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-112">Use the commands  `Get-MsolAccountSku` and `(Get-MsolAccountSku | where {$_.AccountSkuId -eq '<AccountSkuId>'}).ServiceStatus` to find the following information:</span></span>
    
  - <span data-ttu-id="e5a8c-113">Los planes de licencias que están disponibles en su organización.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-113">The licensing plans that are available in your organization.</span></span>
    
  - <span data-ttu-id="e5a8c-114">Los servicios que están disponibles en cada plan de licencias y el orden en que muestran (el número de índice).</span><span class="sxs-lookup"><span data-stu-id="e5a8c-114">The services that are available in each licensing plan, and the order in which they are listed (the index number).</span></span>
    
     <span data-ttu-id="e5a8c-115">Para obtener más información acerca de las licencias de los planes, licencias y servicios, consulte [ver licencias y servicios con Office 365 PowerShell](view-licenses-and-services-with-office-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e5a8c-115">For more information about licensing plans, license, and services, see [View licenses and services with Office 365 PowerShell](view-licenses-and-services-with-office-365-powershell.md).</span></span>
    
- <span data-ttu-id="e5a8c-116">Utilice el comando `Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses` para encontrar las licencias que se asignan a un usuario y el orden en que están enumerados (el número de índice).</span><span class="sxs-lookup"><span data-stu-id="e5a8c-116">Use the command  `Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses` to find the licenses that are assigned to a user, and the order in which they are listed (the index number).</span></span>
    
- <span data-ttu-id="e5a8c-117">Si usa el cmdlet **Get-MsolUser** sin usar el parámetro _All_, solo se devuelven las 500 primeras cuentas.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-117">If you use the **Get-MsolUser** cmdlet without using the _All_ parameter, only the first 500 accounts are returned.</span></span>
    
## <a name="the-short-version-instructions-without-explanations"></a><span data-ttu-id="e5a8c-118">Versión corta (instrucciones sin explicaciones)</span><span class="sxs-lookup"><span data-stu-id="e5a8c-118">The short version (instructions without explanations)</span></span>
<span data-ttu-id="e5a8c-119"><a name="ShortVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="e5a8c-119"></span></span>

<span data-ttu-id="e5a8c-120">Para ver todos los servicios de Office 365 PowerShell que un usuario tiene acceso, utilice la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-120">To view all the Office 365 PowerShell services that a user has access to, use the following syntax:</span></span>
  
```
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

<span data-ttu-id="e5a8c-p103">En este ejemplo se muestra los servicios a que tiene acceso el usuario BelindaN@litwareinc.com. Muestra los servicios que están asociados con todas las licencias asignados a su cuenta.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p103">This example shows the services to which the user BelindaN@litwareinc.com has access. This shows the services that are associated with all licenses that are assigned to her account.</span></span>
  
```
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

<span data-ttu-id="e5a8c-123">En este ejemplo se muestran los servicios a los que tiene acceso la usuaria BelindaN@litwareinc.com a partir de la primera licencia asignada a su cuenta (el número de índice es 0).</span><span class="sxs-lookup"><span data-stu-id="e5a8c-123">This example shows the services that user BelindaN@litwareinc.com has access to from the first license that's assigned to her account (the index number is 0).</span></span>
  
```
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

<span data-ttu-id="e5a8c-124">Para buscar todos los usuarios con licencia que están habilitados o no habilitados para servicios específicos, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-124">To find all the licensed users who have been enabled or not enabled for specific services, use the following syntax:</span></span>
  
```
Get-MsolUser -All | where {$_.isLicensed -eq $true -and $_.Licenses[<LicenseIndexNumber> ].ServiceStatus[<ServiceIndexNumber> ].ProvisioningStatus <-eq | -ne> "Disabled" -and $_.Licenses[<LicenseIndexNumber> ].ServiceStatus[<ServiceIndexNumber> ].ProvisioningStatus <-eq | -ne> "Disabled"...}
```

<span data-ttu-id="e5a8c-125">Estos ejemplos usan la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-125">These examples use the following information:</span></span>
  
- <span data-ttu-id="e5a8c-126">La licencia que da acceso a los servicios de Office 365 que nos interesa es la primera que se asigna a todos los usuarios (el número de índice es 0).</span><span class="sxs-lookup"><span data-stu-id="e5a8c-126">The license that gives access to the Office 365 services that we're interested in is the first license that's assigned to all users (the index number is 0).</span></span>
    
- <span data-ttu-id="e5a8c-p104">Los servicios de Office 365 que nos interesa son Skype para los negocios en línea y Exchange Online. Para las licencias que están asociadas con el plan de licencias, Skype para los negocios en línea es el servicio de 6 enumerado (el número de índice es 5), y Exchange Online es el servicio 9o enumerados (el número de índice es 8).</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p104">The Office 365 services that we're interested in are Skype for Business Online and Exchange Online. For the licenses that are associated with the licensing plan, Skype for Business Online is the 6th service listed (the index number is 5), and Exchange Online is the 9th service listed (the index number is 8).</span></span>
    
<span data-ttu-id="e5a8c-129">Este ejemplo devuelve con licencia de todos los usuarios habilitados para Skype para los negocios en línea y Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-129">This example returns all licensed users who are enabled for Skype for Business Online and Exchange Online.</span></span>
  
```
Get-MsolUser -All | where {$_.isLicensed -eq $true -and $_.Licenses[0].ServiceStatus[5].ProvisioningStatus -ne "Disabled" -and $_.Licenses[0].ServiceStatus[8].ProvisioningStatus -ne "Disabled"}
```

<span data-ttu-id="e5a8c-130">Este ejemplo devuelve todos los usuarios con licencia que no están habilitados para Skype en Exchange Online o negocios en línea.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-130">This example returns all licensed users who aren't enabled for Skype for Business Online or Exchange Online.</span></span>
  
```
Get-MsolUser -All | where {$_.isLicensed -eq $true -and $_.Licenses[0].ServiceStatus[5].ProvisioningStatus -eq "Disabled" -and $_.Licenses[0].ServiceStatus[8].ProvisioningStatus -eq "Disabled"}
```

## <a name="the-long-version-instructions-with-detailed-explanations"></a><span data-ttu-id="e5a8c-131">Versión larga (instrucciones con explicaciones detalladas)</span><span class="sxs-lookup"><span data-stu-id="e5a8c-131">The long version (instructions with detailed explanations)</span></span>
<span data-ttu-id="e5a8c-132"><a name="LongVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="e5a8c-132"></span></span>

### <a name="find-the-office-365-powershell-services-that-a-user-has-access-to"></a><span data-ttu-id="e5a8c-133">Encontrar los servicios de Office 365 PowerShell que un usuario tenga acceso a</span><span class="sxs-lookup"><span data-stu-id="e5a8c-133">Find the Office 365 PowerShell services that a user has access to</span></span>

<span data-ttu-id="e5a8c-p105">Es sin duda importante para saber los usuarios que se hayan expedido licencias de Office 365 y los usuarios que aún no. (Vea el artículo [Ver usuarios con licenciados como sin con Office 365 PowerShell](view-licensed-and-unlicensed-users-with-office-365-powershell.md) para obtener más información). Sin embargo, basta con tener una licencia de Office 365 no sabrá nada acerca de lo que el usuario realmente puede hacer con Office 365. ¿Él o ella sirve Exchange Online o Skype para los negocios en línea? ¿Puede este usuario tener acceso a SharePoint Online? ¿Él o ella tiene acceso a Office Professional Plus? Una licencia significa simplemente que el usuario tiene la posibilidad de tener acceso a estos servicios. Sin embargo, las capacidades disponibles para el usuario dependen de los servicios que se han habilitado en su licencia.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p105">It's obviously important for you to know which users have been issued Office 365 licenses and which users haven't. (See the article [View licensed and unlicensed users with Office 365 PowerShell](view-licensed-and-unlicensed-users-with-office-365-powershell.md) for more information). However, simply having an Office 365 license doesn't tell you anything about what that user can actually do with Office 365. Can he or she use Exchange Online or Skype for Business Online? Can this user access SharePoint Online? Does he or she have access to Office Professional Plus? Having a license simply means that the user has the potential to access these services. However, the capabilities available to a user depend on the services that have been enabled on his or her license.</span></span>
  
<span data-ttu-id="e5a8c-p106">Entonces, ¿cómo podemos determinar qué características de Office 365 un usuario tiene acceso a? Para ello, es necesario ejecutar un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p106">So how can we determine which Office 365 features a user has access to? To do that we need to run a command similar to this one:</span></span>
  
```
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.com | Select-Object -ExpandProperty Licenses | Select-Object -ExpandProperty ServiceStatus
```

<span data-ttu-id="e5a8c-144">En este comando, estamos utilizando el cmdlet **Get-MsolUser** para devolver información sobre la cuenta BelindaN@litwareinc.com. Una vez que nos hemos devuelto esa información, luego canalizar los datos de la cuenta al cmdlet **Select-Object** y solicitar **Select-Object** "expandir" el valor de la propiedad de **licencias** :</span><span class="sxs-lookup"><span data-stu-id="e5a8c-144">In this command, we're using the **Get-MsolUser** cmdlet to return information about the account BelindaN@litwareinc.com. Once we've returned that information, we then pipe the account data to the **Select-Object** cmdlet and ask **Select-Object** to "expand" the value of the **Licenses** property:</span></span>
  
 `Select-Object -ExpandProperty Licenses`
  
<span data-ttu-id="e5a8c-p107">¿Por qué lo hacemos? Bueno, de forma predeterminada, las **licencias de** propiedad sólo nos indica el nombre del paquete de licencias licencia de Belinda procedencia:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p107">Why do we do that? Well, by default the **Licenses** property only tells us the name of the licensing pack where Belinda's license came from:</span></span>
  
```
Licenses
--------
{litwareinc:ENTERPRISEPACK}
```

<span data-ttu-id="e5a8c-147">La propiedad de **licencias** "expansión" nos da un poco más de información:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-147">"Expanding" the **Licenses** property gives us a little more information:</span></span>
  
```
ExtensionData     AccountSku       AccountSkuId ServiceStatus
-------------     ----------       ------------ -------------
System.Runtime... Microsoft.On...  litwarein... {Microsoft.Online.A...
```

<span data-ttu-id="e5a8c-148">Y, a continuación, expandiendo la propiedad **ServiceStatus** , podemos obtener aún más información:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-148">And then by expanding the **ServiceStatus** property we can get back even more information:</span></span>
  
|<span data-ttu-id="e5a8c-149">****Plan de servicio****</span><span class="sxs-lookup"><span data-stu-id="e5a8c-149">****Service plan****</span></span>|<span data-ttu-id="e5a8c-150">****Descripción****</span><span class="sxs-lookup"><span data-stu-id="e5a8c-150">****Description****</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="e5a8c-151">Sway</span><span class="sxs-lookup"><span data-stu-id="e5a8c-151">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="e5a8c-152">Administración de dispositivos móviles para Office 365</span><span class="sxs-lookup"><span data-stu-id="e5a8c-152">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="e5a8c-153">Yammer</span><span class="sxs-lookup"><span data-stu-id="e5a8c-153">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="e5a8c-154">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="e5a8c-154">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="e5a8c-155">Office Professional Plus</span><span class="sxs-lookup"><span data-stu-id="e5a8c-155">Office Professional Plus</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="e5a8c-156">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="e5a8c-156">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="e5a8c-157">Office Online</span><span class="sxs-lookup"><span data-stu-id="e5a8c-157">Office Online</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="e5a8c-158">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e5a8c-158">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="e5a8c-159">Plan 2 de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e5a8c-159">Exchange Online Plan 2</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="e5a8c-p108">¿Se dice que es demasiado escribiendo? Bueno, si usted puede poner con un poco obtusidad de Windows PowerShell, puede ejecutar esta versión condensada del comando en su lugar: >`(Get-MsolUser -UserPrincipalName BelindaN@litwareinc.com).Licenses[0].ServiceStatus`</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p108">You say that's too much typing? Well, if you can put up with a little Windows PowerShell obtuseness, you can run this condensed version of the command instead: >  `(Get-MsolUser -UserPrincipalName BelindaN@litwareinc.com).Licenses[0].ServiceStatus`</span></span>
  
<span data-ttu-id="e5a8c-p109">En caso de que se lo está preguntando, podemos "expandir" la propiedad de **licencias** porque **licencias** es una propiedad multivalor: es una sola propiedad que puede almacenar varios valores. Cuando se expande un valor de propiedad para que se desglosará simplemente obtener estos valores adicionales que, de forma predeterminada, no se muestran en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p109">In case you're wondering, we can "expand" the **Licenses** property because **Licenses** is a multivalued property: it's a single property that can store multiple values. When we expand a property value we simply drill down to get at these additional values that, by default, are not displayed onscreen.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e5a8c-p110">¿Cómo se supone que sabe que un valor es una propiedad multivalor? Bien, para buscar que fuera, prueba ejecutando un comando similar a éste: > `Get-MsolUser -UserPrincipalName BelindaN@litwareinc.com | Get-Member`> el cmdlet **Get-member** devuelve información sobre el objeto en Sí; en este caso, información sobre la propiedad valores que componen un objeto de cuenta de usuario. Aquí está lo que **Get-Member** tiene que decir sobre la propiedad de **licencias** : > `Licenses Property System.Collections.Generic.List[Microsoft.On...`> Si la definición de propiedad dice algo sobre colecciones (en este caso, `System.Collections.Generic.List`), a continuación, sabrá que usted está tratando con una propiedad multivalor.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p110">So how are you supposed to know that a value is a multivalued property? Well, to find that out, try running a command similar to this: >  `Get-MsolUser -UserPrincipalName BelindaN@litwareinc.com | Get-Member`> The **Get-member** cmdlet returns information about the object itself; in this case, information about the property values that make up a user account object. Here's what **Get-Member** has to say about the **Licenses** property:>  `Licenses Property System.Collections.Generic.List[Microsoft.On...`> If the property definition says something about collections (in this case,  `System.Collections.Generic.List`) then you know you're dealing with a multivalued property.</span></span> 
  
<span data-ttu-id="e5a8c-p111">Así que ¿qué significa todo esto? Para averiguarlo, primero echemos otro vistazo a la información devuelta por el cmdlet **Get-MsolUser** :</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p111">So what does all this mean? To answer that, let's first take another look at the information returned by the **Get-MsolUser** cmdlet:</span></span>
  
```
ServicePlan                       ProvisioningStatus
-----------                       ------------------
SWAY                              Success
INTUNE_O365                       Success
YAMMER_ENTERPRISE                 PendingInput
RMS_S_ENTERPRISE                  Success
OFFICESUBSCRIPTION                Success
MCOSTANDARD                       Success
SHAREPOINTWAC                     Success
SHAREPOINTENTERPRISE              Success
EXCHANGE_S_ENTERPRISE             Success
```

<span data-ttu-id="e5a8c-169">Y también Echemos un vistazo a una tabla que explica lo que representan realmente estos planes de servicio denominada de forma extraña:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-169">And let's also take a look at a table that explains what these oddly-named service plans really represent:</span></span>
  
|<span data-ttu-id="e5a8c-170">****Plan de servicio****</span><span class="sxs-lookup"><span data-stu-id="e5a8c-170">****Service plan****</span></span>|<span data-ttu-id="e5a8c-171">****Descripción****</span><span class="sxs-lookup"><span data-stu-id="e5a8c-171">****Description****</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="e5a8c-172">Sway</span><span class="sxs-lookup"><span data-stu-id="e5a8c-172">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="e5a8c-173">Administración de dispositivos móviles para Office 365</span><span class="sxs-lookup"><span data-stu-id="e5a8c-173">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="e5a8c-174">Yammer</span><span class="sxs-lookup"><span data-stu-id="e5a8c-174">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="e5a8c-175">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="e5a8c-175">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="e5a8c-176">Office Professional Plus</span><span class="sxs-lookup"><span data-stu-id="e5a8c-176">Office Professional Plus</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="e5a8c-177">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="e5a8c-177">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="e5a8c-178">Office Online</span><span class="sxs-lookup"><span data-stu-id="e5a8c-178">Office Online</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="e5a8c-179">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e5a8c-179">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="e5a8c-180">Plan 2 de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e5a8c-180">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="e5a8c-p112">¿Lo ha entendido todo?  `MCOSTANDARD` es simplemente un nombre de programación interno de Skype para los negocios en línea, mientras que `OFFICESUSBCRIPTION` es simplemente el nombre de programación interno para Office Professional Plus. No es la solución más intuitiva del mundo, pero mientras tenga esta tabla a mano no tendrá muchos problemas cuando se trata de trabajar con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p112">Got all that?  `MCOSTANDARD` is just an internal programming name for Skype for Business Online, while `OFFICESUSBCRIPTION` is just the internal programming name for Office Professional Plus. It's not the most intuitive thing in the world, but as long as you keep this table handy you won't have many problems when it comes to working with Office 365 services.</span></span>
  
<span data-ttu-id="e5a8c-p113">Pero espere un momento: hay más. Como vimos en el artículo [servicios con Office 365 PowerShell y licencias de vista](view-licenses-and-services-with-office-365-powershell.md), si se establece la **ProvisioningStatus** en `Success` que significa que el servicio se ha habilitado totalmente; Por ejemplo si `MCOSTANDARD` se establece en `Success` que significa que el usuario puede tener acceso a Skype para los negocios en línea. Si se establece la **ProvisioningStatus** en `PendingInput` que significa que Office 365 todavía está procesando la solicitud de servicio; Sin embargo, el usuario puede iniciar sesión normalmente y tener acceso al servicio, mientras que la solicitud finalice el procesamiento. ( `YAMMER_ENTERPRISE` siempre se mostrarán como `PendingInput`, pero eso está bien: que no impedirá que un usuario inicie sesión en Yammer).</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p113">But wait: there's more. As we learned in the article [View licenses and services with Office 365 PowerShell](view-licenses-and-services-with-office-365-powershell.md), if the **ProvisioningStatus** is set to `Success` that means that the service has been fully enabled; for example if `MCOSTANDARD` is set to `Success` that means that the user can access Skype for Business Online. If the **ProvisioningStatus** is set to `PendingInput` that means that Office 365 is still processing the service request; however, the user can typically log on and access the service while the request finishes processing. ( `YAMMER_ENTERPRISE` will always be shown as `PendingInput`, but that's OK: that won't stop a user from logging on to Yammer).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e5a8c-188">Los usuarios pueden instalar y activar una nueva instalación de Office Professional Plus al `OFFICESUBSCRIPTION` en el `PendingInput` estado.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-188">Users can install and activate a new Office Professional Plus installation while  `OFFICESUBSCRIPTION` is in the `PendingInput` state.</span></span>
  
<span data-ttu-id="e5a8c-189">Y, evidentemente, es un servicio está configurado para `Disabled` que significa que el servicio en cuestión no está disponible para el usuario.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-189">And, needless to say, is a service is set to  `Disabled` that means that the service in question is not available to the user.</span></span>
  

### <a name="find-users-that-have-access-to-specific-office-365-powershell-services"></a><span data-ttu-id="e5a8c-190">Buscar los usuarios que tienen acceso a servicios específicos de Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5a8c-190">Find users that have access to specific Office 365 PowerShell services</span></span>

<span data-ttu-id="e5a8c-p114">En un artículo independiente, vimos cómo puede utilizar Office 365 PowerShell para deshabilitar el acceso del usuario a los servicios. (Si se perdió ese artículo, vea [Deshabilitar el acceso a los servicios de Office 365 PowerShell](disable-access-to-services-with-office-365-powershell.md)). Esto nos lleva a una pregunta obvia: ¿hay alguna manera de determinar qué *usuarios* (es decir, más de un usuario) tiene los servicios que habilitan o deshabilitan?</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p114">In a separate article, we saw how you can use Office 365 PowerShell to disable user access to services. (If you missed that article, see [Disable access to services with Office 365 PowerShell](disable-access-to-services-with-office-365-powershell.md)). That leads to an obvious question: is there any way to determine which  *users*  (that is, more than one user) have which services enabled or disabled?</span></span>
  
<span data-ttu-id="e5a8c-p115">Esperamos que alguien pediría. Para poder responder a esa pregunta, vamos a revisar la tabla de servicios que primero analizamos en el artículo [ver licencias y servicios con Office 365 PowerShell](view-licenses-and-services-with-office-365-powershell.md) para nuestro plan de licencias sólo está disponible `litwareinc:ENTERPRISEPACK`:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p115">We were hoping that someone would ask that. In order to answer that question, let's review the table of services that we first looked at in the article [View licenses and services with Office 365 PowerShell](view-licenses-and-services-with-office-365-powershell.md) for our only available licensing plan `litwareinc:ENTERPRISEPACK`:</span></span>
  
|<span data-ttu-id="e5a8c-196">****Plan de servicio****</span><span class="sxs-lookup"><span data-stu-id="e5a8c-196">****Service plan****</span></span>|<span data-ttu-id="e5a8c-197">****Descripción****</span><span class="sxs-lookup"><span data-stu-id="e5a8c-197">****Description****</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="e5a8c-198">Sway</span><span class="sxs-lookup"><span data-stu-id="e5a8c-198">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="e5a8c-199">Administración de dispositivos móviles para Office 365</span><span class="sxs-lookup"><span data-stu-id="e5a8c-199">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="e5a8c-200">Yammer</span><span class="sxs-lookup"><span data-stu-id="e5a8c-200">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="e5a8c-201">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="e5a8c-201">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="e5a8c-202">Office Professional Plus</span><span class="sxs-lookup"><span data-stu-id="e5a8c-202">Office Professional Plus</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="e5a8c-203">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="e5a8c-203">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="e5a8c-204">Office Online</span><span class="sxs-lookup"><span data-stu-id="e5a8c-204">Office Online</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="e5a8c-205">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e5a8c-205">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="e5a8c-206">Plan 2 de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e5a8c-206">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="e5a8c-p116">Como quizá recuerde, el plan de servicio no es más que el nombre de programación interno de un producto; Por ejemplo, `OFFICESUBSCRIPTION`, a nombre de uno, es el nombre de programación interno para Office Professional Plus. Si `OFFICESUBSCRIPTION` se muestra como `SUCCESS` en el plan de servicio de un usuario, a continuación, que significa que el usuario puede tener acceso a Office Professional Plus. Si `EXCHANGE_S_ENTERPRISE` aparece como `DISABLED` que significa que el usuario no puede utilizar Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p116">As you might recall, the service plan is nothing more than the internal programming name for a product; for example,  `OFFICESUBSCRIPTION`, to name one, is the internal programming name for Office Professional Plus. If  `OFFICESUBSCRIPTION` shows up as `SUCCESS` on a user's service plan, then that means that the user is allowed to access Office Professional Plus. If `EXCHANGE_S_ENTERPRISE` is listed as `DISABLED` that means the user can't use Exchange Online.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e5a8c-210">Los usuarios pueden instalar y activar una nueva instalación de Office Professional Plus al `OFFICESUBSCRIPTION` en el `PendingInput` estado.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-210">Users can install and activate a new Office Professional Plus installation while  `OFFICESUBSCRIPTION` is in the `PendingInput` state.</span></span>
  
<span data-ttu-id="e5a8c-p117">Ahora es el momento donde es muy importante el orden en que aparecen los servicios. Windows PowerShell se asigna un número de índice a cada entrada de la lista. La primera entrada es 0, la siguiente entrada es 1 y así sucesivamente. Los resultados se explican en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p117">Now is the time where the order in which the services appear is extremely important. Windows PowerShell assigns an index number to each entry in the list. The first entry is 0, the next entry is 1, and so on. The results are explained in the following table:</span></span>
  
|<span data-ttu-id="e5a8c-215">Número de índice ***</span><span class="sxs-lookup"><span data-stu-id="e5a8c-215">****Index number****</span></span>|<span data-ttu-id="e5a8c-216">****Plan de servicio****</span><span class="sxs-lookup"><span data-stu-id="e5a8c-216">****Service plan****</span></span>|
|:-----|:-----|
|<span data-ttu-id="e5a8c-217">0</span><span class="sxs-lookup"><span data-stu-id="e5a8c-217">0</span></span>  <br/> | `SWAY` <br/> |
|<span data-ttu-id="e5a8c-218">1</span><span class="sxs-lookup"><span data-stu-id="e5a8c-218">1</span></span>  <br/> | `INTUNE_O365` <br/> |
|<span data-ttu-id="e5a8c-219">2</span><span class="sxs-lookup"><span data-stu-id="e5a8c-219">2</span></span>  <br/> | `YAMMER_ENTERPRISE` <br/> |
|<span data-ttu-id="e5a8c-220">3</span><span class="sxs-lookup"><span data-stu-id="e5a8c-220">3</span></span>  <br/> | `RMS_S_ENTERPRISE` <br/> |
|<span data-ttu-id="e5a8c-221">4</span><span class="sxs-lookup"><span data-stu-id="e5a8c-221">4</span></span>  <br/> | `OFFICESUBSCRIPTION` <br/> |
|<span data-ttu-id="e5a8c-222">5</span><span class="sxs-lookup"><span data-stu-id="e5a8c-222">5</span></span>  <br/> | `MCOSTANDARD` <br/> |
|<span data-ttu-id="e5a8c-223">6</span><span class="sxs-lookup"><span data-stu-id="e5a8c-223">6</span></span>  <br/> | `SHAREPOINTWAC` <br/> |
|<span data-ttu-id="e5a8c-224">7</span><span class="sxs-lookup"><span data-stu-id="e5a8c-224">7</span></span>  <br/> | `SHAREPOINTENTERPRISE` <br/> |
|<span data-ttu-id="e5a8c-225">8</span><span class="sxs-lookup"><span data-stu-id="e5a8c-225">8</span></span>  <br/> | `EXCHANGE_S_ENTERPRISE` <br/> |
   
<span data-ttu-id="e5a8c-226">Como puede ver, `SWAY` es el primer servicio de la lista, por lo que se obtiene asignado el número de índice 0.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-226">As you can see,  `SWAY` is the first service listed, so it gets assigned index number 0.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e5a8c-p118">¿Por qué no 1 y 0? Es algo de programación. En lenguajes de programación índices indican hasta qué punto un elemento "offset" desde el principio de la matriz. El primer elemento *es* el principio de la matriz, por lo que su desplazamiento es 0. El segundo elemento es 1 artículo desde el principio de la matriz, por lo que su desplazamiento es 1.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p118">Why 0 and not 1? That's a programming thing. In programming languages indices tell you how far an item is "offset" from the beginning of the array. The first item  *is*  the beginning of the array, so its offset is 0. The second item is 1 item from the beginning of the array, so its offset is 1.</span></span>
  
<span data-ttu-id="e5a8c-p119">Probemos un ejemplo. Supongamos que nos gustaría una lista de todos los usuarios con licencia que no se han habilitado para Exchange Online. Para ello, podemos utilizar el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p119">Let's try an example. Suppose we'd like a list of all the licensed users who have not been enabled for Exchange Online. To do that, we can use the following command:</span></span>
  
```
Get-MsolUser | Where-Object {$_.isLicensed -eq $true -and $_.Licenses[0].ServiceStatus[8].ProvisioningStatus -eq "Disabled"}
```

<span data-ttu-id="e5a8c-p120">Hay que reconocer que es un comando poco aspecto críptico, así que vamos a tardar un minuto a explicar cómo funciona. Esto es realmente un comando de dos partes, y la primera parte es muy sencilla: utilizamos el cmdlet **Get-MsolUser** para devolver una colección de todos los usuarios de Office 365 (con licencia y sin licencia):</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p120">Admittedly, that's a cryptic-looking little command, so let's take a minute to explain how it works. This is actually a two-part command, and the first part is very simple: we use the **Get-MsolUser** cmdlet to return a collection of all our Office 365 users (both licensed and unlicensed):</span></span>
  
```
Get-MsolUser
```

<span data-ttu-id="e5a8c-p121">Entonces, esa información se canaliza hacia el cmdlet **Where-Object** . **Where-Object** pasa por todas las cuentas de usuario y busca aquellas cuentas que los criterios siguientes cumplan:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p121">That information is then piped to the **Where-Object** cmdlet. **Where-Object** goes through all the user accounts and looks for those accounts that meet both of the following criteria:</span></span>
  
- <span data-ttu-id="e5a8c-p122">Es igual a la propiedad **isLicensed** ( `-eq`) `True` ( `$true`). Que nos permite descartar los usuarios sin licencia.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p122">The **isLicensed** property is equal to ( `-eq`)  `True` ( `$true`). That enables us to weed out the unlicensed users.</span></span>
    
- <span data-ttu-id="e5a8c-p123">El valor de las licencias de **[0]. ServiceStatus [8]. ProvisioningStatus** propiedad es igual a ( `-eq`) `Disabled`. Para nuestros fines inmediatas, la parte importante de este nombre de propiedad inmanejable es esto:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p123">The value of the **Licenses[0].ServiceStatus[8].ProvisioningStatus** property is equal to ( `-eq`)  `Disabled`. For our immediate purposes, the important part of this unwieldy property name is this:</span></span>
    
     `ServiceStatus[8]`
    
    <span data-ttu-id="e5a8c-p124">El `[8]` representa el número de índice para Exchange Online. (Sabemos el análisis de la tabla hace unos minutos). ¿Qué pasaría si quisiéramos encontrar todos los usuarios habilitados para Skype para los negocios en línea? Bueno, el número de índice de Skype para los negocios en línea es 5, por lo que utilizaríamos esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p124">The  `[8]` represents the index number for Exchange Online. (We know that from looking at the table a few minutes ago). What if we wanted to find all the users enabled for Skype for Business Online? Well, the index number for Skype for Business Online is 5, so we'd use this syntax:</span></span>
    
     `ServiceStatus[5]`
    
    <span data-ttu-id="e5a8c-247">Etc., etc.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-247">Etc., etc.</span></span>
    
    <span data-ttu-id="e5a8c-p125">Por cierto, `Licenses[0]` indica el plan de licencias que queremos mirar. Dado que nuestro dominio de prueba sólo tiene un plan de licencias esto no importa mucho. Pero supongamos que tenemos un usuario que se ha asignado licencias desde dos planes de licencias diferentes. En ese caso, `Licenses[0]` representaría el primer plan de licencias, y `Licenses[1]` representaría el segundo plan de licencias.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p125">Incidentally,  `Licenses[0]` indicates the licensing plan that we want to look at. Since our test domain only has one licensing plan this doesn't matter much. But suppose we had a user who has been assigned licenses from two different licensing plans. In that case, `Licenses[0]` would represent the first licensing plan, and `Licenses[1]` would represent the second licensing plan.</span></span>
    
    <span data-ttu-id="e5a8c-252">Para encontrar las licencias que están asignadas a un usuario y el orden en que se muestran, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-252">To find the licenses that are assigned to a user, and the order in which they are listed, run the following command:</span></span>
    
  ```
  Get-MsolUser -UserPrincipalName <Account>  | Format-List DisplayName,Licenses
  ```

<span data-ttu-id="e5a8c-p126">¿Puede ver cómo funciona todo esto? El número de índice para Office Professional Plus es 4; por lo tanto, este comando devuelve una lista de todos los usuarios que no han sido habilitados para Office Professional Plus:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p126">Do you see how this all works? The index number for Office Professional Plus is 4; therefore, this command returns a list of all the users who have not been enabled for Office Professional Plus:</span></span>
  
```
Get-MsolUser | Where-Object {$_.isLicensed -eq $true -and $_.Licenses.ServiceStatus[4].ProvisioningStatus -eq "Disabled"}
```

<span data-ttu-id="e5a8c-p127">Y ¿qué ocurre si deseáramos obtener una lista de usuarios que han sido *habilitados* para Office Professional Plus? Bueno, si ya ha habilitado y será su **ServiceStatus** `PendingInput` o `Success`; en otras palabras, su **ServiceStatus** será igual *no* ( `-ne`) `Disabled`. Eso significa que todo lo que tenemos que hacer es tomar nuestro comando anterior e intercambiar el `-eq` operador para la `-ne` operador:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p127">And what if we wanted a list of users who have been  *enabled*  for Office Professional Plus? Well, if you've been enabled then your **ServiceStatus** will either be `PendingInput` or `Success`; in other words, your **ServiceStatus** will *not*  equal ( `-ne`)  `Disabled`. That means all we have to do is take our previous command and swap out the  `-eq` operator for the `-ne` operator:</span></span>
  
```
Get-MsolUser | Where-Object {$_.isLicensed -eq $true -and $_.Licenses.ServiceStatus[4].ProvisioningStatus -ne "Disabled"}
```

<span data-ttu-id="e5a8c-p128">Como se suele decir va, que código probablemente no gana muchos concursos de belleza. Y, verdad sea dicha, el código puede obtener incluso más complicada. Por ejemplo, supongamos que queremos buscar usuarios que se han habilitado para ambos Skype para los negocios en línea y Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p128">As the saying goes, that code probably won't win many beauty contests. And, truth be told, the code can get even more tangled. For example, suppose we want to look for users who have been enabled for both Skype for Business Online and Exchange Online:</span></span>
  
```
Get-MsolUser | Where-Object {$_.isLicensed -eq $true -and $_.Licenses.ServiceStatus[5].ProvisioningStatus -ne "Disabled" -and $_.Licenses.ServiceStatus[8].ProvisioningStatus -ne "Disabled"}
```

<span data-ttu-id="e5a8c-p129">Pero no se preocupe demasiado sobre cómo más complicadas que podría ser: lo importante es que, con relativamente poco esfuerzo, puede recuperar esta información. ¿No se obtener en la misma información mediante el centro de administración de Office 365? En teoría, sí pero, en términos prácticos, no. Para llegar a la misma información mediante el centro de administración de Office 365, deberá mirar la información de licencia para cada usuario, un usuario a la vez, y entonces manualmente realizar un seguimiento de quién se ha habilitado para *X* y que no se habían. Que debería funcionar, pero seamos sinceros: si tiene más de 10 u 11 usuarios, no va a hacerlo. Es demasiado tediosas y lentas.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p129">But don't worry too much about how gnarly that might look: the important thing is that, with relatively little effort, you can retrieve this information. Can't you get at this same information using the Office 365 admin center? In theory, yes but, in practical terms, no. To get at this same information using the Office 365 admin center you'd need to look at the licensing information for each user, one user at a time, and then manually keep track of who'd been enabled for  *X*  and who hadn't. That would work, but let's be honest: if you have more than 10 or 11 users, you're not going to do this. It's way too tedious and time-consuming.</span></span>
  
<span data-ttu-id="e5a8c-267">Que, por supuesto, es por eso que tenemos de Windows PowerShell: Windows PowerShell le ayuda a ahorrar de tareas tediosas y lentas como el.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-267">Which, of course, is why we have Windows PowerShell: Windows PowerShell helps save you from tedious and time-consuming tasks such as that.</span></span>
  
<span data-ttu-id="e5a8c-268">Mientras estamos en él, presentamos el último comando para ver la información de servicio:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-268">While we're at it, here's the ultimate command for viewing service information:</span></span>
  
```
Get-MsolUser | Select-Object DisplayName, @{Name="Sway";Expression={$_.Licenses[0].ServiceStatus[0].ProvisioningStatus}}, @{Name="MDM";Expression={$_.Licenses[0].ServiceStatus[1].ProvisioningStatus}}, @{Name="Yammer";Expression={$_.Licenses[0].ServiceStatus[2].ProvisioningStatus}}, @{Name="AD RMS";Expression={$_.Licenses[0].ServiceStatus[3].ProvisioningStatus}}, @{Name="OfficePro";Expression={$_.Licenses[0].ServiceStatus[4].ProvisioningStatus}}, @{Name="Skype";Expression={$_.Licenses[0].ServiceStatus[5].ProvisioningStatus}}, @{Name="OfficeWeb";Expression={$_.Licenses[0].ServiceStatus[6].ProvisioningStatus}}, @{Name="SharePoint";Expression={$_.Licenses[0].ServiceStatus[7].ProvisioningStatus}}, @{Name="Exchange";Expression={$_.Licenses[0].ServiceStatus[8].ProvisioningStatus}} | ConvertTo-Html > "C:\\My Documents\\Service Info.html"
```

<span data-ttu-id="e5a8c-p130">Y Sí, es un comando muy raros. Pero se crea un archivo CSV que muestra todos los usuarios y sus Estados de servicio.</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p130">And yes, that's a very crazy-looking command. But it creates a CSV file showing all of your users and all of their service statuses.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="e5a8c-271">See also</span><span class="sxs-lookup"><span data-stu-id="e5a8c-271">See also</span></span>
<span data-ttu-id="e5a8c-272"><a name="SeeAlso"> </a></span><span class="sxs-lookup"><span data-stu-id="e5a8c-272"></span></span>

<span data-ttu-id="e5a8c-273">Vea los siguientes temas adicionales acerca de cómo administrar usuarios con Office 365 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-273">See the following additional topics about managing users with Office 365 PowerShell:</span></span>
  
- [<span data-ttu-id="e5a8c-274">Crear cuentas de usuario con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="e5a8c-274">Create user accounts with Office 365 PowerShell</span></span>](create-user-accounts-with-office-365-powershell.md)
    
- [<span data-ttu-id="e5a8c-275">Eliminar y restaurar cuentas de usuario con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="e5a8c-275">Delete and restore user accounts with Office 365 PowerShell</span></span>](delete-and-restore-user-accounts-with-office-365-powershell.md)
    
- [<span data-ttu-id="e5a8c-276">Bloquear cuentas de usuario con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="e5a8c-276">Block user accounts with Office 365 PowerShell</span></span>](block-user-accounts-with-office-365-powershell.md)
    
- [<span data-ttu-id="e5a8c-277">Asignar licencias a cuentas de usuario con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="e5a8c-277">Assign licenses to user accounts with Office 365 PowerShell</span></span>](assign-licenses-to-user-accounts-with-office-365-powershell.md)
    
- [<span data-ttu-id="e5a8c-278">Eliminar licencias de cuentas de usuario con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="e5a8c-278">Remove licenses from user accounts with Office 365 PowerShell</span></span>](remove-licenses-from-user-accounts-with-office-365-powershell.md)
    
<span data-ttu-id="e5a8c-279">Para obtener más información sobre los cmdlets que se usan en estos procedimientos, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="e5a8c-279">For more information about the cmdlets that are used in these procedures, see the following topics:</span></span>
  
- [<span data-ttu-id="e5a8c-280">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="e5a8c-280">ConvertTo-Html</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=113290)
    
- [<span data-ttu-id="e5a8c-281">Format-List</span><span class="sxs-lookup"><span data-stu-id="e5a8c-281">Format-List</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=113302)
    
- [<span data-ttu-id="e5a8c-282">Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="e5a8c-282">Get-MsolUser</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=691543)
    
- [<span data-ttu-id="e5a8c-283">Select-Object</span><span class="sxs-lookup"><span data-stu-id="e5a8c-283">Select-Object</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=113387)
    
- [<span data-ttu-id="e5a8c-284">Where-Object</span><span class="sxs-lookup"><span data-stu-id="e5a8c-284">Where-Object</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=113423)
    

  
## <a name="new-to-office-365"></a><span data-ttu-id="e5a8c-285">¿Es la primera vez que usa Office 365?</span><span class="sxs-lookup"><span data-stu-id="e5a8c-285">New to Office 365?</span></span>


||
|:-----|
|<span data-ttu-id="e5a8c-p131">![El icono reducido de LinkedIn Learning](images/d547e1cb-7c66-422b-85be-7e7db2a9cf97.png) **¿Es la primera vez que usa Office 365?**         LinkedIn Learning pone a su disposición vídeos gratuitos de cursos de [Office 365 admins and IT pros](https://support.office.com/article/Office-365-admin-and-IT-pro-courses-68cc9b95-0bdc-491e-a81f-ee70b3ec63c5).</span><span class="sxs-lookup"><span data-stu-id="e5a8c-p131">![The short icon for LinkedIn Learning](images/d547e1cb-7c66-422b-85be-7e7db2a9cf97.png) **New to Office 365?**         Discover free video courses for [Office 365 admins and IT pros](https://support.office.com/article/Office-365-admin-and-IT-pro-courses-68cc9b95-0bdc-491e-a81f-ee70b3ec63c5), brought to you by LinkedIn Learning.</span></span> |
   
