---
title: Ver las licencias y los servicios con PowerShell de Office 365
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
- Ent_Office_Other
- O365ITProTrain
- DecEntMigration
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: "Explica cómo utilizar Office 365 PowerShell para ver información acerca de los planes de licencias, servicios y licencias que están disponibles en la organización de Office 365."
ms.openlocfilehash: dc9ea5ad5077062a05c0070ffecbf580d3aacc49
ms.sourcegitcommit: d31cf57295e8f3d798ab971d405baf3bd3eb7a45
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="view-licenses-and-services-with-office-365-powershell"></a><span data-ttu-id="51700-103">Ver las licencias y los servicios con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="51700-103">View licenses and services with Office 365 PowerShell</span></span>

<span data-ttu-id="51700-104">**Resumen:** Explica cómo utilizar Office 365 PowerShell para ver información acerca de los planes de licencias, servicios y licencias que están disponibles en la organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="51700-104">**Summary:** Explains how to use Office 365 PowerShell to view information about the licensing plans, services, and licenses that are available in your Office 365 organization.</span></span>
  
<span data-ttu-id="51700-105">Todas las suscripciones de Office 365 se componen de estos elementos:</span><span class="sxs-lookup"><span data-stu-id="51700-105">Every Office 365 subscription consists of the following elements:</span></span>
- <span data-ttu-id="51700-p101">**Planes de licencias** También se conocen comoplanes de licencia o planes de Office 365. Los planes de licencias determinan los servicios de Office 365 que están disponibles para los usuarios. Su suscripción a Office 365 puede contener varios planes de licencias. Un plan de licencias de ejemplo sería Office 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="51700-p101">**Licensing plans** These are also known aslicense plans or Office 365 plans. Licensing plans define the Office 365 services that are available to users. Your Office 365 subscription may contain multiple licensing plans. An example licensing plan would be Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="51700-p102">**Servicios** También se conocen comoplanes de servicio. Los servicios son los productos, las características y las capacidades de Office 365 disponibles en cada plan de licencias, por ejemplo, Exchange Online y Office Professional Plus. Los usuarios pueden tener varias licencias asignadas que provengan de diferentes planes de licencias, y les permitan obtener acceso a diferentes servicios.</span><span class="sxs-lookup"><span data-stu-id="51700-p102">**Services** These are also known asservice plans. Services are the Office 365 products, features, and capabilities that are available in each licensing plan, for example, Exchange Online and Office Professional Plus. Users can have multiple licenses assigned to them from different licensing plans that grant access to different services.</span></span>
    
- <span data-ttu-id="51700-p103">**Licencias** Los planes de licencias contienen el número de licencias que haya adquirido. Puede asignar licencias a los usuarios para que estos puedan usar los servicios de Office 365 definidos por el plan de licencias. Cada cuenta de usuario necesita como mínimo una licencia del plan de licencias para que el usuario correspondiente pueda iniciar sesión en Office 365 y usar los servicios.</span><span class="sxs-lookup"><span data-stu-id="51700-p103">**Licenses** Each licensing plan contains the number of licenses that you purchased. You assign licenses to users so they can use the Office 365 services that are defined by the licensing plan. Every user account requires at least one license from one licensing plan so they can log on to Office 365 and use the services.</span></span>
    
<span data-ttu-id="51700-p104">Puede usar PowerShell de Office 365 para ver información detallada sobre los planes de licencias, las licencias y los servicios disponibles en su organización de Office 365. Para obtener más información sobre los productos, las características y los servicios disponibles en las diferentes suscripciones de Office 365, consulte [Opciones de planes de Office 365](https://go.microsoft.com/fwlink/p/?LinkId=691147).</span><span class="sxs-lookup"><span data-stu-id="51700-p104">You can use Office 365 PowerShell to view details about the available licensing plans, licenses, and services in your Office 365 organization. For more information about the products, features, and services that are available in different Office 365 subscriptions, see [Office 365 Plan Options](https://go.microsoft.com/fwlink/p/?LinkId=691147).</span></span>
## <a name="before-you-begin"></a><span data-ttu-id="51700-118">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="51700-118">Before you begin</span></span>
<span data-ttu-id="51700-119"><a name="RTT"> </a></span><span class="sxs-lookup"><span data-stu-id="51700-119"></span></span>

- <span data-ttu-id="51700-p105">Los procedimientos de este tema requieren conectarse a PowerShell de Office 365. Para obtener instrucciones, vea [Conectarse a PowerShell de Office 365](connect-to-office-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="51700-p105">The procedures in this topic require you to connect to Office 365 PowerShell. For instructions, see [Connect to Office 365 PowerShell](connect-to-office-365-powershell.md).</span></span>
    
- <span data-ttu-id="51700-p106">Hay un script de PowerShell que automatiza los procedimientos descritos en este tema. En concreto, el script le permite ver y deshabilitar servicios de la organización de Office 365, incluido Sway. Para obtener más información, consulte [Deshabilitar el acceso a Sway con Office 365 PowerShell](disable-access-to-sway-with-office-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="51700-p106">A PowerShell script is available that automates the procedures described in this topic. Specifically, the script allows you to view and disable services in your Office 365 organization, including Sway. For more information, see [Disable access to Sway with Office 365 PowerShell](disable-access-to-sway-with-office-365-powershell.md).</span></span>
    
## <a name="view-information-about-licensing-plans-and-the-available-licenses"></a><span data-ttu-id="51700-125">Ver información sobre los planes de licencias y las licencias disponibles</span><span class="sxs-lookup"><span data-stu-id="51700-125">View information about licensing plans and the available licenses</span></span>
<span data-ttu-id="51700-126"><a name="ShortVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="51700-126"></span></span>

<span data-ttu-id="51700-127">Para obtener información resumida sobre los planes de licencias actuales y las licencias disponibles en cada plan, ejecute el siguiente comando en PowerShell de Office 365:</span><span class="sxs-lookup"><span data-stu-id="51700-127">To view summary information about your current licensing plans and the available licenses for each plan, run the following command in Office 365 PowerShell:</span></span>
  
```
Get-MsolAccountSku
```

<span data-ttu-id="51700-128">Los resultados contienen la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="51700-128">The results contain the following information:</span></span>
  
- <span data-ttu-id="51700-p107">**AccountSkuId:** Mostrar los planes de licencia disponibles para su organización mediante la sintaxis `<CompanyName>:<LicensingPlan>`.  _<CompanyName>_ es el valor que proporciona cuando se inscribe en Office 365 y es exclusivo para su organización. El _<LicensingPlan>_ valor es el mismo para todos los usuarios. Por ejemplo, en el valor `litwareinc:ENTERPRISEPACK`, el nombre de la empresa es `litwareinc`y el nombre del plan de licencia `ENTERPRISEPACK`, que es el nombre del sistema para Office 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="51700-p107">**AccountSkuId:** Show the available licensing plans for your organization by using the syntax `<CompanyName>:<LicensingPlan>`.  _<CompanyName>_ is the value that you provided when you enrolled in Office 365, and is unique for your organization. The _<LicensingPlan>_ value is the same for everyone. For example, in the value `litwareinc:ENTERPRISEPACK`, the company name is  `litwareinc`, and the licensing plan name  `ENTERPRISEPACK`, which is the system name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="51700-133">**ActiveUnits:** Número de licencias que haya compras para un determinado plan de licencias.</span><span class="sxs-lookup"><span data-stu-id="51700-133">**ActiveUnits:** Number of licenses that you've purchases for a specific licensing plan.</span></span>
    
- <span data-ttu-id="51700-134">**WarningUnits:** Número de licencias en un plan de licencias que usted no ha renovado y que caducará después del período de gracia de 30 días.</span><span class="sxs-lookup"><span data-stu-id="51700-134">**WarningUnits:** Number of licenses in a licensing plan that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="51700-135">**ConsumedUnits:** Número de licencias que haya asignado a los usuarios de un determinado plan de licencias.</span><span class="sxs-lookup"><span data-stu-id="51700-135">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="51700-136">Para ver información detallada sobre los servicios de Office 365 disponibles en todos sus planes de licencia, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="51700-136">To view details about the Office 365 services that are available in all of your license plans, run the following command:</span></span>
  
```
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="51700-p108">En la tabla siguiente, se muestran los planes de servicio de Office 365, junto con sus nombres descriptivos, para los servicios más comunes. Su lista de planes de servicio puede ser diferente. Para obtener una lista completa de los planes de servicio y sus nombres descriptivos, póngase en contacto con el [soporte técnico de Office ](https://support.office.com/home/contact).</span><span class="sxs-lookup"><span data-stu-id="51700-p108">The following table shows the Office 365 service plans and their friendly names for the most common services. Your list of service plans might be different. For a complete list of service plans and their friendly names, contact [Office Support](https://support.office.com/home/contact).</span></span>
  
|<span data-ttu-id="51700-140">****Plan de servicio****</span><span class="sxs-lookup"><span data-stu-id="51700-140">****Service plan****</span></span>|<span data-ttu-id="51700-141">****Descripción****</span><span class="sxs-lookup"><span data-stu-id="51700-141">****Description****</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="51700-142">Sway</span><span class="sxs-lookup"><span data-stu-id="51700-142">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="51700-143">Administración de dispositivos móviles para Office 365</span><span class="sxs-lookup"><span data-stu-id="51700-143">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="51700-144">Yammer</span><span class="sxs-lookup"><span data-stu-id="51700-144">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="51700-145">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="51700-145">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="51700-146">Office Professional Plus</span><span class="sxs-lookup"><span data-stu-id="51700-146">Office Professional Plus</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="51700-147">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="51700-147">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="51700-148">Office Online</span><span class="sxs-lookup"><span data-stu-id="51700-148">Office Online</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="51700-149">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="51700-149">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="51700-150">Plan 2 de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="51700-150">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="51700-151">Para obtener información detallada sobre los servicios de Office 365 disponibles en un plan de licencias en concreto, use la sintaxis siguiente.</span><span class="sxs-lookup"><span data-stu-id="51700-151">To view details about the Office 365 services that are available in a specific licensing plan, use the following syntax.</span></span>
  
```
(Get-MsolAccountSku | where {$_.AccountSkuId -eq " <AccountSkuId>"}).ServiceStatus
```

<span data-ttu-id="51700-152">Este ejemplo muestra los servicios de Office 365 que están disponibles en el plan de licencia litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="51700-152">This example shows the Office 365 services that are available in the  litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan.</span></span>
  
```
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="new-to-office-365"></a><span data-ttu-id="51700-153">¿Es la primera vez que usa Office 365?</span><span class="sxs-lookup"><span data-stu-id="51700-153">New to Office 365?</span></span>
<span data-ttu-id="51700-154"><a name="ShortVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="51700-154"></span></span>

||
|:-----|
|<span data-ttu-id="51700-p109">![El icono reducido de LinkedIn Learning](images/d547e1cb-7c66-422b-85be-7e7db2a9cf97.png) **¿Es la primera vez que usa Office 365?**         LinkedIn Learning pone a su disposición vídeos gratuitos de cursos de [Office 365 admins and IT pros](https://support.office.com/article/Office-365-admin-and-IT-pro-courses-68cc9b95-0bdc-491e-a81f-ee70b3ec63c5).</span><span class="sxs-lookup"><span data-stu-id="51700-p109">![The short icon for LinkedIn Learning](images/d547e1cb-7c66-422b-85be-7e7db2a9cf97.png) **New to Office 365?**         Discover free video courses for [Office 365 admins and IT pros](https://support.office.com/article/Office-365-admin-and-IT-pro-courses-68cc9b95-0bdc-491e-a81f-ee70b3ec63c5), brought to you by LinkedIn Learning.</span></span> |
   
## <a name="see-also"></a><span data-ttu-id="51700-157">See also</span><span class="sxs-lookup"><span data-stu-id="51700-157">See also</span></span>
<span data-ttu-id="51700-158"><a name="ShortVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="51700-158"></span></span>

#### 

[<span data-ttu-id="51700-159">Ver los usuarios con licencia y sin licencia con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="51700-159">View licensed and unlicensed users with Office 365 PowerShell</span></span>](view-licensed-and-unlicensed-users-with-office-365-powershell.md)
  
[<span data-ttu-id="51700-160">Ver los detalles del servicio y la licencia de la cuenta con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="51700-160">View account license and service details with Office 365 PowerShell</span></span>](view-account-license-and-service-details-with-office-365-powershell.md)
#### 

[<span data-ttu-id="51700-161">Get-MsolAccountSku</span><span class="sxs-lookup"><span data-stu-id="51700-161">Get-MsolAccountSku</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=691549)
