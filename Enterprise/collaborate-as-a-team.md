---
title: Colaborar con los invitados en un equipo
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
localization_priority: Normal
description: Obtenga información sobre cómo colaborar con invitados en Microsoft Teams.
ms.openlocfilehash: 9a169e33a9cbd8f079966443bd3d830aa79f4971
ms.sourcegitcommit: 3bba97053caf5f9cff0ef3205afb7869535f38bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2019
ms.locfileid: "36992419"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="b864c-103">Colaborar con los invitados en un equipo</span><span class="sxs-lookup"><span data-stu-id="b864c-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="b864c-104">Si necesita colaborar con invitados en documentos, tareas y conversaciones, le recomendamos que use Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b864c-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="b864c-105">Teams ofrece todas las características de colaboración disponibles en Office y SharePoint con chat persistente y un conjunto de herramientas de colaboración personalizable y extensible en una experiencia de usuario unificada.</span><span class="sxs-lookup"><span data-stu-id="b864c-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="b864c-106">En este artículo, analizaremos los pasos de configuración de Microsoft 365 necesarios para configurar un equipo para la colaboración con los invitados.</span><span class="sxs-lookup"><span data-stu-id="b864c-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="b864c-107">Configuración de las relaciones de organización de Azure</span><span class="sxs-lookup"><span data-stu-id="b864c-107">Azure Organizational relationships settings</span></span>

<span data-ttu-id="b864c-108">El uso compartido en Microsoft 365 se rige en su nivel más alto por la configuración de relaciones organizativas en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b864c-108">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="b864c-109">Si el uso compartido de invitado está deshabilitado o restringido en Azure AD, se invalidará cualquier configuración de uso compartido que configure en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b864c-109">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="b864c-110">Compruebe la configuración de relaciones de organización para asegurarse de que no se bloquee el uso compartido con invitados.</span><span class="sxs-lookup"><span data-stu-id="b864c-110">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Captura de pantalla de la página de configuración de relaciones empresariales de Azure Active Directory](media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="b864c-112">Para establecer la configuración de relación organizativa</span><span class="sxs-lookup"><span data-stu-id="b864c-112">To set organizational relationship settings</span></span>

1. <span data-ttu-id="b864c-113">Inicie sesión en Microsoft Azure en [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="b864c-113">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="b864c-114">En el panel de navegación izquierdo, haga clic en **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b864c-114">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="b864c-115">En el panel de **información general** , haga clic en **relaciones organizativas**.</span><span class="sxs-lookup"><span data-stu-id="b864c-115">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="b864c-116">En el panel relaciones de la **organización** , haga clic en **configuración**.</span><span class="sxs-lookup"><span data-stu-id="b864c-116">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="b864c-117">Asegúrese de que los **administradores y los usuarios de la función invitador invitado puedan** invitar y que **los miembros puedan invitar** están establecidos en **sí**.</span><span class="sxs-lookup"><span data-stu-id="b864c-117">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="b864c-118">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b864c-118">If you made changes, click **Save**.</span></span>

<span data-ttu-id="b864c-119">Anote la configuración de la sección **restricciones de colaboración** .</span><span class="sxs-lookup"><span data-stu-id="b864c-119">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="b864c-120">Asegúrese de que los dominios de los invitados con los que desea colaborar no están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="b864c-120">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="b864c-121">Configuración de acceso de invitado de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b864c-121">Teams guest access settings</span></span>

<span data-ttu-id="b864c-122">Los equipos tienen un conmutador de encendido y apagado principal para el acceso de invitado y una variedad de opciones de configuración disponibles para controlar lo que pueden hacer los invitados en un equipo.</span><span class="sxs-lookup"><span data-stu-id="b864c-122">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="b864c-123">El conmutador maestro, **permitir el acceso de invitado en Microsoft Teams** , debe estar **activado** para que el acceso de invitado trabaje en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b864c-123">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="b864c-124">Asegúrese de que el acceso de invitado esté habilitado en Microsoft Teams y realice cualquier ajuste en la configuración de invitado en función de las necesidades de su empresa.</span><span class="sxs-lookup"><span data-stu-id="b864c-124">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="b864c-125">Tenga en cuenta que esta configuración afecta a todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="b864c-125">Keep in mind that these settings affect all teams.</span></span>

![Captura de pantalla de alternancia de acceso de invitado de Teams](media/teams-guest-access-toggle-on.png)

<span data-ttu-id="b864c-127">Para establecer la configuración de acceso de invitado de Teams</span><span class="sxs-lookup"><span data-stu-id="b864c-127">To set Teams guest access settings</span></span>

1. <span data-ttu-id="b864c-128">Inicie sesión en el centro de administración de Microsoft [https://admin.microsoft.com](https://admin.microsoft.com)365 en.</span><span class="sxs-lookup"><span data-stu-id="b864c-128">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="b864c-129">En el panel de navegación izquierdo, haga clic en **Mostrar todo**.</span><span class="sxs-lookup"><span data-stu-id="b864c-129">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="b864c-130">En **centros de administración**, haga clic en **Teams**.</span><span class="sxs-lookup"><span data-stu-id="b864c-130">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="b864c-131">En el centro de administración de Teams, en el panel de navegación de la izquierda, expanda **configuración de toda la organización** y haga clic en **acceso de invitado**.</span><span class="sxs-lookup"><span data-stu-id="b864c-131">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="b864c-132">Asegúrese de que la **opción permitir el acceso de invitado en Microsoft Teams** está **activada**.</span><span class="sxs-lookup"><span data-stu-id="b864c-132">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="b864c-133">Realice los cambios que desee en la configuración de invitado adicional y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b864c-133">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="b864c-134">La configuración del invitado de Teams puede tardar hasta 24 horas en activa una vez que la activa.</span><span class="sxs-lookup"><span data-stu-id="b864c-134">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

## <a name="office-365-groups-guest-settings"></a><span data-ttu-id="b864c-135">Configuración de invitado de Office 365 Groups</span><span class="sxs-lookup"><span data-stu-id="b864c-135">Office 365 Groups guest settings</span></span>

<span data-ttu-id="b864c-136">Microsoft Teams usa los grupos de Office 365 para la pertenencia al equipo.</span><span class="sxs-lookup"><span data-stu-id="b864c-136">Teams uses Office 365 Groups for team membership.</span></span> <span data-ttu-id="b864c-137">La configuración de invitado de los grupos de Office 365 debe estar activada para que el acceso de invitado en Microsoft Teams funcione.</span><span class="sxs-lookup"><span data-stu-id="b864c-137">The Office 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Captura de pantalla de la configuración de invitado de Office 365 Groups en el centro de administración de Microsoft 365](media/office-365-groups-guest-settings.png)

<span data-ttu-id="b864c-139">Para establecer la configuración de invitado de Office 365 Groups</span><span class="sxs-lookup"><span data-stu-id="b864c-139">To set Office 365 Groups guest settings</span></span>

1. <span data-ttu-id="b864c-140">En el centro de administración de Microsoft 365, en el panel de navegación de la izquierda, expanda **configuración**.</span><span class="sxs-lookup"><span data-stu-id="b864c-140">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="b864c-141">Haga clic en **servicios & complementos**.</span><span class="sxs-lookup"><span data-stu-id="b864c-141">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="b864c-142">En la lista, haga clic en **grupos de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="b864c-142">In the list, click **Office 365 Groups**.</span></span>
4. <span data-ttu-id="b864c-143">Asegúrese de que la casilla **permitir a los miembros del grupo fuera de la organización el acceso al contenido del grupo** y **que los propietarios del grupo agreguen personas fuera de la organización a las** casillas de verificación están activadas.</span><span class="sxs-lookup"><span data-stu-id="b864c-143">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="b864c-144">Si ha realizado cambios, haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="b864c-144">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="b864c-145">Configuración de uso compartido en el nivel de organización de SharePoint</span><span class="sxs-lookup"><span data-stu-id="b864c-145">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="b864c-146">Para que los invitados tengan acceso a los archivos de Microsoft Teams, la configuración de uso compartido en el nivel de la organización de SharePoint debe permitir el uso compartido con invitados.</span><span class="sxs-lookup"><span data-stu-id="b864c-146">In order for guests to have access to files in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="b864c-147">La configuración en el nivel de la organización determina qué opciones de configuración están disponibles para cada uno de los sitios, incluidos los sitios asociados a teams.</span><span class="sxs-lookup"><span data-stu-id="b864c-147">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="b864c-148">La configuración del sitio no puede ser más permisiva que la configuración de nivel de organización.</span><span class="sxs-lookup"><span data-stu-id="b864c-148">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="b864c-149">Si desea permitir el uso compartido de archivos y carpetas con usuarios anónimos, elija **cualquier persona**.</span><span class="sxs-lookup"><span data-stu-id="b864c-149">If you want to allow file and folder sharing with anonymous users, choose **Anyone**.</span></span> <span data-ttu-id="b864c-150">Si desea asegurarse de que todos los invitados tienen que autenticarse, elija los **invitados nuevos y existentes**.</span><span class="sxs-lookup"><span data-stu-id="b864c-150">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="b864c-151">Elija la configuración más permisiva que necesitará cualquier sitio de la organización.</span><span class="sxs-lookup"><span data-stu-id="b864c-151">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Captura de pantalla de la configuración de uso compartido en el nivel de organización de SharePoint](media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="b864c-153">Para establecer la configuración de uso compartido en el nivel de la organización de SharePoint</span><span class="sxs-lookup"><span data-stu-id="b864c-153">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="b864c-154">En el centro de administración de Microsoft 365, en el panel de navegación izquierdo, en **centros de administración**, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b864c-154">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="b864c-155">En el centro de administración de SharePoint, en el panel de navegación izquierdo, haga clic en **compartir**.</span><span class="sxs-lookup"><span data-stu-id="b864c-155">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="b864c-156">Asegúrese de que el uso compartido externo para SharePoint está establecido en **todos** o en **invitados nuevos o existentes**.</span><span class="sxs-lookup"><span data-stu-id="b864c-156">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="b864c-157">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b864c-157">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="b864c-158">Configuración de vínculos predeterminados de nivel de organización de SharePoint</span><span class="sxs-lookup"><span data-stu-id="b864c-158">SharePoint organization level default link settings</span></span>

<span data-ttu-id="b864c-159">La configuración predeterminada de los vínculos de archivos y carpetas determina qué opción de vínculo se muestra al usuario de forma predeterminada cuando comparte un archivo o una carpeta.</span><span class="sxs-lookup"><span data-stu-id="b864c-159">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="b864c-160">Los usuarios pueden cambiar el tipo de vínculo a una de las otras opciones antes de compartirlo, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="b864c-160">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="b864c-161">Tenga en cuenta que esta configuración afecta a todos los equipos y sitios de SharePoint de la organización.</span><span class="sxs-lookup"><span data-stu-id="b864c-161">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="b864c-162">Elija el tipo de vínculo que está seleccionado de forma predeterminada cuando los usuarios comparten archivos y carpetas:</span><span class="sxs-lookup"><span data-stu-id="b864c-162">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="b864c-163">**Cualquiera que tenga el vínculo** : elija esta opción si prevé compartir una gran cantidad de archivos y carpetas con usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="b864c-163">**Anyone with the link** - Choose this option if you expect to share a lot of files and folders with anonymous users.</span></span> <span data-ttu-id="b864c-164">Si desea permitir que *todos* los vínculos, pero le preocupa el uso compartido de anónimos accidentales, tenga en cuenta una de las otras opciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="b864c-164">If you want to allow *Anyone* links but are concerned about accidental anonymous sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="b864c-165">Este tipo de vínculo solo está disponible si ha habilitado a **todos los usuarios** que comparten el mismo.</span><span class="sxs-lookup"><span data-stu-id="b864c-165">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="b864c-166">**Solo las personas de su organización** : elija esta opción si prevé que la mayoría del uso compartido de archivos y carpetas sea para personas dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="b864c-166">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="b864c-167">**Personas específicas** : considere esta opción si espera compartir muchos archivos y carpetas con los invitados.</span><span class="sxs-lookup"><span data-stu-id="b864c-167">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="b864c-168">Este tipo de vínculo funciona con los invitados y requiere que se autentiquen.</span><span class="sxs-lookup"><span data-stu-id="b864c-168">This type of link works with guests and requires them to authenticate.</span></span>
 
![Captura de pantalla de la configuración de uso compartido de archivos y carpetas en el nivel de organización de SharePoint](media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="b864c-170">Para establecer la configuración de vínculos predeterminados de nivel de organización de SharePoint</span><span class="sxs-lookup"><span data-stu-id="b864c-170">To set the SharePoint organization level default link settings</span></span>

1. <span data-ttu-id="b864c-171">Vaya a la página de uso compartido en el centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b864c-171">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="b864c-172">En **vínculos de archivos y carpetas**, seleccione el vínculo de uso compartido predeterminado que desee usar.</span><span class="sxs-lookup"><span data-stu-id="b864c-172">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="b864c-173">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b864c-173">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="b864c-174">Crear un equipo</span><span class="sxs-lookup"><span data-stu-id="b864c-174">Create a team</span></span>

<span data-ttu-id="b864c-175">El siguiente paso es crear el equipo que planea usar para colaborar con invitados.</span><span class="sxs-lookup"><span data-stu-id="b864c-175">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="b864c-176">Para crear un equipo</span><span class="sxs-lookup"><span data-stu-id="b864c-176">To create a team</span></span>
1. <span data-ttu-id="b864c-177">En Microsoft Teams, en **la pestaña Microsoft Teams** , haga clic en **unirse o en crear un equipo** en la parte inferior del panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="b864c-177">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="b864c-178">Haga clic en **crear un equipo**.</span><span class="sxs-lookup"><span data-stu-id="b864c-178">Click **Create a team**.</span></span>
3. <span data-ttu-id="b864c-179">Haga clic en **crear un equipo desde cero**.</span><span class="sxs-lookup"><span data-stu-id="b864c-179">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="b864c-180">Elija **privado** o **público**.</span><span class="sxs-lookup"><span data-stu-id="b864c-180">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="b864c-181">Escriba un nombre y una descripción para el equipo y, a continuación, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="b864c-181">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="b864c-182">Haga clic en **omitir**.</span><span class="sxs-lookup"><span data-stu-id="b864c-182">Click **Skip**.</span></span>

<span data-ttu-id="b864c-183">Invitaremos a los usuarios más adelante.</span><span class="sxs-lookup"><span data-stu-id="b864c-183">We'll invite users later.</span></span> <span data-ttu-id="b864c-184">A continuación, es importante comprobar la configuración de uso compartido de nivel de sitio para el sitio de SharePoint asociado al equipo.</span><span class="sxs-lookup"><span data-stu-id="b864c-184">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="b864c-185">Configuración de uso compartido del nivel de sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="b864c-185">SharePoint site level sharing settings</span></span>

<span data-ttu-id="b864c-186">Compruebe la configuración de uso compartido de nivel de sitio para asegurarse de que permite el tipo de acceso que desea para este equipo.</span><span class="sxs-lookup"><span data-stu-id="b864c-186">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="b864c-187">Por ejemplo, si establece la configuración en el nivel de la organización en **cualquiera**, pero desea que todos los invitados se autentiquen para este equipo, asegúrese de que la configuración de uso compartido de nivel de sitio esté establecida en **invitados nuevos y existentes**.</span><span class="sxs-lookup"><span data-stu-id="b864c-187">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Captura de pantalla de la configuración de uso compartido externo del sitio de SharePoint](media/sharepoint-site-external-sharing-settings.png)


<span data-ttu-id="b864c-189">Para establecer la configuración de uso compartido de nivel de sitio</span><span class="sxs-lookup"><span data-stu-id="b864c-189">To set site-level sharing settings</span></span>
1. <span data-ttu-id="b864c-190">En el centro de administración de SharePoint, en el panel de navegación de la izquierda, expanda **sitios** y haga clic en **sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="b864c-190">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="b864c-191">Seleccione el sitio para el equipo que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="b864c-191">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="b864c-192">En la cinta, haga clic en **uso compartido**.</span><span class="sxs-lookup"><span data-stu-id="b864c-192">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="b864c-193">Asegúrese de que el uso compartido está establecido en **todos** o en **invitados nuevos o existentes**.</span><span class="sxs-lookup"><span data-stu-id="b864c-193">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="b864c-194">Si ha realizado cambios, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b864c-194">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="b864c-195">Invitar a usuarios</span><span class="sxs-lookup"><span data-stu-id="b864c-195">Invite users</span></span>

<span data-ttu-id="b864c-196">La configuración de uso compartido de invitados ya está configurada, por lo que puede empezar a agregar invitados y usuarios internos a su equipo.</span><span class="sxs-lookup"><span data-stu-id="b864c-196">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="b864c-197">Para invitar a usuarios internos a un equipo</span><span class="sxs-lookup"><span data-stu-id="b864c-197">To invite internal users to a team</span></span>
1. <span data-ttu-id="b864c-198">En el equipo, haga clic en **más opciones** (**\*\***) y, a continuación, haga clic en **Agregar miembro**.</span><span class="sxs-lookup"><span data-stu-id="b864c-198">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="b864c-199">Escriba el nombre de la persona a la que desea invitar.</span><span class="sxs-lookup"><span data-stu-id="b864c-199">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="b864c-200">Haga clic en **Agregar** y, después, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b864c-200">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="b864c-201">Para invitar a invitados a un equipo</span><span class="sxs-lookup"><span data-stu-id="b864c-201">To invite guests to a team</span></span>
1. <span data-ttu-id="b864c-202">En el equipo, haga clic en **más opciones** (**\*\***) y, a continuación, haga clic en **Agregar miembro**.</span><span class="sxs-lookup"><span data-stu-id="b864c-202">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="b864c-203">Escriba la dirección de correo electrónico del invitado al que desea invitar.</span><span class="sxs-lookup"><span data-stu-id="b864c-203">Type the email address of the guest who you want to invite.</span></span>
3. <span data-ttu-id="b864c-204">Haga clic en **editar información de invitado**.</span><span class="sxs-lookup"><span data-stu-id="b864c-204">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="b864c-205">Escriba el nombre completo del invitado y haga clic en la marca de verificación.</span><span class="sxs-lookup"><span data-stu-id="b864c-205">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="b864c-206">Haga clic en **Agregar** y, después, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b864c-206">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b864c-207">Vea también</span><span class="sxs-lookup"><span data-stu-id="b864c-207">See Also</span></span>
