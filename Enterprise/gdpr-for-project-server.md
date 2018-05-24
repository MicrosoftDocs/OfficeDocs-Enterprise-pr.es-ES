---
title: RGPD para Project Server
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: ''
localization_priority: Priority
description: Obtenga información sobre cómo cumplir los requisitos de RGPD en Project Server local.
ms.openlocfilehash: 6a630dc4cef2c4117e0ba25497f898d0b8da221b
ms.sourcegitcommit: aabd369fc8b397f9e738374d42d8afd18b96d469
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2018
---
# <a name="gdpr-for-project-server"></a><span data-ttu-id="a9e27-103">RGPD para Project Server</span><span class="sxs-lookup"><span data-stu-id="a9e27-103">Plan for Project Server</span></span>

<span data-ttu-id="a9e27-p101">Project Server usa scripts personalizados para exportar y redactar datos de usuario en Project Web App. El proceso básico es:</span><span class="sxs-lookup"><span data-stu-id="a9e27-p101">Project Server uses custom scripts to export and redact user data in Project Web App. The basic process is:</span></span>

1.  <span data-ttu-id="a9e27-106">Busque los sitios de Project Web App en la granja de servidores.</span><span class="sxs-lookup"><span data-stu-id="a9e27-106">Find the Project Web App sites in your farm.</span></span>

2.  <span data-ttu-id="a9e27-107">Busque los proyectos en cada sitio que contiene el usuario.</span><span class="sxs-lookup"><span data-stu-id="a9e27-107">Find the projects in each site that contain the user.</span></span>

3.  <span data-ttu-id="a9e27-108">Exporte y revise los tipos de datos que desee revisar.</span><span class="sxs-lookup"><span data-stu-id="a9e27-108">Export and review the types of data that you want to review.</span></span>

4.  <span data-ttu-id="a9e27-109">Redacte los datos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a9e27-109">Redact data as needed.</span></span>

<span data-ttu-id="a9e27-110">Estos pasos se tratan con detalle en los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="a9e27-110">These three scenarios are covered in detail in the following articles:</span></span>

- [<span data-ttu-id="a9e27-111">Exportar datos de usuario de Project Server</span><span class="sxs-lookup"><span data-stu-id="a9e27-111">Export user data from Project Server</span></span>](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [<span data-ttu-id="a9e27-112">Eliminar datos de usuario de Project Server</span><span class="sxs-lookup"><span data-stu-id="a9e27-112">Delete user data from Project Server</span></span>](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


<span data-ttu-id="a9e27-113">Tenga en cuenta que Project Server está basado en SharePoint Server y registra eventos en los registros ULS de SharePoint y en la base de datos de uso.</span><span class="sxs-lookup"><span data-stu-id="a9e27-113">Note that Project Server is built on top of SharePoint Server and logs events to the SharePoint ULS logs and Usage database.</span></span>
