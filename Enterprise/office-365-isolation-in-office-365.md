---
title: Aislamiento y control de acceso de Office 365 en Office 365
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
description: 'Resumen: una explicación del aislamiento y el control de acceso dentro de las distintas aplicaciones de Office 365.'
ms.openlocfilehash: 541aef20e885f6d7fbd505ffe2fe32a8525999d4
ms.sourcegitcommit: 55a046bdf49bf7c62ab74da73be1fd1cf6f0ad86
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37067810"
---
# <a name="isolation-and-access-control-in-office-365"></a><span data-ttu-id="cb07c-103">Aislamiento y Control de acceso en Office 365</span><span class="sxs-lookup"><span data-stu-id="cb07c-103">Isolation and Access Control in Office 365</span></span>

<span data-ttu-id="cb07c-104">Azure Active Directory y Office 365 usan un modelo de datos muy complejo que incluye decenas de servicios, cientos de entidades, miles de relaciones y decenas de miles de atributos.</span><span class="sxs-lookup"><span data-stu-id="cb07c-104">Azure Active Directory and Office 365 use a highly complex data model that includes tens of services, hundreds of entities, thousands of relationships, and tens of thousands of attributes.</span></span> <span data-ttu-id="cb07c-105">En un nivel alto, Azure Active Directory y los directorios de servicio son los contenedores de los inquilinos y los destinatarios que se mantienen sincronizados mediante protocolos de replicación basados en el estado.</span><span class="sxs-lookup"><span data-stu-id="cb07c-105">At a high level, Azure Active Directory and the service directories are the containers of tenants and recipients kept in sync using state-based replication protocols.</span></span> <span data-ttu-id="cb07c-106">Además de la información de directorio contenida en Azure Active Directory, cada una de las cargas de trabajo de servicio tiene su propia infraestructura de servicios de directorio.</span><span class="sxs-lookup"><span data-stu-id="cb07c-106">In addition to the directory information held within Azure Active Directory, each of the service workloads have their own directory services infrastructure.</span></span>
 
![Sincronización de datos del espacio empresarial de Office 365](media/office-365-isolation-tenant-data-sync.png)

<span data-ttu-id="cb07c-108">Dentro de este modelo, no hay un único origen de datos de directorio.</span><span class="sxs-lookup"><span data-stu-id="cb07c-108">Within this model, there is no single source of directory data.</span></span> <span data-ttu-id="cb07c-109">Sistemas específicos que poseen partes individuales de datos, pero ningún sistema único contiene todos los datos.</span><span class="sxs-lookup"><span data-stu-id="cb07c-109">Specific systems own individual pieces of data, but no single system holds all the data.</span></span> <span data-ttu-id="cb07c-110">Los servicios de Office 365 cooperan con Azure Active Directory en este modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="cb07c-110">Office 365 services cooperate with Azure Active Directory in this data model.</span></span> <span data-ttu-id="cb07c-111">Azure Active Directory es el "sistema de verdad" para datos compartidos, que normalmente son datos pequeños y estáticos que usan todos los servicios.</span><span class="sxs-lookup"><span data-stu-id="cb07c-111">Azure Active Directory is the "system of truth" for shared data, which is typically small and static data used by every service.</span></span> <span data-ttu-id="cb07c-112">El modelo federado usado en Office 365 y Azure Active Directory proporciona la vista compartida de los datos.</span><span class="sxs-lookup"><span data-stu-id="cb07c-112">The federated model used within Office 365 and Azure Active Directory provides the shared view of the data.</span></span>

<span data-ttu-id="cb07c-113">Office 365 usa el almacenamiento físico y el almacenamiento en la nube de Azure.</span><span class="sxs-lookup"><span data-stu-id="cb07c-113">Office 365 uses both physical storage and Azure cloud storage.</span></span> <span data-ttu-id="cb07c-114">Exchange Online (incluida la protección en línea de Exchange) y Skype empresarial usan su propio almacenamiento para los datos de clientes.</span><span class="sxs-lookup"><span data-stu-id="cb07c-114">Exchange Online (including Exchange Online Protection) and Skype for Business use their own storage for customer data.</span></span> <span data-ttu-id="cb07c-115">SharePoint Online usa el almacenamiento de SQL Server y Azure Storage, de ahí la necesidad de un aislamiento adicional de los datos de cliente en el nivel de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="cb07c-115">SharePoint Online uses both SQL Server storage and Azure Storage, hence the need for additional isolation of customer data at the storage level.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="cb07c-116">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cb07c-116">Exchange Online</span></span>

<span data-ttu-id="cb07c-117">Exchange Online almacena los datos de clientes dentro de los buzones.</span><span class="sxs-lookup"><span data-stu-id="cb07c-117">Exchange Online stores customer data within mailboxes.</span></span> <span data-ttu-id="cb07c-118">Los buzones de correo se hospedan en bases de datos del motor de almacenamiento extensible (ESE) denominadas bases de datos de buzones.</span><span class="sxs-lookup"><span data-stu-id="cb07c-118">Mailboxes are hosted within Extensible Storage Engine (ESE) databases called mailbox databases.</span></span> <span data-ttu-id="cb07c-119">Esto incluye los buzones de usuario, los buzones vinculados, los buzones compartidos y los buzones de carpetas públicas.</span><span class="sxs-lookup"><span data-stu-id="cb07c-119">This includes user mailboxes, linked mailboxes, shared mailboxes, and public folder mailboxes.</span></span> <span data-ttu-id="cb07c-120">Los buzones de usuario incluyen contenido guardado de Skype empresarial, como historiales de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="cb07c-120">User mailboxes include saved Skype for Business content, such as conversation histories.</span></span>

<span data-ttu-id="cb07c-121">El contenido de los buzones de usuario incluye:</span><span class="sxs-lookup"><span data-stu-id="cb07c-121">User mailbox content includes:</span></span>

- <span data-ttu-id="cb07c-122">Mensajes de correo electrónico y datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="cb07c-122">Emails and email attachments</span></span>
- <span data-ttu-id="cb07c-123">Información de disponibilidad y calendario</span><span class="sxs-lookup"><span data-stu-id="cb07c-123">Calendaring and free/busy information</span></span>
- <span data-ttu-id="cb07c-124">Contactos</span><span class="sxs-lookup"><span data-stu-id="cb07c-124">Contacts</span></span>
- <span data-ttu-id="cb07c-125">Tareas</span><span class="sxs-lookup"><span data-stu-id="cb07c-125">Tasks</span></span>
- <span data-ttu-id="cb07c-126">Notas</span><span class="sxs-lookup"><span data-stu-id="cb07c-126">Notes</span></span>
- <span data-ttu-id="cb07c-127">Grupos</span><span class="sxs-lookup"><span data-stu-id="cb07c-127">Groups</span></span>
- <span data-ttu-id="cb07c-128">Datos de inferencia</span><span class="sxs-lookup"><span data-stu-id="cb07c-128">Inference data</span></span>

<span data-ttu-id="cb07c-129">Cada base de datos de buzones de correo de Exchange Online contiene buzones de varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="cb07c-129">Each mailbox database within Exchange Online contains mailboxes from multiple tenants.</span></span> <span data-ttu-id="cb07c-130">Un código de autorización protege cada buzón de correo, incluido en un arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="cb07c-130">An authorization code secures each mailbox, including within a tenancy.</span></span> <span data-ttu-id="cb07c-131">De forma predeterminada, solo el usuario asignado tiene acceso a un buzón.</span><span class="sxs-lookup"><span data-stu-id="cb07c-131">By default, only the assigned user has access to a mailbox.</span></span> <span data-ttu-id="cb07c-132">La lista de control de acceso (ACL) que protege a un buzón de correo contiene una identidad autenticada por Azure Active Directory en el nivel de espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="cb07c-132">The access control list (ACL) that secures a mailbox contains an identity authenticated by Azure Active Directory at the tenant level.</span></span> <span data-ttu-id="cb07c-133">Los buzones de cada inquilino están limitados a identidades autenticadas en el proveedor de autenticación del inquilino, que solo incluye a los usuarios de ese inquilino.</span><span class="sxs-lookup"><span data-stu-id="cb07c-133">The mailboxes for each tenant are limited to identities authenticated against the tenant's authentication provider, which includes only users from that tenant.</span></span> <span data-ttu-id="cb07c-134">El contenido del espacio empresarial A no puede ser obtenido de ninguna manera por los usuarios del inquilino B, a menos que lo apruebe explícitamente el inquilino A.</span><span class="sxs-lookup"><span data-stu-id="cb07c-134">Content in tenant A cannot in any way be obtained by users in tenant B, unless explicitly approved by tenant A.</span></span>

## <a name="skype-for-business"></a><span data-ttu-id="cb07c-135">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="cb07c-135">Skype for Business</span></span>

<span data-ttu-id="cb07c-136">Skype empresarial almacena datos en varios lugares:</span><span class="sxs-lookup"><span data-stu-id="cb07c-136">Skype for Business stores data in various places:</span></span>

- <span data-ttu-id="cb07c-137">La información de usuarios y cuentas, que incluye los extremos de conexión, los identificadores de inquilino, los planes de marcado, la configuración de itinerancia, el estado de presencia, las listas de contactos, etc., se almacena en los servidores de Active Directory de Skype empresarial y en varios servidores de base de datos de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="cb07c-137">User and account information, which includes connection endpoints, tenant IDs, dial plans, roaming settings, presence state, contact lists, etc., is stored in the Skype for Business Active Directory servers, and in various Skype for Business database servers.</span></span> <span data-ttu-id="cb07c-138">Las listas de contactos se almacenan en el buzón de correo de Exchange online del usuario si el usuario está habilitado para ambos productos o en servidores de Skype empresarial si el usuario no lo está.</span><span class="sxs-lookup"><span data-stu-id="cb07c-138">Contact lists are stored in the user's Exchange Online mailbox if the user is enabled for both products, or on Skype for Business servers if the user is not.</span></span> <span data-ttu-id="cb07c-139">Los servidores de base de datos de Skype empresarial no tienen particiones por inquilino, pero el aislamiento de datos multiinquilino se aplica mediante el control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="cb07c-139">Skype for Business database servers are not partitioned per-tenant, but multi-tenancy isolation of data is enforced through role-based access control (RBAC).</span></span>
- <span data-ttu-id="cb07c-140">El contenido de la reunión y los datos cargados se almacenan en recursos compartidos del sistema de archivos distribuido (DFS).</span><span class="sxs-lookup"><span data-stu-id="cb07c-140">Meeting content and uploaded data is stored on Distributed File System (DFS) shares.</span></span> <span data-ttu-id="cb07c-141">Este contenido también se puede archivar en Exchange Online si está habilitado.</span><span class="sxs-lookup"><span data-stu-id="cb07c-141">This content can also be archived in Exchange Online if enabled.</span></span> <span data-ttu-id="cb07c-142">Los recursos compartidos DFS no tienen particiones por espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="cb07c-142">The DFS shares are not partitioned per-tenant.</span></span> <span data-ttu-id="cb07c-143">el contenido está protegido con ACL y la función de multiinquilino se aplica a través de RBAC.</span><span class="sxs-lookup"><span data-stu-id="cb07c-143">the content is secured with ACLs and multi-tenancy is enforced through RBAC.</span></span>
- <span data-ttu-id="cb07c-144">Los registros de detalles de llamadas, que son el historial de actividades, como el historial de llamadas, las sesiones de mensajería instantánea, el uso compartido de aplicaciones, el historial de mi, etc., también se pueden almacenar en Exchange Online, pero la mayoría de los registros de detalles de llamadas se almacenan temporalmente en los servidores de registro de detalles de llamadas (CDR).</span><span class="sxs-lookup"><span data-stu-id="cb07c-144">Call detail records, which are the activity history, such as call history, IM sessions, application sharing, IM history, etc., can also be stored in Exchange Online, but most call detail records are temporarily stored on call detail record (CDR) servers.</span></span> <span data-ttu-id="cb07c-145">El contenido no se divide en particiones por inquilino, pero la función de multiinquilino se aplica a través de RBAC.</span><span class="sxs-lookup"><span data-stu-id="cb07c-145">Content is not partitioned per tenant, but multi-tenancy is enforced through RBAC.</span></span>

## <a name="sharepoint-online"></a><span data-ttu-id="cb07c-146">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb07c-146">SharePoint Online</span></span>

<span data-ttu-id="cb07c-147">SharePoint Online tiene varios mecanismos independientes que proporcionan aislamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="cb07c-147">SharePoint Online has several independent mechanisms that provide data isolation.</span></span> <span data-ttu-id="cb07c-148">Almacena los objetos como código abstracto dentro de las bases de datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cb07c-148">It stores objects as abstracted code within application databases.</span></span> <span data-ttu-id="cb07c-149">Por ejemplo, cuando un usuario carga un archivo en SharePoint Online, el archivo se desensambla, traduce a código de aplicación y se almacena en varias tablas en varias bases de datos.</span><span class="sxs-lookup"><span data-stu-id="cb07c-149">For example, when a user uploads a file to SharePoint Online, the file is disassembled, translated into application code, and stored in multiple tables across multiple databases.</span></span>

<span data-ttu-id="cb07c-150">Si un usuario puede obtener acceso directo al almacenamiento que contiene los datos, el contenido no se puede interpretar como un usuario ni un sistema que no sea SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cb07c-150">If a user could gain direct access to the storage containing the data, the content is not interpretable to a human or any system other than SharePoint Online.</span></span> <span data-ttu-id="cb07c-151">Estos mecanismos incluyen las propiedades y el control de acceso de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cb07c-151">These mechanisms include security access control and properties.</span></span> <span data-ttu-id="cb07c-152">Todos los recursos de SharePoint Online están protegidos por el código de autorización y la Directiva RBAC, incluso dentro de un arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="cb07c-152">All SharePoint Online resources are secured by the authorization code and RBAC policy, including within a tenancy.</span></span> <span data-ttu-id="cb07c-153">La lista de control de acceso (ACL) que protege un recurso contiene una identidad autenticada en el nivel de espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="cb07c-153">The access control list (ACL) that secures a resource contains an identity authenticated at the tenant level.</span></span> <span data-ttu-id="cb07c-154">Los datos de SharePoint Online para un espacio empresarial se limitan a las identidades autenticadas por el proveedor de autenticación para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="cb07c-154">SharePoint Online data for a tenant is limited to identities authenticated by the authentication provider for the tenant.</span></span>

<span data-ttu-id="cb07c-155">Además de las ACL, una propiedad de nivel de inquilino que especifica el proveedor de autenticación (que es el Azure Active Directory específico del inquilino), se escribe una vez y no se puede cambiar una vez establecido.</span><span class="sxs-lookup"><span data-stu-id="cb07c-155">In addition to the ACLs, a tenant level property that specifies the authentication provider (which is the tenant-specific Azure Active Directory), is written once and cannot be changed once set.</span></span> <span data-ttu-id="cb07c-156">Una vez que se ha establecido la propiedad de inquilino de proveedor de autenticación para un espacio empresarial, no se puede cambiar mediante ninguna API expuesta a un inquilino.</span><span class="sxs-lookup"><span data-stu-id="cb07c-156">Once the authentication provider tenant property has been set for a tenant, it cannot be changed using any APIs exposed to a tenant.</span></span>

<span data-ttu-id="cb07c-157">Se usa un *SubscriptionId* único para cada inquilino.</span><span class="sxs-lookup"><span data-stu-id="cb07c-157">A unique *SubscriptionId* is used for each tenant.</span></span> <span data-ttu-id="cb07c-158">Todos los sitios de clientes pertenecen a un inquilino y se les asigna un *SubscriptionId* único para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="cb07c-158">All customer sites are owned by a tenant and assigned a *SubscriptionId* unique to the tenant.</span></span> <span data-ttu-id="cb07c-159">La propiedad *SubscriptionId* de un sitio se escribe una vez y es permanente.</span><span class="sxs-lookup"><span data-stu-id="cb07c-159">The *SubscriptionId* property on a site is written once and is permanent.</span></span> <span data-ttu-id="cb07c-160">Una vez que se ha asignado a un inquilino, no se puede mover un sitio a un inquilino diferente.</span><span class="sxs-lookup"><span data-stu-id="cb07c-160">Once assigned to a tenant, a site cannot be moved to a different tenant.</span></span> <span data-ttu-id="cb07c-161">El *SubscriptionId* es la clave que se usa para crear el ámbito de seguridad para el proveedor de autenticación y está ligado al espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="cb07c-161">The *SubscriptionId* is the key used to create the security scope for the authentication provider and is tied to the tenant.</span></span>

<span data-ttu-id="cb07c-162">SharePoint Online usa SQL Server y Azure Storage para el almacenamiento de metadatos de contenido.</span><span class="sxs-lookup"><span data-stu-id="cb07c-162">SharePoint Online uses SQL Server and Azure Storage for content metadata storage.</span></span> <span data-ttu-id="cb07c-163">La clave de partición del almacén de contenido es *SiteId* en SQL.</span><span class="sxs-lookup"><span data-stu-id="cb07c-163">The partition key for the content store is *SiteId* in SQL.</span></span> <span data-ttu-id="cb07c-164">Cuando se ejecuta una consulta SQL, SharePoint Online usa un *SiteId* verificado como parte de una comprobación de *SubscriptionId* a nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="cb07c-164">When running a SQL query, SharePoint Online uses a *SiteId* verified as part of a tenant-level *SubscriptionId* check.</span></span>

<span data-ttu-id="cb07c-165">SharePoint Online almacena el contenido de los archivos cifrados en blobs de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="cb07c-165">SharePoint Online stores encrypted file content in Microsoft Azure blobs.</span></span> <span data-ttu-id="cb07c-166">Cada granja de servidores de SharePoint Online tiene su propia cuenta de Microsoft Azure y todos los blobs guardados en Azure se cifran individualmente con una clave almacenada en el almacén de contenido de SQL.</span><span class="sxs-lookup"><span data-stu-id="cb07c-166">Each SharePoint Online farm has its own Microsoft Azure account and all the blobs saved in Azure are encrypted individually with a key stored in the SQL content store.</span></span> <span data-ttu-id="cb07c-167">La clave de cifrado protegida en el código por la capa de autorización y no expuesta directamente al usuario final.</span><span class="sxs-lookup"><span data-stu-id="cb07c-167">The encryption key protected in code by the authorization layer and not exposed directly to the end user.</span></span> <span data-ttu-id="cb07c-168">SharePoint Online tiene supervisión en tiempo real para detectar cuándo una solicitud HTTP lee o escribe datos para más de un espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="cb07c-168">SharePoint Online has real-time monitoring to detect when an HTTP request reads or writes data for more than one tenant.</span></span> <span data-ttu-id="cb07c-169">Se realiza un seguimiento de la *suscripción* de identidad de solicitud en el *subscriptionId* del recurso al que se tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="cb07c-169">The request identity *SubscriptionId* is tracked against the *SubscriptionId* of the accessed resource.</span></span> <span data-ttu-id="cb07c-170">Los usuarios finales nunca deben realizar solicitudes para obtener acceso a recursos de más de un espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="cb07c-170">Requests to access resources of more than one tenant should never happen by end users.</span></span> <span data-ttu-id="cb07c-171">Las solicitudes de servicio en un entorno de varios inquilinos son la única excepción.</span><span class="sxs-lookup"><span data-stu-id="cb07c-171">Service requests in a multi-tenant environment are the only exception.</span></span> <span data-ttu-id="cb07c-172">Por ejemplo, el rastreador de búsqueda extrae los cambios de contenido de toda la base de datos a la vez.</span><span class="sxs-lookup"><span data-stu-id="cb07c-172">For example, the search crawler pulls content changes for an entire database all at once.</span></span> <span data-ttu-id="cb07c-173">Normalmente esto implica consultar sitios de más de un espacio empresarial en una sola solicitud de servicio, que se realiza por motivos de eficiencia.</span><span class="sxs-lookup"><span data-stu-id="cb07c-173">This usually involves querying sites of more than one tenant in a single service request, which is done for efficiency reasons.</span></span>