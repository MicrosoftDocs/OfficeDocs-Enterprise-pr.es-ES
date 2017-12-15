---
title: "Seguridad de la aplicación de nube para su entorno de pruebas y desarrollo de Office 365"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Ent_O365_Top
ms.custom:
- DecEntMigration
- TLG
- Ent_TLGs
ms.assetid: 22248f2f-b370-435e-b6ac-0ae0cae36b96
description: "Resumen: Configurar y demostrar la seguridad de la aplicación de Office 365 nube en el entorno de desarrollo y prueba de Office 365."
ms.openlocfilehash: 1fab5ebfd6e0670ba59fe34b2cca8a7282e75723
ms.sourcegitcommit: d31cf57295e8f3d798ab971d405baf3bd3eb7a45
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="cloud-app-security-for-your-office-365-devtest-environment"></a><span data-ttu-id="2a8fa-103">Seguridad de la aplicación de nube para su entorno de pruebas y desarrollo de Office 365</span><span class="sxs-lookup"><span data-stu-id="2a8fa-103">Cloud App Security for your Office 365 dev/test environment</span></span>

 <span data-ttu-id="2a8fa-104">**Resumen:** Configurar y demostrar la seguridad de la aplicación de Office 365 nube en el entorno de desarrollo y prueba de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-104">**Summary:** Configure and demonstrate Office 365 Cloud App Security in your Office 365 dev/test environment.</span></span>
  
<span data-ttu-id="2a8fa-p101">Seguridad de aplicación nube Office 365, anteriormente conocido como Office 365 administración avanzada de seguridad, le permite crear directivas que supervisión y le informan de actividades sospechosas en su suscripción de Office 365, para que pueda investigar y tomar posible acción de corrección. Para obtener más información, consulte [Información general de nube App seguridad en Office 365](https://support.office.com/article/Overview-of-Advanced-Security-Management-in-Office-365-81f0ee9a-9645-45ab-ba56-de9cbccab475).</span><span class="sxs-lookup"><span data-stu-id="2a8fa-p101">Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Cloud App Security in Office 365](https://support.office.com/article/Overview-of-Advanced-Security-Management-in-Office-365-81f0ee9a-9645-45ab-ba56-de9cbccab475).</span></span>
  
<span data-ttu-id="2a8fa-107">Con las instrucciones de este artículo, habilitar y probar la seguridad de la aplicación de nube en su suscripción de prueba de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-107">With the instructions in this article, you enable and test Cloud App Security in your Office 365 trial subscription.</span></span>
  
> [!TIP]
> <span data-ttu-id="2a8fa-108">Haga clic [aquí](http://aka.ms/catlgstack) para ver un mapa visual para todos los artículos de la pila de una guía de laboratorio de prueba de nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-108">Click [here](http://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-office-365-devtest-environment"></a><span data-ttu-id="2a8fa-109">Fase 1: Crear un entorno de desarrollo y pruebas ligero o de una empresa simulada de Office 365</span><span class="sxs-lookup"><span data-stu-id="2a8fa-109">Phase 1: Build out your lightweight or simulated enterprise Office 365 dev/test environment</span></span>

<span data-ttu-id="2a8fa-110">Si desea probar la seguridad de la aplicación de nube en una manera ligera con los requisitos mínimos, siga las instrucciones que aparecen en las fases 2 y 3 del [entorno de desarrollo y prueba de Office 365](office-365-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="2a8fa-110">If you just want to test Cloud App Security in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [Office 365 dev/test environment](office-365-dev-test-environment.md).</span></span>
  
<span data-ttu-id="2a8fa-111">Si desea probar la seguridad de la aplicación de nube en una empresa simulada, siga las instrucciones de [sincronización de directorios para el entorno de desarrollo y prueba de Office 365](dirsync-for-your-office-365-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="2a8fa-111">If you want to test Cloud App Security in a simulated enterprise, follow the instructions in [DirSync for your Office 365 dev/test environment](dirsync-for-your-office-365-dev-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2a8fa-p102">Pruebas de nube, seguridad de la aplicación no requiere que el entorno de desarrollo/pruebas simuladas enterprise, que incluye una intranet simulada conectada a Internet y sincronización de directorios para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar la seguridad de la aplicación de nube y experimentar con él en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-p102">Testing Cloud App Security does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test Cloud App Security and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-before-enabling-cloud-app-security-and-creating-a-policy"></a><span data-ttu-id="2a8fa-114">Fase 2: antes de habilitar la seguridad de la aplicación de nube y la creación de una directiva</span><span class="sxs-lookup"><span data-stu-id="2a8fa-114">Phase 2: Before enabling Cloud App Security and creating a policy</span></span>

<span data-ttu-id="2a8fa-115">En este procedimiento, se demuestre que antes de habilitar la seguridad de la aplicación de nube, cambiar una función de usuario no proporciona ninguna notificación de correo electrónico para el administrador global.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-115">In this procedure, you demonstrate that before enabling Cloud App Security, changing a user's role provides no email notification to the global administrator.</span></span>
  
### <a name="test-the-default-notification-behavior-of-office-365"></a><span data-ttu-id="2a8fa-116">Probar el comportamiento de notificación predeterminado de Office 365</span><span class="sxs-lookup"><span data-stu-id="2a8fa-116">Test the default notification behavior of Office 365</span></span>

1. <span data-ttu-id="2a8fa-117">Ir al portal de Office 365 ([https://portal.office.com](https://portal.office.com)) e iniciar sesión en su suscripción de prueba de Office 365 con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-117">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="2a8fa-118">Si usa el entorno de desarrollo y pruebas ligero de Office 365, inicie sesión desde el equipo local.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-118">If you are using the lightweight Office 365 dev/test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="2a8fa-119">Si utiliza el entorno de desarrollo/pruebas simuladas enterprise Office 365, usar el [portal de Azure](https://portal.azure.com) para conectarse a la máquina virtual de CLIENTE1 e inicie sesión desde CLIENTE1.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-119">If you are using the simulated enterprise Office 365 dev/test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
    
2. <span data-ttu-id="2a8fa-120">Desde la página principal del portal, haga clic en **Admin**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-120">From the main portal page, click **Admin**.</span></span>
    
3. <span data-ttu-id="2a8fa-121">En el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-121">In the left navigation, click **Users > Active users**.</span></span>
    
4. <span data-ttu-id="2a8fa-122">Haga clic en la cuenta de **usuario 4** .</span><span class="sxs-lookup"><span data-stu-id="2a8fa-122">Click the **User 4** account.</span></span>
    
5. <span data-ttu-id="2a8fa-123">En la página **4 de usuario** , haga clic en **Editar** para la fila de **funciones** .</span><span class="sxs-lookup"><span data-stu-id="2a8fa-123">On the **User 4** page, click **Edit** for the **Roles** row.</span></span>
    
6. <span data-ttu-id="2a8fa-p103">En la página **Editar roles de usuario** , haga clic en **Administrador Global**, escriba **user4@contoso.com** en la **dirección de correo electrónico alternativa**y, a continuación, haga clic en **Guardar**. Haga clic dos veces en **Cerrar** .</span><span class="sxs-lookup"><span data-stu-id="2a8fa-p103">On the **Edit user roles** page, click **Global administrator**, type **user4@contoso.com** in the **Alternative email address**, and then click **Save**. Click **Close** twice.</span></span>
    
7. <span data-ttu-id="2a8fa-126">Seleccione el icono del selector de la aplicación en la parte superior izquierda y elija **correo**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-126">Select the app launcher icon in the upper-left and choose **Mail**.</span></span>
    
8. <span data-ttu-id="2a8fa-p104">Espere 30 minutos. Observe que no aparece ningún mensaje de correo electrónico en la Bandeja de entrada que notifica el cambio en el rol de usuario 4 como un administrador global.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-p104">Wait 30 minutes. Notice that there is no email message in the inbox notifying you of the change in User 4's role as a global administrator.</span></span>
    
## <a name="phase-3-enable-cloud-app-security-and-create-a-policy"></a><span data-ttu-id="2a8fa-129">Fase 3: Habilitar la seguridad de la aplicación de nube y crear una directiva</span><span class="sxs-lookup"><span data-stu-id="2a8fa-129">Phase 3: Enable Cloud App Security and create a policy</span></span>

<span data-ttu-id="2a8fa-p105">En este procedimiento, puede habilita la seguridad de la aplicación de nube y crea una nueva directiva para enviar notificaciones por correo electrónico a su cuenta de administrador global para cambios en las funciones de cuenta de usuario. Este procedimiento requiere:</span><span class="sxs-lookup"><span data-stu-id="2a8fa-p105">In this procedure, you enable Cloud App Security and create a new policy to send email notifications to your global administrator account for changes in user account roles. This procedure requires:</span></span>
  
- <span data-ttu-id="2a8fa-132">El nombre y la contraseña de la cuenta de administrador global de la suscripción de prueba de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-132">The global administrator account name and password of your Office 365 trial subscription.</span></span>
    
- <span data-ttu-id="2a8fa-133">El nombre y la contraseña de la cuenta del Usuario 5 de la suscripción de prueba de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-133">The name and password of the User 5 account of your Office 365 trial subscription.</span></span>
    
### <a name="enable-and-configure-cloud-app-security"></a><span data-ttu-id="2a8fa-134">Habilitar y configurar la seguridad de la aplicación de nube</span><span class="sxs-lookup"><span data-stu-id="2a8fa-134">Enable and configure Cloud App Security</span></span>

1. <span data-ttu-id="2a8fa-135">Ir al portal de Office 365 ([https://portal.office.com](https://portal.office.com)) e iniciar sesión en su suscripción de prueba de Office 365 con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-135">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="2a8fa-136">Haga clic en el **seguridad &amp; Compliance** mosaico.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-136">Click the **Security &amp; Compliance** tile.</span></span>
    
3. <span data-ttu-id="2a8fa-137">En el panel de navegación de la izquierda, haga clic en **alertas > Administrar alertas de avanzada**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-137">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
    
4. <span data-ttu-id="2a8fa-138">En la página **Administrar alertas de avanzada** , haga clic en **activar la seguridad de la aplicación de nube de Office 365**y, a continuación, haga clic en **Ir a la seguridad de la aplicación de nube de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-138">On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.</span></span>
    
5. <span data-ttu-id="2a8fa-139">En la ficha nuevo del **panel** , haga clic en **Control > directivas**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-139">On the new **Dashboard** tab, click **Control > Policies**.</span></span>
    
6. <span data-ttu-id="2a8fa-140">En la página de **Directiva** , haga clic en **Crear directiva**y, a continuación, haga clic en **Directiva de actividad**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-140">On the **Policy** page, click **Create policy**, and then click **Activity policy**.</span></span>
    
7. <span data-ttu-id="2a8fa-141">En **nombre de directiva**, escriba **actividad administrativa**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-141">In **Policy name**, type **Administrative activity**.</span></span>
    
8. <span data-ttu-id="2a8fa-142">**Gravedad de la directiva**, haga clic en **alto**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-142">In **Policy severity**, click **High**.</span></span>
    
9. <span data-ttu-id="2a8fa-143">En **categoría**, haga clic en **cuentas con privilegios**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-143">In **Category**, click **Privileged accounts**.</span></span>
    
10. <span data-ttu-id="2a8fa-144">**Crear filtros para la directiva**, en **las actividades que coinciden con todas las opciones siguientes**, haga clic en **actividad administrativa**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-144">In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.</span></span>
    
11. <span data-ttu-id="2a8fa-p106">En **alertas**, haga clic en **Enviar alerta por correo electrónico**. En el cuadro **para**, escriba la dirección de correo electrónico de la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-p106">In **Alerts**, click **Send alert as email**. In **To**, type the email address of your global administrator account.</span></span>
    
12. <span data-ttu-id="2a8fa-147">En la parte inferior de la página, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-147">At the bottom of the page, click **Create**.</span></span>
    
## <a name="phase-4-show-cloud-app-security-in-action"></a><span data-ttu-id="2a8fa-148">Fase 4: Mostrar nube App seguridad en acción</span><span class="sxs-lookup"><span data-stu-id="2a8fa-148">Phase 4: Show Cloud App Security in action</span></span>

<span data-ttu-id="2a8fa-149">En este procedimiento, que demuestran cómo la seguridad de la aplicación de nube crea alertas y envía notificaciones por correo electrónico a la cuenta de administrador global al usuario 4 hace 5 de usuario, un administrador del usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-149">In this procedure, you demonstrate how Cloud App Security creates alerts and sends email notifications to the global administrator account when User 4 makes User 5 a password and user management administrator.</span></span>
  
### <a name="demonstrate-email-notification-for-a-change-in-user-account-roles"></a><span data-ttu-id="2a8fa-150">Demostración de la notificación por correo electrónico en caso de cambio en los roles de la cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="2a8fa-150">Demonstrate email notification for a change in user account roles</span></span>

1. <span data-ttu-id="2a8fa-151">En la parte superior derecha, haga clic en el icono de usuario y, a continuación, haga clic en **Cerrar sesión**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-151">In the upper-right, click the user icon, and then click **Sign out**.</span></span>
    
2. <span data-ttu-id="2a8fa-152">Vaya a [https://portal.office.com](https://portal.office.com).</span><span class="sxs-lookup"><span data-stu-id="2a8fa-152">Go to [https://portal.office.com](https://portal.office.com).</span></span>
    
3. <span data-ttu-id="2a8fa-153">En la página de identificación Office 365, haga clic en **usar otra cuenta**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-153">On the Office 365 sign in page, click **Use another account**.</span></span>
    
4. <span data-ttu-id="2a8fa-154">Escriba el nombre de la cuenta de usuario 4 y su contraseña y, a continuación, haga clic en **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-154">Type the User 4 account name and its password, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="2a8fa-155">Si es necesario, cambiar la contraseña de la cuenta de usuario 4 y, a continuación, haga clic en **Actualizar contraseña e iniciar sesión en**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-155">If needed, change the User 4 account password, and then click **Update password and sign in**.</span></span>
    
6. <span data-ttu-id="2a8fa-156">En la página de portal de Office 365, haga clic en **Admin**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-156">On the Office 365 portal page, click **Admin**.</span></span>
    
7. <span data-ttu-id="2a8fa-157">Si es necesario, haga clic en **Cancelar** cuando se le pida para actualizar tu información de contacto del administrador.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-157">If needed, click **cancel** when prompted to update your admin contact info.</span></span>
    
8. <span data-ttu-id="2a8fa-158">Desde la página principal del portal, haga clic en **Admin**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-158">From the main portal page, click **Admin**.</span></span>
    
9. <span data-ttu-id="2a8fa-159">En el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-159">In the left navigation, click **Users > Active users**.</span></span>
    
10. <span data-ttu-id="2a8fa-160">Haga clic en la cuenta de **usuario 5** .</span><span class="sxs-lookup"><span data-stu-id="2a8fa-160">Click the **User 5** account.</span></span>
    
11. <span data-ttu-id="2a8fa-161">En la página **5 de usuario** , haga clic en **Editar** para la fila de **funciones** .</span><span class="sxs-lookup"><span data-stu-id="2a8fa-161">On the **User 5** page, click **Edit** for the **Roles** row.</span></span>
    
12. <span data-ttu-id="2a8fa-p107">En la página **Editar roles de usuario** , haga clic en **Administrador de personalizado**, haga clic en **Administrador de contraseñas** y de **Administrador del usuario**, escriba **user5@contoso.com** en la **dirección de correo electrónico alternativa**y, a continuación, haga clic en **Guardar**. Haga clic dos veces en **Cerrar** .</span><span class="sxs-lookup"><span data-stu-id="2a8fa-p107">On the **Edit user roles** page, click **Customized administrator**, click **Password administrator** and **User management administrator**, type **user5@contoso.com** in the **Alternative email address**, and then click **Save**. Click **Close** twice.</span></span>
    
13. <span data-ttu-id="2a8fa-164">Haga clic en el icono de usuario en la parte superior derecha y, a continuación, haga clic en **Cerrar sesión**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-164">Click the user icon in the upper-right, and then click **Sign out**.</span></span> 
    
14. <span data-ttu-id="2a8fa-165">Vaya a [https://portal.office.com](https://portal.office.com).</span><span class="sxs-lookup"><span data-stu-id="2a8fa-165">Go to [https://portal.office.com](https://portal.office.com).</span></span>
    
15. <span data-ttu-id="2a8fa-166">En la página **Office 365 iniciar sesión en** , haga clic en el nombre de la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-166">On the **Office 365 sign in** page, click your global administrator account name.</span></span>
    
16. <span data-ttu-id="2a8fa-167">Escriba la contraseña y, a continuación, haga clic en **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-167">Type the password, and then click **Sign in**.</span></span>
    
17. <span data-ttu-id="2a8fa-168">Desde la página principal del portal, haga clic en **Admin**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-168">From the main portal page, click **Admin**.</span></span>
    
18. <span data-ttu-id="2a8fa-169">Haga clic en el **seguridad &amp; Compliance** mosaico.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-169">Click the **Security &amp; Compliance** tile.</span></span>
    
19. <span data-ttu-id="2a8fa-170">En el panel de navegación de la izquierda, haga clic en **alertas > Administrar alertas de avanzada**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-170">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
    
20. <span data-ttu-id="2a8fa-171">En la página **Administrar alertas de avanzada** , haga clic en **Ir a la seguridad de la aplicación de nube de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-171">On the **Manage advanced alerts** page, click **Go to Office 365 Cloud App Security**.</span></span>
    
21. <span data-ttu-id="2a8fa-172">En la ficha nuevo del **panel** , observe las dos nuevas alertas de **actividad administrativa**.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-172">On the new **Dashboard** tab, notice the two new alerts for **Administrative activity**.</span></span>
    
22. <span data-ttu-id="2a8fa-p108">En la ficha **Página de inicio de Microsoft Office** , haga clic en **correo**. Espere 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="2a8fa-p108">From the **Microsoft Office Home** tab, click **Mail**. Wait up to 30 minutes.</span></span> 
    
    <span data-ttu-id="2a8fa-p109">Debería ver dos mensajes de correo electrónico nuevo en la Bandeja de entrada con el título **Servicio de notificación de AD de Microsoft Azure**. Un mensaje indica que se ha agregado la cuenta de usuario 5 a la función de **Administrador de contraseñas** y otro mensaje que se ha agregado la cuenta de usuario 5 a la función de **Administrador de usuarios** (igual que la función de administrador de gestión de usuario en el Centro de administración de Office 365).</span><span class="sxs-lookup"><span data-stu-id="2a8fa-p109">You should see two new email messages in the inbox with the title **Microsoft Azure AD Notification Service**. One message indicates that the User 5 account was added to the **Password Administrator** role and another message indicates that the User 5 account was added to the **User Administrator** role (equal to the User management administrator role in the Office 365 Admin center).</span></span>
    
<span data-ttu-id="2a8fa-p110">Ahora puede utilizar este entorno para crear nuevas directivas y experimentar aún más con la seguridad de la aplicación de nube de Office 365. Para obtener vínculos a artículos de configuración adicionales, consulte [Prepárese para seguridad de la aplicación de nube de Office 365](https://support.office.com/article/Get-ready-for-Office-365-Cloud-App-Security-d9ee4d67-f2b3-42b4-9c9e-c4529904990a) .</span><span class="sxs-lookup"><span data-stu-id="2a8fa-p110">You can now use this environment to create new policies and further experiment with Office 365 Cloud App Security. See [Get ready for Office 365 Cloud App Security](https://support.office.com/article/Get-ready-for-Office-365-Cloud-App-Security-d9ee4d67-f2b3-42b4-9c9e-c4529904990a) for links to additional configuration articles.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2a8fa-179">See Also</span><span class="sxs-lookup"><span data-stu-id="2a8fa-179">See Also</span></span>

[<span data-ttu-id="2a8fa-180">Guías del laboratorio de pruebas de adopción de la nube (TLG)</span><span class="sxs-lookup"><span data-stu-id="2a8fa-180">Cloud adoption Test Lab Guides (TLGs)</span></span>](cloud-adoption-test-lab-guides-tlgs.md)
  
[<span data-ttu-id="2a8fa-181">Entorno de desarrollo y pruebas de Office 365</span><span class="sxs-lookup"><span data-stu-id="2a8fa-181">Office 365 dev/test environment</span></span>](office-365-dev-test-environment.md)
  
[<span data-ttu-id="2a8fa-182">Adopción de la nube y soluciones híbridas</span><span class="sxs-lookup"><span data-stu-id="2a8fa-182">Cloud adoption and hybrid solutions</span></span>](cloud-adoption-and-hybrid-solutions.md)

[<span data-ttu-id="2a8fa-183">Resumen de seguridad de la aplicación de nube en Office 365</span><span class="sxs-lookup"><span data-stu-id="2a8fa-183">Overview of Cloud App Security in Office 365</span></span>](https://support.office.com/article/Overview-of-Advanced-Security-Management-in-Office-365-81f0ee9a-9645-45ab-ba56-de9cbccab475)

