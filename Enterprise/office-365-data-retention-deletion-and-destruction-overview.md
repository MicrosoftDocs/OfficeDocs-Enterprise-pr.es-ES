---
title: Retención, eliminación y destrucción de datos en Office 365
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
- M365-security-compliance
description: Información general sobre las directivas de Microsoft para Office 365 relativas a la retención, eliminación y destrucción de datos.
ms.openlocfilehash: 08b04e4fec762249208acb626fa20562ffecb82f
ms.sourcegitcommit: 55a046bdf49bf7c62ab74da73be1fd1cf6f0ad86
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37067846"
---
# <a name="data-retention-deletion-and-destruction-in-office-365"></a><span data-ttu-id="6797d-103">Retención, eliminación y destrucción de datos en Office 365</span><span class="sxs-lookup"><span data-stu-id="6797d-103">Data Retention, Deletion, and Destruction in Office 365</span></span>

<span data-ttu-id="6797d-104">Microsoft tiene una directiva estándar de tratamiento de datos para Office 365 que especifica cuánto tiempo se conservan los datos de los clientes tras la eliminación.</span><span class="sxs-lookup"><span data-stu-id="6797d-104">Microsoft has a Data Handling Standard policy for Office 365 that specifies how long customer data is retained after deletion.</span></span> <span data-ttu-id="6797d-105">Normalmente, hay dos escenarios en los que se eliminan los datos de los clientes:</span><span class="sxs-lookup"><span data-stu-id="6797d-105">There are generally two scenarios in which customer data is deleted:</span></span>

- <span data-ttu-id="6797d-106">**Eliminación activa:** El inquilino tiene una suscripción activa y un usuario elimina datos o los administradores eliminan los datos proporcionados por un usuario.</span><span class="sxs-lookup"><span data-stu-id="6797d-106">**Active Deletion:** The tenant has an active subscription and a user deletes data, or administrators delete data provided by a user.</span></span>
- <span data-ttu-id="6797d-107">**Eliminación pasiva:** Finaliza la suscripción de inquilino.</span><span class="sxs-lookup"><span data-stu-id="6797d-107">**Passive Deletion:** The tenant subscription ends.</span></span>

## <a name="data-retention"></a><span data-ttu-id="6797d-108">Retención de datos</span><span class="sxs-lookup"><span data-stu-id="6797d-108">Data Retention</span></span>

<span data-ttu-id="6797d-109">Para cada uno de estos escenarios de eliminación, en la tabla siguiente se muestra el período de retención de datos máximo, por categoría de datos y clasificación:</span><span class="sxs-lookup"><span data-stu-id="6797d-109">For each of these deletion scenarios, the following table shows the maximum data retention period, by data category and classification:</span></span>

| <span data-ttu-id="6797d-110">Categoría de datos</span><span class="sxs-lookup"><span data-stu-id="6797d-110">Data Category</span></span> | <span data-ttu-id="6797d-111">Clasificación de datos</span><span class="sxs-lookup"><span data-stu-id="6797d-111">Data Classification</span></span> | <span data-ttu-id="6797d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6797d-112">Description</span></span> | <span data-ttu-id="6797d-113">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6797d-113">Examples</span></span> | <span data-ttu-id="6797d-114">Período de retención</span><span class="sxs-lookup"><span data-stu-id="6797d-114">Retention Period</span></span> |
|-----------------|-----------------|-----------------|----------------------------------|-------------------------------|
| <span data-ttu-id="6797d-115">Datos de cliente</span><span class="sxs-lookup"><span data-stu-id="6797d-115">Customer Data</span></span> | <span data-ttu-id="6797d-116">Contenido del cliente</span><span class="sxs-lookup"><span data-stu-id="6797d-116">Customer Content</span></span>| <span data-ttu-id="6797d-117">Contenido proporcionado directamente/creado por administradores y usuarios</span><span class="sxs-lookup"><span data-stu-id="6797d-117">Content directly provided/created by admins and users</span></span> <br><br> <span data-ttu-id="6797d-118">Incluye todo el texto, sonido, vídeo, archivos de imagen y software creado y almacenado en centros de datos de Microsoft cuando se usan los servicios de Office 365</span><span class="sxs-lookup"><span data-stu-id="6797d-118">Includes all text, sound, video, image files, and software created and stored in Microsoft data centers when using the services in Office 365</span></span> | <span data-ttu-id="6797d-119">Algunos ejemplos de las aplicaciones de Office 365 más usadas que permiten a los usuarios crear datos son Word, Excel, PowerPoint, Outlook y OneNote</span><span class="sxs-lookup"><span data-stu-id="6797d-119">Examples of the most commonly used Office 365 applications that allow users to author data include Word, Excel, PowerPoint, Outlook, and OneNote</span></span> <br><br> <span data-ttu-id="6797d-120">El contenido del cliente también incluye secretos de propiedad del cliente o proporcionados (contraseñas, certificados, claves de cifrado, claves de almacenamiento)</span><span class="sxs-lookup"><span data-stu-id="6797d-120">Customer content also includes customer-owned/provided secrets (passwords, certificates, encryption keys, storage keys)</span></span> | <span data-ttu-id="6797d-121">**Escenario de eliminación activa:** como máximo 30 días</span><span class="sxs-lookup"><span data-stu-id="6797d-121">**Active Deletion Scenario:** at most 30 days</span></span> <br><br> <span data-ttu-id="6797d-122">**Escenario de eliminación pasiva:** como máximo 180 días</span><span class="sxs-lookup"><span data-stu-id="6797d-122">**Passive Deletion Scenario:** at most 180 days</span></span> |
| <span data-ttu-id="6797d-123">Datos de cliente</span><span class="sxs-lookup"><span data-stu-id="6797d-123">Customer Data</span></span> | <span data-ttu-id="6797d-124">Información de identificación del usuario final (EUII)</span><span class="sxs-lookup"><span data-stu-id="6797d-124">End User Identifiable Information (EUII)</span></span> | <span data-ttu-id="6797d-125">Datos que identifican o pueden usarse para identificar al usuario de un servicio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6797d-125">Data that identifies or could be used to identify the user of a Microsoft service.</span></span> <span data-ttu-id="6797d-126">EUII no incluye contenido del cliente</span><span class="sxs-lookup"><span data-stu-id="6797d-126">EUII does not contain Customer content</span></span> | <span data-ttu-id="6797d-127">Nombre de usuario o nombre para mostrar (Dominio\nombre de usuario)</span><span class="sxs-lookup"><span data-stu-id="6797d-127">User name or display name (DOMAIN\UserName)</span></span> <br><br> <span data-ttu-id="6797d-128">Nombre principal de usuario (nombre @ dominio)</span><span class="sxs-lookup"><span data-stu-id="6797d-128">User principal name (name@domain)</span></span> <br><br>  <span data-ttu-id="6797d-129">Direcciones IP específicas del usuario</span><span class="sxs-lookup"><span data-stu-id="6797d-129">User-specific IP addresses</span></span> | <span data-ttu-id="6797d-130">**Escenario de eliminación activa:** como máximo de 180 días (solo una acción de administrador de inquilinos)</span><span class="sxs-lookup"><span data-stu-id="6797d-130">**Active Deletion Scenario:** at most 180 days (only a tenant administrator action)</span></span> <br><br> <span data-ttu-id="6797d-131">**Escenario de eliminación pasiva:** como máximo 180 días</span><span class="sxs-lookup"><span data-stu-id="6797d-131">**Passive Deletion Scenario:** at most 180 days</span></span> |
| <span data-ttu-id="6797d-132">Datos personales</span><span class="sxs-lookup"><span data-stu-id="6797d-132">Personal Data</span></span> <br> <span data-ttu-id="6797d-133">(datos no incluidos en los datos del cliente)</span><span class="sxs-lookup"><span data-stu-id="6797d-133">(data not included in Customer Data)</span></span> | <span data-ttu-id="6797d-134">Identificadores de seudónimos de usuario final (EUPI)</span><span class="sxs-lookup"><span data-stu-id="6797d-134">End User Pseudonymous Identifiers (EUPI)</span></span> | <span data-ttu-id="6797d-135">Identificador creado por Microsoft ligado al usuario de un servicio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6797d-135">An identifier created by Microsoft tied to the user of a Microsoft service.</span></span> <span data-ttu-id="6797d-136">Cuando se combina con otra información, como una tabla de asignación, EUPI identifica al usuario final</span><span class="sxs-lookup"><span data-stu-id="6797d-136">When combined with other information, such as a mapping table, EUPI identifies the end user</span></span> <br><br> <span data-ttu-id="6797d-137">EUPI no contiene información que el cliente ha cargado o creado</span><span class="sxs-lookup"><span data-stu-id="6797d-137">EUPI does not contain information uploaded or created by the customer</span></span> | <span data-ttu-id="6797d-138">GUID de usuario, PUIDs o SID</span><span class="sxs-lookup"><span data-stu-id="6797d-138">User GUIDs, PUIDs, or SIDs</span></span> <br><br> <span data-ttu-id="6797d-139">Identificadores de sesión</span><span class="sxs-lookup"><span data-stu-id="6797d-139">Session IDs</span></span> | <span data-ttu-id="6797d-140">**Escenario de eliminación activa:** como máximo 30 días</span><span class="sxs-lookup"><span data-stu-id="6797d-140">**Active Deletion Scenario:** at most 30 days</span></span> <br><br> <span data-ttu-id="6797d-141">**Escenario de eliminación pasiva:** como máximo 180 días</span><span class="sxs-lookup"><span data-stu-id="6797d-141">**Passive Deletion Scenario:** at most 180 days</span></span> |

## <a name="subscription-retention"></a><span data-ttu-id="6797d-142">Retención de suscripción</span><span class="sxs-lookup"><span data-stu-id="6797d-142">Subscription Retention</span></span>

<span data-ttu-id="6797d-143">En el término de una suscripción activa, un suscriptor puede obtener acceso, extraer o eliminar los datos de los clientes almacenados en Office 365.</span><span class="sxs-lookup"><span data-stu-id="6797d-143">In the term of an active subscription, a subscriber can access, extract, or delete customer data stored in Office 365.</span></span> <span data-ttu-id="6797d-144">Si una suscripción de pago finaliza o se termina, Microsoft conserva los datos del cliente almacenados en Office 365 en una cuenta de funciones limitadas durante 90 días para permitir que el suscriptor Extraiga los datos.</span><span class="sxs-lookup"><span data-stu-id="6797d-144">If a paid subscription ends or is terminated, Microsoft retains customer data stored in Office 365 in a limited-function account for 90 days to enable the subscriber to extract the data.</span></span> <span data-ttu-id="6797d-145">Una vez finalizado el período de retención de 90 días, Microsoft deshabilita la cuenta y elimina los datos del cliente.</span><span class="sxs-lookup"><span data-stu-id="6797d-145">After the 90-day retention period ends, Microsoft disables the account and deletes the customer data.</span></span> <span data-ttu-id="6797d-146">No más de 180 días tras la expiración o cancelación de una suscripción a Office 365, Microsoft deshabilita la cuenta y elimina todos los datos del cliente de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="6797d-146">No more than 180 days after expiration or termination of a subscription to Office 365, Microsoft disables the account and deletes all customer data from the account.</span></span> <span data-ttu-id="6797d-147">Una vez que ha transcurrido el período de retención máximo de los datos, los datos se representan comercialmente no recuperables.</span><span class="sxs-lookup"><span data-stu-id="6797d-147">Once the maximum retention period for any data has elapsed, the data is rendered commercially unrecoverable.</span></span>

<span data-ttu-id="6797d-148">Para una prueba gratuita, la cuenta pasa a un estado de gracia durante 30 días en la mayoría de países y regiones.</span><span class="sxs-lookup"><span data-stu-id="6797d-148">For a free trial, your account moves into a grace status for 30 days in most countries and regions.</span></span> <span data-ttu-id="6797d-149">Durante este período de gracia, puede comprar Office 365.</span><span class="sxs-lookup"><span data-stu-id="6797d-149">During this grace period, you can purchase Office 365.</span></span> <span data-ttu-id="6797d-150">Si decide no comprar Office 365, puede cancelar la versión de prueba o dejar que expire el período de gracia y se elimine la información y los datos de la cuenta de prueba.</span><span class="sxs-lookup"><span data-stu-id="6797d-150">If you decide not to buy Office 365, you can either cancel your trial or let the grace period expire, and your trial account information and data is deleted.</span></span>

## <a name="expedited-deletion"></a><span data-ttu-id="6797d-151">Eliminación urgente</span><span class="sxs-lookup"><span data-stu-id="6797d-151">Expedited Deletion</span></span>

<span data-ttu-id="6797d-152">Para cualquier suscripción, un suscriptor puede ponerse en contacto con el soporte técnico de Microsoft y solicitar el aprovisionamiento de suscripciones urgentes.</span><span class="sxs-lookup"><span data-stu-id="6797d-152">For any subscription, a subscriber can contact Microsoft Support and request expedited subscription de-provisioning.</span></span> <span data-ttu-id="6797d-153">En este proceso, todos los datos de usuario se eliminan tres días después de que el administrador escriba el código de bloqueo proporcionado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6797d-153">In this process, all user data is deleted three days after the administrator enters the lockout code provided by Microsoft.</span></span> <span data-ttu-id="6797d-154">Esto incluye datos en SharePoint Online y Exchange Online suspendidos o almacenados en buzones inactivos.</span><span class="sxs-lookup"><span data-stu-id="6797d-154">This includes data in SharePoint Online and Exchange Online under hold or stored in inactive mailboxes.</span></span>

<span data-ttu-id="6797d-155">Para obtener más información acerca de la deshabilitación de aprovisionamiento rápido, consulte [Cancelar Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a).</span><span class="sxs-lookup"><span data-stu-id="6797d-155">For more information on expedited de-provisioning, see [Cancel Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a).</span></span>

## <a name="related-links"></a><span data-ttu-id="6797d-156">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="6797d-156">Related Links</span></span>
- [<span data-ttu-id="6797d-157">Destrucción de datos</span><span class="sxs-lookup"><span data-stu-id="6797d-157">Data Destruction</span></span>](office-365-data-destruction.md)
- [<span data-ttu-id="6797d-158">Inmutabilidad en Office 365</span><span class="sxs-lookup"><span data-stu-id="6797d-158">Immutability in Office 365</span></span>](office-365-data-immutability.md)
- [<span data-ttu-id="6797d-159">Eliminación de datos en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6797d-159">Exchange Online Data Deletion</span></span>](office-365-exchange-online-data-deletion.md)
- [<span data-ttu-id="6797d-160">Eliminación de datos en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6797d-160">SharePoint Online Data Deletion</span></span>](office-365-sharepoint-online-data-deletion.md)
- [<span data-ttu-id="6797d-161">Eliminación de datos en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="6797d-161">Skype for Business Data Deletion</span></span>](office-365-skype-data-deletion.md)