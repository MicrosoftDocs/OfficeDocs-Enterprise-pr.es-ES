---
title: "Implementar Sincronización de directorios (DirSync) de Office 365 en Microsoft Azure"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 9/7/2017
ms.audience: ITPro
ms.topic: concetpual
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Ent_O365
- Ent_O365_Top
ms.custom:
- DecEntMigration
- Strat_O365_Enterprise
- Ent_Solutions
ms.assetid: b8464818-4325-4a56-b022-5af1dad2aa8b
---

# Implementar Sincronización de directorios (DirSync) de Office 365 en Microsoft Azure

 **Resumen:** Implemente Azure AD Connect (DirSync) en una máquina virtual en Azure para sincronizar las cuentas entre el directorio local y el inquilino de Azure AD con su suscripción de Office 365.
  
Azure Active Directory (AD) Connect (antes conocida como herramienta de sincronización de directorios, herramienta de DirSync o herramienta DirSync.exe) es una aplicación basada en servidor que se instala en un servidor unido a un dominio para sincronizar a los usuarios de Windows Server Active Directory local con el inquilino de Azure Active Directory de su suscripción a Office 365. Puede instalar Azure AD Connect en un servidor local, pero también puede instalarlo en una máquina virtual en Azure por los siguientes motivos:
  
- Puede aprovisionar y configurar los servidores basados en la nube con mayor rapidez, y conseguir así que los servicios estén disponibles para los usuarios mucho antes.
    
- Azure ofrece mejor disponibilidad de sitios con menos esfuerzo.
    
- Puede reducir el número de servidores locales de su organización.
    
En este artículo:
  
- [Introducción a la implementación de sincronización de directorios de Office 365 en Azure](deploy-office-365-directory-synchronization-dirsync-in-microsoft-azure.md#Overview)
    
- [Planeación para hospedar un servidor de DirSync para Office 365 en Azure](deploy-office-365-directory-synchronization-dirsync-in-microsoft-azure.md#PlanningVirtual)
    
- Guía de implementación
    
> [!IMPORTANT]
> Esta solución requiere conectividad entre la red local y la red virtual de Azure. Para más información, vea [Conectar una red local con una red virtual de Microsoft Azure](81190961-5454-4a5c-8b0e-6ae75b9fb035.md).
  
> [!IMPORTANT]
> En este artículo se describe la sincronización de un único dominio en un único bosque. Azure AD Connect sincroniza todos los dominios de Windows Server AD en el bosque de Active Directory con Office 365. Si tiene varios bosques de Active Directory para sincronizar con Office 365, consulte el tema [Integración de las identidades locales con Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=393091).
  
> [!NOTE]
> Office 365 usa Azure Active Directory (Azure AD) para su servicio de directorio. La suscripción a Office 365 incluye un inquilino de Azure AD. Este inquilino también puede usarse para la administración de identidades de la organización con otras cargas de trabajo en la nube, incluidas otras aplicaciones SaaS y aplicaciones de Azure.
  
## Introducción a la implementación de sincronización de directorios de Office 365 en Azure
<a name="Overview"> </a>

El siguiente diagrama muestra Azure Connect de AD se ejecuta en una máquina virtual en Azure (el servidor de sincronización de directorios) que sincroniza un bosque de Windows Server AD local a una suscripción deOffice 365.
  
![Herramienta Azure AD Connect en una máquina virtual en Azure durante la sincronización de cuentas locales con el inquilino de Azure AD de una suscripción a Office 365 con flujo de tráfico.](images/CP_DirSyncOverview.png)
  
En el diagrama, hay dos redes conectadas por una conexión de sitio a sitio VPN o ExpressRoute. Hay una red local donde se encuentran los controladores de dominio de AD de Windows Server, y hay una red virtual de Azure con un servidor de sincronización de directorios, que es una máquina virtual ejecuta [Azure Connect AD](https://www.microsoft.com/download/details.aspx?id=47594). Hay dos flujos de tráfico principal original desde el servidor de sincronización de directorios:
  
- Azure AD Connect consulta un controlador de dominio en la red local para conocer los cambios de cuentas y contraseñas.
    
- Azure AD Connect envía los cambios de cuentas y contraseñas a la instancia de Azure AD de su suscripción de Office 365. Como el servidor de DirSync se encuentra en una parte extendida de la red local, estos cambios se envían a través del servidor proxy de la red local.
    
> [!NOTE]
> En esta solución se describe la sincronización de un único dominio de Active Directory en un único bosque de Active Directory. Azure AD Connect sincroniza todos los dominios de Active Directory en el bosque de Active Directory con Office 365. Si tiene varios bosques de Active Directory para sincronizar con Office 365, consulte [Integración de las identidades locales con Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=393091).
  
En ambos casos, el tráfico originado por Azure AD Connect que se ejecuta en la máquina virtual de Azure se reenvía a una puerta de enlace en la red virtual en Azure, que luego reenvía el tráfico a través de la conexión VPN de sitio a sitio o ExpressRoute en el dispositivo de puerta de enlace de VPN de la red local. Después, la infraestructura de enrutamiento de la red local reenvía el tráfico a su destino, como un controlador de dominio o un servidor proxy.
  
Existen dos pasos principales cuando implementa esta solución:
  
1. Crear una red virtual de Azure y establecer una conexión VPN de sitio a sitio en su red local. Para obtener más información, consulte [Conectar una red local con una red virtual de Microsoft Azure](81190961-5454-4a5c-8b0e-6ae75b9fb035.md).
    
2. Instalar [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) en una máquina virtual unida a un dominio en Azure y después sincronizar Windows Server AD local con Office 365. Esto conlleva lo siguiente:
    
1. Crear una Máquina virtual de Azure para ejecutar Azure AD Connect.
    
2. Instalar y configurar [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).
    
    Configurar Azure AD Connect requiere las credenciales (nombre de usuario y contraseña) de una cuenta de administrador de Azure AD y una cuenta de administrador empresarial de Windows Server AD. Azure AD Connect se ejecuta inmediatamente y de forma continuada para sincronizar el bosque de Windows Server AD local con Office 365.
    
Antes de implementar esta solución en producción, utilice las instrucciones en [Sincronización de directorios (DirSync) para el entorno de desarrollo y pruebas de Office 365](dirsync-for-your-office-365-dev-test-environment.md) para establecer esta configuración como una prueba de concepto para demostraciones, o para la experimentación.
  
> [!IMPORTANT]
> Cuando la configuración de Azure AD Connect se completa, no guarda las credenciales de la cuenta de administrador empresarial de Windows Server AD.
  
> [!NOTE]
> Esta solución describe la sincronización de un único bosque de Windows Server AD a Office 365. La topología que se describen en este artículo representa sólo una manera de implementar esta solución. La topología de su organización puede diferir en función de sus requisitos de red únicos y consideraciones de seguridad.
  
## Planeación para hospedar un servidor de DirSync para Office 365 en Azure
<a name="PlanningVirtual"> </a>

### Requisitos previos

Antes de comenzar, revise los siguientes requisitos previos para esta solución:
  
- Revise el contenido de planeación relacionado en el tema sobre la [Planear la red virtual de Azure](81190961-5454-4a5c-8b0e-6ae75b9fb035.md#PlanningVirtual).
    
- Asegúrese de que cumple todos los [requisitos previos](http://technet.microsoft.com/library/81190961-5454-4a5c-8b0e-6ae75b9fb035%28v=office.15%29.aspx#Prerequisites) para configurar la red virtual de Azure.
    
- Consiga una suscripción a Office 365 que incluya la característica de integración de Active Directory. Para obtener más información sobre las suscripciones de Office 365, vaya a la [página de suscripción de Office 365](https://go.microsoft.com/fwlink/p/?LinkId=394278).
    
- Aprovisione una Máquina virtual de Azure que ejecute Azure AD Connect para sincronizar el bosque de Windows Server AD local con Office 365.
    
    Debe tener las credenciales (nombres y contraseñas) de la cuenta de administrador empresarial de Windows Server AD y una cuenta de administrador de Azure Active Directory.
    
### Suposiciones de diseño de la arquitectura de la solución

En la siguiente lista se describen las elecciones de diseño que se han tomado para esta solución.
  
- Esta solución usa una sola red virtual de Azure con una conexión VPN de sitio a sitio. La red virtual de Azure hospeda una sola subred que contiene un servidor, el servidor de DirSync que ejecuta Azure AD Connect.
    
- En la red local, hay un controlador de dominio y servidores DNS.
    
- Azure AD Connect realiza la sincronización de contraseñas en lugar del inicio de sesión único. No es necesario implementar una infraestructura de Servicios de federación de Active Directory (AD FS). Para obtener más información sobre la sincronización de contraseñas y las opciones de inicio de sesión único, consulte [Determine qué escenario de integración de directorios se debe usar](https://go.microsoft.com/fwlink/p/?LinkId=393094).
    
Hay otras opciones de diseño adicionales que puede tener en cuenta cuando implementa esta solución en su entorno. Se incluyen las siguientes:
  
- Si hay servidores DNS en una red virtual existente de Azure, determine si desea que el servidor DirSync los use para la resolución de nombres, en lugar de usar los servidores DNS de la red local.
    
- Si hay controladores de dominio en una red virtual existente de Azure, determine si la configuración de Sitios y servicios de Active Directory puede suponer una mejor opción. El servidor de DirSync puede consultar los controladores de dominio de la red virtual de Azure para buscar cambios en las cuentas y las contraseñas, en lugar de los controladores de dominio en la red local.
    
## Guía de implementación
<a name="DeploymentRoadmap"> </a>

La implementación de Azure AD Connect en una máquina virtual en Azure consta de tres fases:
  
- Fase 1: Creación y configuración de la red virtual de Azure
    
- Fase 2: Creación y configuración de la máquina virtual de Azure
    
- Fase 3: Instalar y configurar Azure AD Connect
    
Después de la implementación, también debe asignar ubicaciones y licencias para las nuevas cuentas de usuario en Office 365.
  
> [!TIP]
> El [Kit de implementación de DirSync Server en Azure](https://gallery.technet.microsoft.com/DirSync-Server-in-Azure-32cb2ded) contiene todos los bloques de Azure PowerShell necesarios para compilar esta solución, los diagramas en formato de Microsoft PowerPoint y Visio y un libro de configuración de Excel que genera bloques de comandos de Azure PowerShell personalizados según su configuración.
  
### Fase 1: Creación y configuración de la red virtual de Azure

Para crear y configurar la red virtual de Azure, complete la [fase 1: preparar la red local ](http://technet.microsoft.com/library/81190961-5454-4a5c-8b0e-6ae75b9fb035%28v=office.15%29.aspx#Phase1) y la[fase 2: crear la red virtual entre entornos locales en Azure](http://technet.microsoft.com/library/81190961-5454-4a5c-8b0e-6ae75b9fb035%28v=office.15%29.aspx#Phase2) de la guía de implementación de[Conectar una red local con una red virtual de Microsoft Azure](81190961-5454-4a5c-8b0e-6ae75b9fb035.md).
  
Esta es la configuración resultante.
  
![Fase 1 del servidor de sincronización de directorios para Office 365 alojado en Azure](images/aab6a9a4-eb78-4d85-9b96-711e6de420d7.png)
  
En esta figura se muestra una red local conectada a una red virtual de Azure mediante una conexión de ExpressRoute o VPN de sitio a sitio.
  
### Fase 2: Creación y configuración de la máquina virtual de Azure

Cree la máquina virtual en Azure con las instrucciones [Creación de la primera máquina virtual de Windows en Azure Portal](https://go.microsoft.com/fwlink/p/?LinkId=393098). Use la configuración siguiente:
  
- En el panel **Datos básicos**, seleccione la misma suscripción, ubicación y grupo de recursos que la red virtual. Registre el nombre de usuario y la contraseña en un lugar seguro. Los necesitará posteriormente para conectarse a la máquina virtual.
    
- En el panel **Elija un tamaño**, seleccione el tamaño **A2 estándar**.
    
- En el panel **Configuración**, en la sección **Almacenamiento**, seleccione el tipo de almacenamiento **Estándar**. En la sección **Red**, seleccione el nombre de la red virtual y la subred que van a hospedar el servidor de DirSync (no la subred de puerta de enlace). Deje todas las demás opciones con sus valores predeterminados.
    
Compruebe que el servidor de DirSync use DNS correctamente. Para ello, compruebe su DNS interno para asegurarse de que se ha agregado un registro de dirección (A) para la máquina virtual con su dirección IP.
  
Use las instrucciones de [Conexión a la máquina virtual e inicio de sesión](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-hero-tutorial?toc=%2fazure%2fvirtual-machines%2fwindows%2ftoc.json#connect-to-the-virtual-machine-and-sign-on) para conectarse al servidor de DirSync con una conexión a Escritorio remoto. Después de iniciar sesión, una la máquina virtual al dominio de Windows Server AD local.
  
Para que Azure AD Connect obtenga acceso a recursos de Internet, debe configurar el servidor DirSync de modo que use el servidor proxy de la red local. Póngase en contacto con su administrador de red para conocer los pasos de configuración adicionales que debe realizar.
  
Esta es la configuración resultante.
  
![Fase 2 del servidor de sincronización de directorios para Office 365 alojado en Azure](images/9d8c9349-a207-4828-9b2b-826fe9c06af3.png)
  
En esta figura se muestra la máquina virtual del servidor de DirSync en la red virtual de Azure entre locales.
  
### Fase 3: Instalar y configurar Azure AD Connect

Haga lo siguiente:
  
1. Conéctese al servidor de DirSync mediante una conexión a Escritorio remoto con una cuenta de dominio de Windows Server AD que tenga privilegios de administrador local. Consulte [Conexión a la máquina virtual e inicio de sesión](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-hero-tutorial?toc=%2fazure%2fvirtual-machines%2fwindows%2ftoc.json#connect-to-the-virtual-machine-and-sign-on).
    
2. Desde el servidor de sincronización de directorios, abra el artículo [Configurar la sincronización de directorios en Office 365](https://support.office.com/article/Set-up-directory-synchronization-in-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846) y siga las instrucciones relativas a la sincronización de directorios con la sincronización de contraseñas.
    
> [!CAUTION]
> El programa de instalación crea la cuenta **AAD_xxxxxxxxxxxx** en la unidad organizativa (UO) de usuarios locales. No mueva ni quite esta cuenta porque entonces se producirá un error de sincronización.
  
Esta es la configuración resultante.
  
![Fase 3 del servidor de sincronización de directorios para Office 365 alojado en Azure](images/3f692b62-b77c-4877-abee-83c7edffa922.png)
  
En esta figura se muestra el servidor de DirSync con Azure AD Connect en la red virtual de Azure entre locales.
  
### Asignar ubicaciones y licencias a los usuarios de Office 365

Azure AD Connect agrega cuentas a su suscripción de Office 365 desde Windows Server AD local, pero para que los usuarios inicien sesión en Office 365 y usen sus servicios, las cuentas deben configurarse con una ubicación y licencias. Use estos pasos para agregar la ubicación y activar las licencias para las cuentas de usuario adecuadas:
  
1. Inicie sesión en la [página del Portal de Office 365](https://portal.office.com) y, después, haga clic en **Administrador**.
    
2. En el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.
    
3. En la lista de las cuentas de usuarios, seleccione la casilla junto al usuario que quiere activar.
    
4. En la página del usuario, haga clic en **Editar** para **Licencias de productos**.
    
5. En la página **Licencias de productos**, seleccione una ubicación para el usuario en **Ubicación** y, después, habilite las licencias adecuadas para el usuario.
    
6. Cuando finalice, haga clic en **Guardar** y, después, haga clic en **Cerrar** dos veces.
    
7. Vuelva al paso 3 para usuarios adicionales.
    
## See Also
<a name="DeploymentRoadmap"> </a>

#### 

[Adopción de la nube y soluciones híbridas](cloud-adoption-and-hybrid-solutions.md)
  
[Conectar una red local con una red virtual de Microsoft Azure](81190961-5454-4a5c-8b0e-6ae75b9fb035.md)
#### 

[Descargar Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594)
  
[Configurar la sincronización de directorios en Office 365](https://support.office.com/article/Set-up-directory-synchronization-in-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)
  
[Kit de implementación de DirSync Server en Azure](https://gallery.technet.microsoft.com/DirSync-Server-in-Azure-32cb2ded)

