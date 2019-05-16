---
title: 'Compatibilidad con aplicaciones cliente de Office 365: autenticación basada en certificados'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
description: Office 365 Client App Support for Certificate-Based Authentication.
ms.openlocfilehash: 88bc59934399588f0a5c682c6b136ad0948ecd52
ms.sourcegitcommit: 9c6e31204aa326c31d60befe80e610f702e65800
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "33990937"
---
# <a name="office-365-client-app-support--certificate-based-authentication"></a><span data-ttu-id="8f1c2-103">Compatibilidad con aplicaciones cliente de Office 365: autenticación basada en certificados</span><span class="sxs-lookup"><span data-stu-id="8f1c2-103">Office 365 Client App Support — Certificate-based Authentication</span></span>

<span data-ttu-id="8f1c2-104">La autenticación basada en certificados permite autenticar a Azure Active Directory con un certificado de cliente en dispositivos Windows, Android o iOS.</span><span class="sxs-lookup"><span data-stu-id="8f1c2-104">Certificate-based authentication enables you to authenticate to Azure Active Directory with a client certificate on Windows, Android, or iOS devices.</span></span> <span data-ttu-id="8f1c2-105">La configuración de esta característica elimina la necesidad de escribir una combinación de nombre de usuario y contraseña en determinadas aplicaciones de correo y Microsoft Office en el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="8f1c2-105">Configuring this feature eliminates the need to enter a username and password combination into certain mail and Microsoft Office applications on your mobile device.</span></span>

<span data-ttu-id="8f1c2-106">Obtenga más información acerca de [la autenticación basada en certificados](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).</span><span class="sxs-lookup"><span data-stu-id="8f1c2-106">Learn more about [certificate-based authentication](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="8f1c2-107">Plataformas compatibles</span><span class="sxs-lookup"><span data-stu-id="8f1c2-107">Supported platforms</span></span>

 - <span data-ttu-id="8f1c2-108">Escritorio de Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8f1c2-108">Windows 10 Desktop<sup>2</sup></span></span>
 - <span data-ttu-id="8f1c2-109">Aplicaciones modernas de Windows 10</span><span class="sxs-lookup"><span data-stu-id="8f1c2-109">Windows 10 Modern Apps</span></span>
 - <span data-ttu-id="8f1c2-110">Exploradores Web</span><span class="sxs-lookup"><span data-stu-id="8f1c2-110">Web browsers</span></span>
 - <span data-ttu-id="8f1c2-111">Android</span><span class="sxs-lookup"><span data-stu-id="8f1c2-111">Android</span></span>
 - <span data-ttu-id="8f1c2-112">iOS</span><span class="sxs-lookup"><span data-stu-id="8f1c2-112">iOS</span></span>
 - <span data-ttu-id="8f1c2-113">macOS<sup>1</sup> <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8f1c2-113">macOS<sup>1</sup> <sup>2</sup></span></span>

<span data-ttu-id="8f1c2-114">Para obtener más información acerca de la compatibilidad de plataformas en Office 365, vea [System Requirements for office 365](https://products.office.com/office-system-requirements).</span><span class="sxs-lookup"><span data-stu-id="8f1c2-114">For more information about platform support in Office 365, see [System requirements for Office 365](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-clients"></a><span data-ttu-id="8f1c2-115">Clientes compatibles</span><span class="sxs-lookup"><span data-stu-id="8f1c2-115">Supported clients</span></span>

<span data-ttu-id="8f1c2-116">Las versiones más recientes de los siguientes clientes admiten la autenticación basada en certificados:</span><span class="sxs-lookup"><span data-stu-id="8f1c2-116">The latest versions of the following clients support certificate-based authentication:</span></span>

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="8f1c2-117">![Icono de acceso](media/o365-access-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-117">![Access icon](media/o365-access-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-118">Acceso</span><span class="sxs-lookup"><span data-stu-id="8f1c2-118">Access</span></span>](https://products.office.com/access) | <span data-ttu-id="8f1c2-119">![Icono de Azure](media/o365-azure-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-119">![Azure icon](media/o365-azure-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-120">Portal de <br> Azure ad</span><span class="sxs-lookup"><span data-stu-id="8f1c2-120">Azure AD <br> Portal </span></span>](https://azure.microsoft.com/features/azure-portal/) | <span data-ttu-id="8f1c2-121">![Icono del portal de empresa](media/o365-microsoft-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-121">![Company portal icon](media/o365-microsoft-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-122">Portal <br> de empresa</span><span class="sxs-lookup"><span data-stu-id="8f1c2-122">Company <br> Portal </span></span>](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) | <span data-ttu-id="8f1c2-123">![Icono de Delve](media/o365-delve-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-123">![Delve icon](media/o365-delve-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-124">Delve</span><span class="sxs-lookup"><span data-stu-id="8f1c2-124">Delve</span></span>](https://products.office.com/business/intelligent-search) | <span data-ttu-id="8f1c2-125">![Icono de Dynamics 365](media/o365-dynamics365-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-125">![Dynamics 365 icon](media/o365-dynamics365-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-126">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8f1c2-126">Dynamics 365</span></span>](https://dynamics.microsoft.com) 
| <span data-ttu-id="8f1c2-127">![Icono de borde](media/o365-edge-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-127">![Edge icon](media/o365-edge-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-128">Vanguardia</span><span class="sxs-lookup"><span data-stu-id="8f1c2-128">Edge</span></span>](https://www.microsoft.com/windows/microsoft-edge) | <span data-ttu-id="8f1c2-129">![Icono de Excel](media/o365-excel-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-129">![Excel icon](media/o365-excel-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-130">Excel</span><span class="sxs-lookup"><span data-stu-id="8f1c2-130">Excel</span></span>](https://products.office.com/excel) | <span data-ttu-id="8f1c2-131">![Icono de flujo](media/o365-flow-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-131">![Flow icon](media/o365-flow-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-132">Flow</span><span class="sxs-lookup"><span data-stu-id="8f1c2-132">Flow</span></span>](https://flow.microsoft.com) | <span data-ttu-id="8f1c2-133">![Icono formularios](media/o365-forms-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-133">![Forms icon](media/o365-forms-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-134">Forms</span><span class="sxs-lookup"><span data-stu-id="8f1c2-134">Forms</span></span>](https://flow.microsoft.com/connectors/shared_microsoftforms/microsoft-forms/) | <span data-ttu-id="8f1c2-135">![Icono de Kaizala](media/o365-kaizala-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-135">![Kaizala icon](media/o365-kaizala-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-136">Kaizala</span><span class="sxs-lookup"><span data-stu-id="8f1c2-136">Kaizala</span></span>](https://products.office.com/en/business/microsoft-kaizala) 
| <span data-ttu-id="8f1c2-137">![Icono de Office 365 administrador](media/o365-o365admin-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-137">![Office 365 Admin icon](media/o365-o365admin-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-138">Office 365 <br> administrador</span><span class="sxs-lookup"><span data-stu-id="8f1c2-138">Office 365 <br> Admin</span></span>](https://products.office.com/business/manage-office-365-admin-app) | <span data-ttu-id="8f1c2-139">![Icono de lente](media/o365-lens-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-139">![Lens icon](media/o365-lens-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-140">Office Lens</span><span class="sxs-lookup"><span data-stu-id="8f1c2-140">Office Lens</span></span>](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | <span data-ttu-id="8f1c2-141">![Icono de OneDrive para la empresa](media/o365-OneDrive-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-141">![OneDrive for Business icon](media/o365-OneDrive-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-142">OneDrive<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8f1c2-142">OneDrive<sup>1</sup></span></span>](https://products.office.com/onedrive-for-business/online-cloud-storage) |  <span data-ttu-id="8f1c2-143">![Icono de OneNote](media/o365-OneNote-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-143">![OneNote icon](media/o365-OneNote-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-144">OneNote</span><span class="sxs-lookup"><span data-stu-id="8f1c2-144">OneNote</span></span>](https://products.office.com/onenote) | <span data-ttu-id="8f1c2-145">![Icono de Outlook](media/o365-outlook-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-145">![Outlook icon](media/o365-outlook-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-146">Outlook</span><span class="sxs-lookup"><span data-stu-id="8f1c2-146">Outlook</span></span>](https://products.office.com/outlook) 
| <span data-ttu-id="8f1c2-147">![Icono de Planner](media/o365-planner-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-147">![Planner icon](media/o365-planner-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-148">Planner</span><span class="sxs-lookup"><span data-stu-id="8f1c2-148">Planner</span></span>](https://products.office.com/business/task-management-software) | <span data-ttu-id="8f1c2-149">![Icono de PowerApps](media/o365-powerapps-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-149">![PowerApps icon](media/o365-powerapps-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-150">PowerApps</span><span class="sxs-lookup"><span data-stu-id="8f1c2-150">PowerApps </span></span>](https://powerapps.microsoft.com) | <span data-ttu-id="8f1c2-151">![Icono de PowerBI](media/o365-powerbi-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-151">![PowerBI icon](media/o365-powerbi-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-152">Power BI</span><span class="sxs-lookup"><span data-stu-id="8f1c2-152">Power BI</span></span>](https://powerbi.microsoft.com)| <span data-ttu-id="8f1c2-153">![Icono de PowerPoint](media/o365-powerpoint-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-153">![PowerPoint icon](media/o365-powerpoint-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-154">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="8f1c2-154">PowerPoint</span></span>](https://products.office.com/powerpoint) | <span data-ttu-id="8f1c2-155">![Icono de proyecto](media/o365-project-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-155">![Project icon](media/o365-project-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-156">Project</span><span class="sxs-lookup"><span data-stu-id="8f1c2-156">Project</span></span>](https://products.office.com/project) 
| <span data-ttu-id="8f1c2-157">![Icono de Publisher](media/o365-publisher-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-157">![Publisher icon](media/o365-publisher-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-158">Publisher</span><span class="sxs-lookup"><span data-stu-id="8f1c2-158">Publisher</span></span>](https://products.office.com/publisher) | <span data-ttu-id="8f1c2-159">![Icono de SharePoint](media/o365-sharepoint-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-159">![SharePoint icon](media/o365-sharepoint-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-160">SharePoint</span><span class="sxs-lookup"><span data-stu-id="8f1c2-160">Sharepoint</span></span>](https://products.office.com/sharepoint) | <span data-ttu-id="8f1c2-161">![Icono de Skype empresarial](media/o365-skypeforbusiness-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-161">![Skype for Business icon](media/o365-skypeforbusiness-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-162">Skype <br> empresarial</span><span class="sxs-lookup"><span data-stu-id="8f1c2-162">Skype for <br> Business</span></span>](https://www.skype.com/business/) | <span data-ttu-id="8f1c2-163">![Icono de notas adhesivas](media/o365-stickynotes-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-163">![Sticky Notes icon](media/o365-stickynotes-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-164">Notas rápidas</span><span class="sxs-lookup"><span data-stu-id="8f1c2-164">Sticky Notes</span></span>](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw) | <span data-ttu-id="8f1c2-165">![Icono de secuencia](media/o365-stream-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-165">![Stream icon](media/o365-stream-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-166">Stream</span><span class="sxs-lookup"><span data-stu-id="8f1c2-166">Stream</span></span>](https://stream.microsoft.com) 
| <span data-ttu-id="8f1c2-167">![Icono de Sway](media/o365-sway-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-167">![Sway icon](media/o365-sway-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-168">Sway</span><span class="sxs-lookup"><span data-stu-id="8f1c2-168">Sway</span></span>](https://sway.com) | <span data-ttu-id="8f1c2-169">![Icono de Teams](media/o365-teams-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-169">![Teams icon](media/o365-teams-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-170">Teams</span><span class="sxs-lookup"><span data-stu-id="8f1c2-170">Teams</span></span>](https://products.office.com/microsoft-teams/group-chat-software) | <span data-ttu-id="8f1c2-171">![Icono de tarea pendiente](media/o365-todo-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-171">![To-Do icon](media/o365-todo-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-172">To-Do</span><span class="sxs-lookup"><span data-stu-id="8f1c2-172">To-Do</span></span>](https://todo.microsoft.com) | <span data-ttu-id="8f1c2-173">![Icono de Visio](media/o365-visio-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-173">![Visio icon](media/o365-visio-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-174">Visio</span><span class="sxs-lookup"><span data-stu-id="8f1c2-174">Visio</span></span>](https://products.office.com/visio/flowchart-software) | <span data-ttu-id="8f1c2-175">![Icono de Word](media/o365-word-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-175">![Word icon](media/o365-word-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-176">Word</span><span class="sxs-lookup"><span data-stu-id="8f1c2-176">Word</span></span>](https://products.office.com/word) 
| <span data-ttu-id="8f1c2-177">![Icono de Yammer](media/o365-yammer-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-177">![Yammer icon](media/o365-yammer-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-178">Yammer<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8f1c2-178">Yammer<sup>2</sup></span></span>](https://products.office.com/yammer/yammer-overview) |

## <a name="supported-powershell-modules"></a><span data-ttu-id="8f1c2-179">Módulos de PowerShell compatibles</span><span class="sxs-lookup"><span data-stu-id="8f1c2-179">Supported PowerShell modules</span></span>

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="8f1c2-180">![Icono de Azure](media/o365-azure-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-180">![Azure icon](media/o365-azure-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-181">PowerShell de <br> Azure ad</span><span class="sxs-lookup"><span data-stu-id="8f1c2-181">Azure AD <br> PowerShell</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | <span data-ttu-id="8f1c2-182">![Icono de Exchange](media/o365-exchange-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-182">![Exchange icon](media/o365-exchange-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-183">PowerShell de <br> Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8f1c2-183">Exchange Online <br> PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps) | <span data-ttu-id="8f1c2-184">![Icono de SharePoint](media/o365-sharepoint-64x64.png)</span><span class="sxs-lookup"><span data-stu-id="8f1c2-184">![SharePoint icon](media/o365-sharepoint-64x64.png)</span></span> <br> [<span data-ttu-id="8f1c2-185">PowerShell de <br> SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8f1c2-185">SharePoint Online <br> PowerShell</span></span>](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell)

> [!NOTE]
> <span data-ttu-id="8f1c2-186"><sup>1</sup> pronto estará disponible la compatibilidad con OneDrive en MacOS.</span><span class="sxs-lookup"><span data-stu-id="8f1c2-186"><sup>1</sup> Support for OneDrive on macOS available soon.</span></span> <br>
> <span data-ttu-id="8f1c2-187"><sup>2</sup> pronto estará disponible la compatibilidad con Yammer en escritorio de Windows y MacOS.</span><span class="sxs-lookup"><span data-stu-id="8f1c2-187"><sup>2</sup> Support for Yammer on Windows Desktop and macOS available soon.</span></span>