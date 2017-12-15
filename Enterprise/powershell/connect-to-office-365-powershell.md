---
title: Conectarse a PowerShell de Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- LIL_Placement
- O365ITProTrain
- DecEntMigration
- apr17entnews
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: "Resumen: Conectarse a su organización de Office 365 mediante Office 365 PowerShell para realizar tareas del centro de administración de Office 365 desde la línea de comandos."
ms.openlocfilehash: 3ac368a3d3584c15e1d0c26104616e8258a78e7b
ms.sourcegitcommit: d31cf57295e8f3d798ab971d405baf3bd3eb7a45
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="connect-to-office-365-powershell"></a><span data-ttu-id="04d0f-103">Conectarse a PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="04d0f-103">Connect to Office 365 PowerShell</span></span>

 <span data-ttu-id="04d0f-104">**Resumen:** Conectarse a su organización de Office 365 mediante Office 365 PowerShell para realizar tareas de administración de Office 365 desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="04d0f-104">**Summary:** Connect to your Office 365 organization using Office 365 PowerShell to perform Office 365 administration tasks from the command line.</span></span>
  
<span data-ttu-id="04d0f-p101">Office 365 PowerShell permite administrar la configuración de Office 365 desde la línea de comandos. Conectarse a Office 365 PowerShell es un proceso sencillo de tres pasos donde instalar el software necesario, ejecutar el software necesario y, a continuación, conectarse a su organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="04d0f-p101">Office 365 PowerShell lets you to manage your Office 365 settings from the command line. Connecting to Office 365 PowerShell is a simple three-step process where you install the required software, run the required software, and then connect to your Office 365 organization.</span></span> 

<span data-ttu-id="04d0f-107">Tenga en cuenta que estas instrucciones de conexión son las mismas que las del tema [ActiveDirectory Azure (MSOnline)](https://go.microsoft.com/fwlink/p/?LinkId=528113).</span><span class="sxs-lookup"><span data-stu-id="04d0f-107">Note that these connection instructions are the same as those in the topic [Azure ActiveDirectory (MSOnline)](https://go.microsoft.com/fwlink/p/?LinkId=528113).</span></span>
  
> [!TIP]
> <span data-ttu-id="04d0f-p102">**Nuevo a PowerShell?** Vea un [Vídeo de información general de PowerShell](http://technet.microsoft.com/library/https://support.office.com/en-us/article/7d0107d4-f672-4d0f-ad7d-417844b926c7.aspx), ofrecido por aprendizaje de LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="04d0f-p102">**New to PowerShell?** See a [video Overview of PowerShell](http://technet.microsoft.com/library/https://support.office.com/en-us/article/7d0107d4-f672-4d0f-ad7d-417844b926c7.aspx), brought to you by LinkedIn Learning.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="04d0f-110">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="04d0f-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="04d0f-111">Tiempo estimado para finalizar: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="04d0f-111">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="04d0f-112">Puede usar las siguientes versiones de Windows:</span><span class="sxs-lookup"><span data-stu-id="04d0f-112">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="04d0f-113">Windows 10, Windows 8.1, Windows 8 o Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="04d0f-113">Windows 10, Windows 8.1, Windows 8 or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="04d0f-114">Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="04d0f-114">Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>
    
    > [!NOTE]
    ><span data-ttu-id="04d0f-p103">Utilice una versión de 64 bits de Windows. Soporte para la versión de 32 bits del Microsoft Azure Active Directory módulo para Windows PowerShell se interrumpió en octubre de 2014.</span><span class="sxs-lookup"><span data-stu-id="04d0f-p103">Use a 64-bit version of Windows. Support for the 32-bit version the Microsoft Azure Active Directory Module for Windows PowerShell was discontinued in October of 2014.</span></span>
    
-  <span data-ttu-id="04d0f-p104">El Office 365 trabajo o escuela cuenta utilizar para estos procedimientos necesidades para ser miembro de una función de administración de Office 365. Para obtener más información, consulte [las funciones de administrador acerca de Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span><span class="sxs-lookup"><span data-stu-id="04d0f-p104">The Office 365 work or school account that you use for these procedures needs to be a member of an Office 365 admin role. For more information, see [About Office 365 admin roles](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span></span>
    
## <a name="step-1-install-required-software"></a><span data-ttu-id="04d0f-119">Paso 1: instalar el software necesario</span><span class="sxs-lookup"><span data-stu-id="04d0f-119">Step 1: Install required software</span></span>

<span data-ttu-id="04d0f-p105">Estos pasos son necesarios una sola vez en el equipo, no cada vez que se conecta. Sin embargo, probablemente necesitará instalar las versiones más recientes de software periódicamente.</span><span class="sxs-lookup"><span data-stu-id="04d0f-p105">These steps are required once on your computer, not every time you connect. However, you'll likely need to install newer versions of the software periodically.</span></span>
  
1.  <span data-ttu-id="04d0f-122">Instalar la versión de 64 bits del Ayudante de inicio de sesión de Microsoft Online Services: [Asistente de inicio de sesión de Microsoft Online Services para RTW de profesionales de TI](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span><span class="sxs-lookup"><span data-stu-id="04d0f-122">Install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
    
2. <span data-ttu-id="04d0f-123">Instale la versión de 64 bits de Módulo de Microsoft Azure Active Directory para Windows PowerShell siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="04d0f-123">Install the 64-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>
    
  - <span data-ttu-id="04d0f-124">Abra la página web [Azure Active Directory Connection](http://connect.microsoft.com/site1164/Downloads/DownloadDetails.aspx?DownloadID=59185).</span><span class="sxs-lookup"><span data-stu-id="04d0f-124">Open the [Azure Active Directory Connection](http://connect.microsoft.com/site1164/Downloads/DownloadDetails.aspx?DownloadID=59185) web page.</span></span>
    
  - <span data-ttu-id="04d0f-125">En **Archivos para descargar**, en la parte inferior de la página, haga clic en el botón **Descargar** del archivo **AdministrationConfig-V1.1.166.0-GA.msi** e instálelo.</span><span class="sxs-lookup"><span data-stu-id="04d0f-125">In **Files in Download** at the bottom of the page, click **Download** for the **AdministrationConfig-V1.1.166.0-GA.msi** file, and then install it.</span></span>
    
## <a name="step-2-open-the-windows-azure-active-directory-module"></a><span data-ttu-id="04d0f-126">Paso 2: abrir el módulo Active Directory de Windows Azure</span><span class="sxs-lookup"><span data-stu-id="04d0f-126">Step 2: Open the Windows Azure Active Directory Module</span></span>

1. <span data-ttu-id="04d0f-127">Busque y abra Módulo de Microsoft Azure Active Directory para Windows PowerShell mediante uno de los métodos siguientes según la versión de Windows:</span><span class="sxs-lookup"><span data-stu-id="04d0f-127">Find and open the Microsoft Azure Active Directory Module for Windows PowerShell by using one of the following methods based on your version of Windows:</span></span>
    
  - <span data-ttu-id="04d0f-128">**Menú Inicio** En el escritorio, haga clic en **Inicio** y escribaAzure.</span><span class="sxs-lookup"><span data-stu-id="04d0f-128">**Start menu** From the desktop, click **Start**, and then type Azure.</span></span>
    
  - <span data-ttu-id="04d0f-129">**No hay menú Inicio** BusqueAzure mediante cualquiera de estos métodos:</span><span class="sxs-lookup"><span data-stu-id="04d0f-129">**No Start menu** Search forAzure using any of these methods:</span></span>
    
  - <span data-ttu-id="04d0f-130">En la pantalla Inicio, haga clic en un área vacía y escriba Azure.</span><span class="sxs-lookup"><span data-stu-id="04d0f-130">On the Start screen, click an empty area, and type Azure.</span></span>
    
  - <span data-ttu-id="04d0f-p106">En el escritorio o la pantalla Inicio, pulse la tecla Windows + Q. En el acceso Buscar, escriba Azure.</span><span class="sxs-lookup"><span data-stu-id="04d0f-p106">On the desktop or the Start screen, press the Windows key+Q. In the Search charm, type Azure.</span></span>
    
  - <span data-ttu-id="04d0f-p107">En el escritorio o la pantalla de inicio, mueva el cursor a la esquina superior derecha, o Deslizar hacia la izquierda desde el borde derecho de la pantalla para mostrar los encantos. Seleccione los bueno de búsqueda y escriba **Azure**.</span><span class="sxs-lookup"><span data-stu-id="04d0f-p107">On the desktop or the Start screen, move your cursor to the upper-right corner, or swipe left from the right edge of the screen to show the charms. Select the Search charm, and type **Azure**.</span></span>
    
2. <span data-ttu-id="04d0f-135">En los resultados, haga clic en **Módulo de Microsoft Azure Active Directory para Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="04d0f-135">In the results, click **Microsoft Azure Active Directory Module for Windows PowerShell**.</span></span>
    
## <a name="step-3-connect-to-your-office-365-subscription"></a><span data-ttu-id="04d0f-136">Paso 3: conectarse a la suscripción de Office 365</span><span class="sxs-lookup"><span data-stu-id="04d0f-136">Step 3: Connect to your Office 365 subscription</span></span>
<span data-ttu-id="04d0f-137"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="04d0f-137"><a name="step3"> </a></span></span>

<span data-ttu-id="04d0f-138">Para conectarse con solo el  *nombre de cuenta y la contraseña*  :</span><span class="sxs-lookup"><span data-stu-id="04d0f-138">To connect with just an  *account name and password*  :</span></span>
  
1. <span data-ttu-id="04d0f-139">Ejecute los comandos siguientes en la ventana de comandos **Módulo de Microsoft Azure Active Directory para Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="04d0f-139">In the **Microsoft Azure Active Directory Module for Windows PowerShell** command window, run the following commands.</span></span>
    
  ```
  $UserCredential = Get-Credential
Connect-MsolService -Credential $UserCredential
  ```

2. <span data-ttu-id="04d0f-140">En el cuadro de diálogo **Solicitud de credenciales para Windows PowerShell**, escriba su nombre de usuario y contraseña de Office 365cuenta profesional o educativa y, luego, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="04d0f-140">In the **Windows PowerShell Credential Request** dialog box, type your Office 365 work or school account user name and password, and then click **OK**.</span></span>
    
<span data-ttu-id="04d0f-141">Para conectarse mediante la  *autenticación multifactor (AMF)*  :</span><span class="sxs-lookup"><span data-stu-id="04d0f-141">To connect with  *multi-factor authentication (MFA)*  :</span></span>
  
1. <span data-ttu-id="04d0f-142">Ejecute el comando siguiente en la ventana de comandos **Módulo de Microsoft Azure Active Directory para Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="04d0f-142">In the **Microsoft Azure Active Directory Module for Windows PowerShell** command window, run the following command.</span></span>
    
  ```
  Connect-MsolService
  ```

2. <span data-ttu-id="04d0f-143">En el cuadro de diálogo **Azure Active Directory PowerShell**, escriba su nombre de usuario y contraseña de Office 365cuenta profesional o educativa y, a continuación, haga clic en **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="04d0f-143">In the **Azure Active Directory PowerShell** dialog box, type your Office 365 work or school account user name and password, and then click **Sign in**.</span></span>
    
3. <span data-ttu-id="04d0f-144">Siga las instrucciones del cuadro de diálogo de **Azure Active Directory PowerShell** para proporcionar información de autenticación adicional, como un código de comprobación, y haga clic en **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="04d0f-144">Follow the instructions in the **Azure Active Directory PowerShell** dialog box to provide additional authentication information, such as a verification code, and then click **Sign in**.</span></span>
    
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="04d0f-145">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="04d0f-145">How do you know this worked?</span></span>
<span data-ttu-id="04d0f-146"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="04d0f-146"><a name="step3"> </a></span></span>

<span data-ttu-id="04d0f-p108">Si no se muestra ningún error, la conexión se habrá establecido correctamente. Para hacer una prueba rápida, ejecute un cmdlet de Office 365, como **Get-MsolUser**, y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="04d0f-p108">If you don't receive any errors, you connected successfully. A quick test is to run an Office 365 cmdlet—for example, **Get-MsolUser** —and see the results.</span></span>
  
<span data-ttu-id="04d0f-149">Si surgen errores, compruebe los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="04d0f-149">If you receive errors, check the following requirements:</span></span>
  
- <span data-ttu-id="04d0f-p109">**Un problema habitual es una contraseña incorrecta**. Vuelva a realizar el paso 3 y preste especial atención al nombre de usuario y la contraseña que escriba.</span><span class="sxs-lookup"><span data-stu-id="04d0f-p109">**A common problem is an incorrect password**. Run Step 3 again. and pay close attention to the user name and password you enter.</span></span>
    
- <span data-ttu-id="04d0f-p110">**Módulo de Microsoft Azure Active Directory para Windows PowerShell requiere que la característica Microsoft .NET Framework 3.5. _x_ esté habilitada en el equipo**. Es probable que el equipo tenga instalada una versión más reciente (por ejemplo, 4 o 4.5. _x_), pero sea posible habilitar o deshabilitar la compatibilidad con versiones anteriores de .NET Framework. Para obtener más información al respecto, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="04d0f-p110">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that the Microsoft .NET Framework 3.5. _x_ feature is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5. _x_), but backwards compatibility with older versions of the .NET Framework can be enabled or disabled. For more information, see the following topics:</span></span>
    
  - <span data-ttu-id="04d0f-157">Para Windows Server 2012 o 2012 R2 de Windows Server, vea [Habilitar.NET Framework 3.5 mediante el agregar funciones y características de asistente](https://go.microsoft.com/fwlink/p/?LinkId=532368)</span><span class="sxs-lookup"><span data-stu-id="04d0f-157">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](https://go.microsoft.com/fwlink/p/?LinkId=532368)</span></span>
    
  - <span data-ttu-id="04d0f-158">Para Windows 8 o Windows 8.1, vea [instalar el 3.5 de.NET Framework en Windows 8 o 8.1](https://go.microsoft.com/fwlink/p/?LinkId=532369)</span><span class="sxs-lookup"><span data-stu-id="04d0f-158">For Windows 8 or Windows 8.1, see [Installing the .NET Framework 3.5 on Windows 8 or 8.1](https://go.microsoft.com/fwlink/p/?LinkId=532369)</span></span>
    
  - <span data-ttu-id="04d0f-159">Para Windows 7 o Windows Server 2008 R2, vea [no se puede abrir Azure Active Directory módulo para Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370)</span><span class="sxs-lookup"><span data-stu-id="04d0f-159">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370)</span></span>
    
- <span data-ttu-id="04d0f-p111">**Puede que su versión de Módulo de Microsoft Azure Active Directory para Windows PowerShell esté obsoleta.** Para comprobarlo, ejecute el siguiente comando en PowerShell de Office 365 o Módulo de Microsoft Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="04d0f-p111">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.** To check, run the following command in Office 365 PowerShell or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="04d0f-162">Si el número de versión devuelto es menor que el valor 1.0.8070.2, desinstale el Módulo de Microsoft Azure Active Directory para Windows PowerShell e instale la versión más reciente desde el vínculo en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="04d0f-162">If the version number returned is lower than the value 1.0.8070.2, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install the latest version from the link in Step 1.</span></span>
    
- <span data-ttu-id="04d0f-163">**Si recibe un error de conexión, vea este tema:** ["Connect-MsolService: excepción de tipo" error](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span><span class="sxs-lookup"><span data-stu-id="04d0f-163">**If you receive a connection error, see this topic:** ["Connect-MsolService: Exception of type was thrown" error](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span></span>
    
## <a name="connect-with-the-azure-active-directory-v2-powershell-module"></a><span data-ttu-id="04d0f-164">Conectarse con el módulo de PowerShell Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="04d0f-164">Connect with the Azure Active Directory V2 PowerShell module</span></span>
<span data-ttu-id="04d0f-165"><a name="ConnectV2"> </a></span><span class="sxs-lookup"><span data-stu-id="04d0f-165"><a name="ConnectV2"> </a></span></span>

<span data-ttu-id="04d0f-166">Para los procedimientos que necesitan los nuevos cmdlets del [módulo de PowerShell Azure Active Directory V2](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory), siga estos pasos para instalar el módulo y conectarse a su suscripción a Office 365:</span><span class="sxs-lookup"><span data-stu-id="04d0f-166">For procedures that require the new cmdlets in the [Azure Active Directory V2 PowerShell module](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory), use these steps to install the module and connect to your Office 365 subscription:</span></span>
  
1. <span data-ttu-id="04d0f-167">Abra un símbolo del sistema de Windows PowerShell con privilegios elevados (ejecute Windows PowerShell como administrador).</span><span class="sxs-lookup"><span data-stu-id="04d0f-167">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="04d0f-168">En la ventana de comandos **Administrador: Windows PowerShell**, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="04d0f-168">In the **Administrator: Windows PowerShell** command window, run this command:</span></span>
    
  ```
  Install-Module -Name AzureAD 
  ```

<span data-ttu-id="04d0f-169">Si se le pregunta si quiere instalar un módulo desde un repositorio que no es de confianza, escriba **Y** y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="04d0f-169">If prompted about installing a module from an untrusted repository, type **Y** and press ENTER.</span></span>
    
3. <span data-ttu-id="04d0f-170">Cuando se complete la instalación del nuevo módulo, use estos comandos para conectarse a su suscripción a Office 365:</span><span class="sxs-lookup"><span data-stu-id="04d0f-170">When the installation of the new module is complete, use these commands to connect to your Office 365 subscription:</span></span>
    
  -  <span data-ttu-id="04d0f-171">Con un  *nombre de cuenta y contraseña*  :</span><span class="sxs-lookup"><span data-stu-id="04d0f-171">With an *account name and password*  :</span></span>
    
  ```
  $UserCredential = Get-Credential
Connect-AzureAD -Credential $UserCredential
  ```

 <span data-ttu-id="04d0f-172">En el cuadro de diálogo **Solicitud de credenciales para Windows PowerShell**, escriba su nombre de usuario y contraseña de Office 365cuenta profesional o educativa y, luego, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="04d0f-172">In the **Windows PowerShell Credential Request** dialog box, type your Office 365 work or school account user name and password, and then click **OK**.</span></span>
    
  - <span data-ttu-id="04d0f-173">Con la  *autenticación multifactor (MFA)*  :</span><span class="sxs-lookup"><span data-stu-id="04d0f-173">With  *multi-factor authentication (MFA)*  :</span></span>
    
  ```
  Connect-AzureAD
  ```

<span data-ttu-id="04d0f-174">En el cuadro de diálogo **Azure Active Directory PowerShell**, escriba su nombre de usuario y contraseña de Office 365cuenta profesional o educativa y, a continuación, haga clic en **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="04d0f-174">In the **Azure Active Directory PowerShell** dialog box, type your Office 365 work or school account user name and password, and then click **Sign in**.</span></span>
    
<span data-ttu-id="04d0f-175">Siga las instrucciones del cuadro de diálogo de **Azure Active Directory PowerShell** para proporcionar información de autenticación adicional, como un código de comprobación, y haga clic en **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="04d0f-175">Follow the instructions in the **Azure Active Directory PowerShell** dialog box to provide additional authentication information, such as a verification code, and then click **Sign in**.</span></span>
    
<span data-ttu-id="04d0f-176">Después de conectarse, podrá usar los nuevos cmdlets del [módulo de PowerShell Azure Active Directory V2](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).</span><span class="sxs-lookup"><span data-stu-id="04d0f-176">After connecting, you can use the new cmdlets for the [Azure Active Directory V2 PowerShell module](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="04d0f-177">See also</span><span class="sxs-lookup"><span data-stu-id="04d0f-177">See also</span></span>

#### 

[<span data-ttu-id="04d0f-178">Administrar Office 365 con PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="04d0f-178">Manage Office 365 with Office 365 PowerShell</span></span>](manage-office-365-with-office-365-powershell.md)
  
[<span data-ttu-id="04d0f-179">Introducción a PowerShell de Office 365</span><span class="sxs-lookup"><span data-stu-id="04d0f-179">Getting started with Office 365 PowerShell</span></span>](getting-started-with-office-365-powershell.md)
  
[<span data-ttu-id="04d0f-180">Conectarse a todos los servicios de Office 365 en una sola ventana de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="04d0f-180">Connect to all Office 365 services in a single Windows PowerShell window</span></span>](connect-to-all-office-365-services-in-a-single-windows-powershell-window.md)
#### 

[<span data-ttu-id="04d0f-181">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="04d0f-181">Get-Credential</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389618)
  
[<span data-ttu-id="04d0f-182">MsolService conectar</span><span class="sxs-lookup"><span data-stu-id="04d0f-182">Connect-MsolService</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532375)
