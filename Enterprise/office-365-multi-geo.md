---
title: Office 365 Multi-Geo
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: ''
ms.collection: Strat_SP_gtc
localization_priority: Priority
description: Expandir la presencia de Office 365 a varias regiones geográficas con Office 365 Multi-Geo.
ms.openlocfilehash: e216f61806ea5d648519ac7217acf7dbaddd1419
ms.sourcegitcommit: 8ba20f1b1839630a199585da0c83aaebd1ceb9fc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30934101"
---
# <a name="office-365-multi-geo"></a><span data-ttu-id="5fdeb-103">Office 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="5fdeb-103">Video: Introducing Office 365 Multi-Geo</span></span>

<span data-ttu-id="5fdeb-104">Con Office 365 Multi-Geo, su organización puede expandir su presencia en Office 365 a varias regiones geográficas y países dentro de su espacio empresarial existente.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-104">With Multi-Geo capabilities in OneDrive Online, your organization can expand its Office 365 presence to multiple geographic regions and/or countries within your existing tenant. Reach out to your Microsoft Account Team to sign up your Multi-National Company for OneDrive for Business Multi-Geo.</span></span> <span data-ttu-id="5fdeb-105">Póngase en contacto con su equipo de cuentas de Microsoft para registrar su compañía multinacional a Office 365 Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-105">Reach out to your Microsoft Account Team to sign up your Multi-National Company for Office 365 Multi-Geo.</span></span>
  
<span data-ttu-id="5fdeb-106">Con Office 365 Multi-Geo, puede aprovisionar y almacenar los datos en reposo en las ubicaciones geográficas que haya elegido para cumplir los requisitos de residencia de datos y, al mismo tiempo, puede permitir la implementación global de experiencias de productividad modernas para sus empleados.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-106">With OneDrive Multi-Geo, you can provision and store data at rest in the geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global roll out of modern productivity experiences to your workforce.</span></span>

#### <a name="video-introducing-office-365-multi-geo"></a><span data-ttu-id="5fdeb-107">Vídeo: Introducción a Office 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="5fdeb-107">Video: Introducing Office 365 Multi-Geo</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1Yk6B?autoplay=false]

<span data-ttu-id="5fdeb-108">En un entorno multigeográfico, su espacio empresarial de Office 365 cuenta con una ubicación central (donde se aprovisionó originalmente la suscripción a Office 365) y una o varias ubicaciones satélites.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-108">In a Multi-Geo environment, your Office 365 tenant consists of a central location (where your Office 365 subscription was originally provisioned) and one or more satellite locations.</span></span> <span data-ttu-id="5fdeb-109">En un espacio empresarial multigeográfico, la información sobre las ubicaciones geográficas, grupos y la información de usuario, se controla en Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="5fdeb-109">In a multi-geo tenant, the information about geo locations, groups, and user information, is mastered in Azure Active Directory (AAD).</span></span> <span data-ttu-id="5fdeb-110">Como la información del espacio empresarial se controla de forma centralizada y se sincroniza en cada ubicación geográfica, el uso compartido y las experiencias que involucran a todos los empleados de su compañía comparten una conciencia global.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-110">Because your tenant information is mastered centrally and synchronized into each geo location, sharing and experiences involving anyone from your company contain global awareness.</span></span>

![Captura de pantalla del mapa multigeográfico desde el Centro de administración de SharePoint Online](media/multi-geo-world-map.png)

<span data-ttu-id="5fdeb-112">Tenga en cuenta que Office 365 Multi-Geo no está diseñado principalmente para optimizar el rendimiento, sino que para cumplir con los requisitos de residencia de datos.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-112">Note that Office 365 Multi-Geo is not designed for performance optimization cases, it is designed to meet data residency requirements. For information about performance optimization for Office 365, see Network planning and performance tuning for Office 365 or contact your support group.</span></span> <span data-ttu-id="5fdeb-113">Para obtener información sobre la optimización del rendimiento de Office 365, vea [Ajuste de rendimiento y planes de red para Office 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) o póngase en contacto con su grupo de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-113">Note that Office 365 Multi-Geo is not designed for performance optimization cases, it is designed to meet data residency requirements. For information about performance optimization for Office 365, see [Network planning and performance tuning for Office 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) or contact your support group.</span></span>

## <a name="terminology"></a><span data-ttu-id="5fdeb-114">Terminología</span><span class="sxs-lookup"><span data-stu-id="5fdeb-114">Terminology</span></span>

<span data-ttu-id="5fdeb-115">Estos son los términos clave utilizados para describir Office 365 Multi-Geo:</span><span class="sxs-lookup"><span data-stu-id="5fdeb-115">Here are the key terms used in describing Office 365 Multi-Geo:</span></span>

- <span data-ttu-id="5fdeb-116">**Ubicación central**: la ubicación geográfica en la que se ha aprovisionado originalmente el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-116">**Central location** - the geo location where your tenant was originally provisioned.</span></span>
- <span data-ttu-id="5fdeb-117">**Administrador geográfico**: un administrador que puede administrar una o varias ubicaciones satélites especificadas.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-117">**Geo administrator** - An administrator who can administer one or more specified satellite locations.</span></span>
- <span data-ttu-id="5fdeb-118">**Código geográfico**: un código de tres letras de una ubicación geográfica determinada.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-118">**Geo code** - a three-letter code for a given geo location.</span></span>
- <span data-ttu-id="5fdeb-119">**Ubicación geográfica**: una ubicación geográfica que puede usarse en un espacio empresarial multigeográfico para alojar datos, como los buzones de Exchange y los sitios de SharePoint y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-119">**Geo location** – A geographic location that can be used in a multi-geo tenant to host data, including Exchange mailboxes and OneDrive and SharePoint sites.</span></span>
- <span data-ttu-id="5fdeb-120">**Ubicación de datos preferida (PDL)**: una propiedad de usuario que establece el administrador e indica la ubicación geográfica donde se deben aprovisionar los buzones de Exchange de usuarios y OneDrive.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-120">**Preferred Data Location (PDL)** – A user property set by the administrator that indicates where the geo location where the users Exchange mailbox and OneDrive should be provisioned.</span></span> <span data-ttu-id="5fdeb-121">La PDL también determina dónde aprovisionar sitios de SharePoint creados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-121">The PDL also determines where SharePoint sites that are created by the user are provisioned.</span></span>
- <span data-ttu-id="5fdeb-122">**Ubicación de satélite**: las ubicaciones geográficas donde están habilitadas las cargas de trabajo compatibles geográficamente de Office 365 (Exchange, OneDrive y SharePoint) en un espacio empresarial multigeográfico.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-122">**Satellite location** – The geo locations where the geo-aware Office 365 workloads (SharePoint, OneDrive, and Exchange) are enabled in a multi-geo tenant.</span></span>
- <span data-ttu-id="5fdeb-123">**Espacio empresarial**: la representación de una organización de Office 365, que suele tener uno o más dominios asociados (por ejemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="5fdeb-123">Tenant – An organization's representation in the Office 365 cloud which typically has one or more domains associated with it (for example, .</span></span>

## <a name="office-365-multi-geo-availability"></a><span data-ttu-id="5fdeb-124">Disponibilidad de Office 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="5fdeb-124">Office 365 Multi-Geo availability</span></span>

<span data-ttu-id="5fdeb-125">Actualmente, se ofrece Office 365 Multi-Geo en estos países y regiones:</span><span class="sxs-lookup"><span data-stu-id="5fdeb-125">OneDrive Multi-Geo is currently offered in these regions and countries:</span></span>

[!INCLUDE [Office 365 Multi-Geo locations](includes/office-365-multi-geo-locations.md)]

## <a name="getting-started"></a><span data-ttu-id="5fdeb-126">Introducción</span><span class="sxs-lookup"><span data-stu-id="5fdeb-126">Getting started</span></span>

<span data-ttu-id="5fdeb-127">Siga estos pasos para empezar a usar Multi-Geo:</span><span class="sxs-lookup"><span data-stu-id="5fdeb-127">Follow these steps to get started:</span></span>

1. <span data-ttu-id="5fdeb-p105">Trabaje con el equipo de cuenta para agregar el plan de servicio _Multi-Geo Capabilities in Office 365_ (Capacidades multigeográficas de Office 365). Le guiará para que agregue el número de licencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-p105">Work with your account team to add the _Multi-Geo Capabilities in Office 365_ service plan. They will guide you to add the number of licenses needed.</span></span>

   <span data-ttu-id="5fdeb-130">Antes de empezar a usar Office 365 Multi-Geo, Microsoft necesita configurar el espacio empresarial de Exchange Online para la compatibilidad con Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-130">Before you can start using Office 365 Multi-Geo, Microsoft needs to configure your Exchange Online tenant for multi-geo support.</span></span> <span data-ttu-id="5fdeb-131">Este proceso de configuración única se activa después de pedir el plan de servicio de las *Capacidades multigeográficas de Office 365* y después de que las licencias se muestren en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-131">This one-time configuration process is triggered after you order the *Multi-Geo Capabilities in Office 365* service plan and the licenses show up in your tenant.</span></span> <span data-ttu-id="5fdeb-132">Recibirá notificaciones en el [centro de mensajes de Office 365](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) cuando se apliquen las licencias Multi-Geo y, después, puede empezar a configurar y usar las capacidades de Office 365 Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="5fdeb-132">You'll receive notifications in the [Office 365 message center](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) once your Multi-Geo licenses are applied and you then may begin configuring and using your Office 365 Multi-Geo capabilities.</span></span>

2. <span data-ttu-id="5fdeb-133">Lea [Planificar el entorno multigeográfico](plan-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="5fdeb-133">Read [Plan your multi-geo environment](plan-for-multi-geo.md).</span></span>

3. <span data-ttu-id="5fdeb-134">Obtenga información sobre cómo [administrar un entorno multigeográfico](administering-a-multi-geo-environment.md) y [cómo los usuarios experimentarán el entorno](multi-geo-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="5fdeb-134">Learn about [administering a multi-geo environment](administering-a-multi-geo-environment.md) and [how your users will experience the environment](multi-geo-user-experience.md).</span></span>

4. <span data-ttu-id="5fdeb-135">Cuando esté listo para configurar Office 365 Multi-Geo, [configure su espacio empresarial multigeográfico](multi-geo-tenant-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="5fdeb-135">When you are ready to set up Office 365 Multi-Geo, [configure your tenant for multi-geo](multi-geo-tenant-configuration.md).</span></span>

5. <span data-ttu-id="5fdeb-136">[Configure la búsqueda](configure-search-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="5fdeb-136">[](configure-search-for-multi-geo.md)Set up people search</span></span>

## <a name="see-also"></a><span data-ttu-id="5fdeb-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fdeb-137">See also</span></span>

[<span data-ttu-id="5fdeb-138">Aka.ms/GoMultiGeo </span><span class="sxs-lookup"><span data-stu-id="5fdeb-138">Aka.ms/GoMultiGeo </span></span>](https://Aka.ms/GoMultiGeo)

[<span data-ttu-id="5fdeb-139">Capacidades multigeográficas de OneDrive y SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5fdeb-139">Multi-Geo Capabilities in OneDrive and SharePoint Online in Office 365</span></span>](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-office-365.md)

[<span data-ttu-id="5fdeb-140">Capacidades multigeográficas de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5fdeb-140">NoteFor information on Multi-Geo Capabilities, see Multi-Geo Capabilities in Exchange Online.</span></span>](multi-geo-capabilities-in-exchange-online.md)