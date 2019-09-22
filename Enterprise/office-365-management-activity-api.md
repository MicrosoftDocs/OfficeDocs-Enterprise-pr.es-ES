---
title: API de Actividad de administración de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-analytics
description: Un breve resumen sobre la API de actividad de administración de Office 365.
ms.openlocfilehash: eb7da1aaade80bd689ba6ec518272d9e0d2d4d05
ms.sourcegitcommit: 55a046bdf49bf7c62ab74da73be1fd1cf6f0ad86
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37067805"
---
# <a name="office-365-management-activity-api"></a><span data-ttu-id="9d2c8-103">API de Actividad de administración de Office 365</span><span class="sxs-lookup"><span data-stu-id="9d2c8-103">Office 365 Management Activity API</span></span>

<span data-ttu-id="9d2c8-104">Microsoft proporciona Reporting Services que puede usar para obtener información de transacciones agregada sobre su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9d2c8-104">Microsoft provides reporting services you can use to obtain aggregated transactional information about your Office 365 tenant.</span></span> <span data-ttu-id="9d2c8-105">La [API de actividad de administración 365 de Office](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) usa un diseño RESTful estándar del sector y OAuth v2 para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="9d2c8-105">The [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) uses an industry-standard RESTful design and OAuth v2 for authentication.</span></span> <span data-ttu-id="9d2c8-106">Esto hace que sea fácil empezar a experimentar con la recuperación de datos y a su recopilación en herramientas y aplicaciones de visualización.</span><span class="sxs-lookup"><span data-stu-id="9d2c8-106">This makes it easy to start experimenting with retrieving data and ingesting it into visualization tools and applications.</span></span> <span data-ttu-id="9d2c8-107">La API proporciona una fuente de datos con información sobre el usuario, el administrador, las operaciones y la actividad de seguridad en Office 365.</span><span class="sxs-lookup"><span data-stu-id="9d2c8-107">The API provides a data feed with information about user, administrator, operations, and security activity in Office 365.</span></span> <span data-ttu-id="9d2c8-108">Los datos pueden conservarse con fines regulatorios o combinarse con datos de registros que se retienen de una infraestructura local u otros orígenes.</span><span class="sxs-lookup"><span data-stu-id="9d2c8-108">The data can be kept for regulatory purposes, or combined with log data procured from an on-premises infrastructure or other sources.</span></span> <span data-ttu-id="9d2c8-109">Esto ayuda a crear una solución de supervisión para operaciones, seguridad y cumplimiento de normas en toda la empresa.</span><span class="sxs-lookup"><span data-stu-id="9d2c8-109">This helps build a monitoring solution for operations, security, and compliance across the enterprise.</span></span>

<span data-ttu-id="9d2c8-110">La API de actividad de administración de Office 365 proporciona información sobre diversas acciones y eventos de usuario, administrador, sistema y directiva de los registros de actividad de Office 365 y Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9d2c8-110">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="9d2c8-111">La API proporciona un esquema de auditoría coherente con más de 10 campos comunes en todos los servicios.</span><span class="sxs-lookup"><span data-stu-id="9d2c8-111">The API provides a consistent audit schema with over 10 fields common across all the services.</span></span> <span data-ttu-id="9d2c8-112">La API permite que las organizaciones realicen conexiones entre eventos fácilmente y habilita nuevas formas de razonamiento sobre los datos.</span><span class="sxs-lookup"><span data-stu-id="9d2c8-112">The API allows organizations to make easy connections between events, and enables new ways to reason over the data.</span></span>

<span data-ttu-id="9d2c8-113">Docenas de proveedores de software independientes (ISV) asociados con Microsoft y han creado soluciones basadas en la API.</span><span class="sxs-lookup"><span data-stu-id="9d2c8-113">Dozens of Independent Software Vendors (ISVs) partnered with Microsoft and have built solutions based on the API.</span></span> <span data-ttu-id="9d2c8-114">Algunas soluciones se centran únicamente en los datos de Office 365 y en otros datos de origen de varios proveedores de nube y sistemas locales para crear una vista unificada de las operaciones, la seguridad y la actividad relacionada con el cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9d2c8-114">Some solutions focus solely on Office 365 data and others source data from multiple cloud providers and on-premises systems to create a unified view of operations, security, and compliance-related activity.</span></span> 

<span data-ttu-id="9d2c8-115">Para obtener más información, vea la referencia de la [API de actividad de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="9d2c8-115">For more information, see the [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>