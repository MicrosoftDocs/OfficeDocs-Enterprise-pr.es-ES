---
title: Intervalos de direcciones IP y URL de Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 8/13/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: 'Resumen: Office 365 necesita conectividad a Internet. Los siguientes puntos de conexión deben resultar accesibles para los clientes que usan planes de Office 365, incluida la nube de la comunidad de administración pública (GCC).'
hideEdit: true
ms.openlocfilehash: 2e6f5afd097aa85c09847b58fd3166961116b773
ms.sourcegitcommit: 69d60723e611f3c973a6d6779722aa9da77f647f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22543008"
---
# <a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="1c9a2-104">Intervalos de direcciones IP y URL de Office 365</span><span class="sxs-lookup"><span data-stu-id="1c9a2-104">Office 365 URLs and IP address ranges</span></span>

 <span data-ttu-id="1c9a2-p102">**Resumen:** Office 365 necesita conectividad a Internet. Los siguientes puntos de conexión deben resultar accesibles para los clientes que usan planes de Office 365, incluida la nube de la comunidad de administración pública (GCC).</span><span class="sxs-lookup"><span data-stu-id="1c9a2-p102">**Summary:** Office 365 requires connectivity to the Internet. The endpoints below should be reachable for customers using Office 365 plans, including Government Community Cloud (GCC).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1c9a2-p103">Microsoft está desarrollando un servicio web basado en REST para las direcciones IP y las entradas FQDN de esta página. Este servicio le ayudará a configurar y actualizar dispositivos de perímetro de red, como firewalls y servidores proxy. Puede descargar la lista de puntos de conexión, la versión actual de la lista o cambios específicos. Este servicio acabará reemplazando al documento XML que se vincula desde esta página. Para probar este nuevo servicio, vaya a [Servicio web](managing-office-365-endpoints.md#webservice).</span><span class="sxs-lookup"><span data-stu-id="1c9a2-p103">Microsoft is developing a REST-based web service for the IP address and FQDN entries on this page. This new service will help you configure and update network perimeter devices such as firewalls and proxy servers. You can download the list of endpoints, the current version of the list, or specific changes. This service will eventually replace the XML document linked from this page. To try out this new service, go to [Web service](managing-office-365-endpoints.md#webservice).</span></span> 
  
<span data-ttu-id="1c9a2-112">*Office 365 mundial (incluido GCC)* | [Office 365 operado por 21Vianet ](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](office-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](office-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](office-365-u-s-government-gcc-high-endpoints.md) |</span><span class="sxs-lookup"><span data-stu-id="1c9a2-112">*Office 365 Worldwide (+GCC)* | [Office 365 operated by 21 Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](office-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](office-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](office-365-u-s-government-gcc-high-endpoints.md) |</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="1c9a2-113">**Última actualización:** 1/8/2018 - ![RSS](media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Suscripción del registro de cambios](https://go.microsoft.com/fwlink/p/?linkid=236301)</span><span class="sxs-lookup"><span data-stu-id="1c9a2-113">**Last updated:** 8/1/2018 - ![RSS](media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Change Log subscription](https://go.microsoft.com/fwlink/p/?linkid=236301)</span></span> <br/> |<span data-ttu-id="1c9a2-114">**Descargue:** todos los destinos obligatorios y opcionales en una lista de [formato XML](https://go.microsoft.com/fwlink/?LinkId=533185).</span><span class="sxs-lookup"><span data-stu-id="1c9a2-114">**Download:** all required and optional destinations in one [XML formatted](https://go.microsoft.com/fwlink/?LinkId=533185) list.</span></span>  <br/> | <span data-ttu-id="1c9a2-115">**Use:** nuestros [archivos PAC](managing-office-365-endpoints.md#pacfiles) de proxy</span><span class="sxs-lookup"><span data-stu-id="1c9a2-115">**Use:** our proxy [PAC files](managing-office-365-endpoints.md#pacfiles)</span></span> <br/> |
   
 <span data-ttu-id="1c9a2-p104">Comience con [Administrar los puntos de conexión de Office 365](managing-office-365-endpoints.md) si desea entender nuestras recomendaciones para administrar la conectividad de red con estos datos. Los datos de puntos de conexión se actualizan al principio de cada mes con las nuevas direcciones IP y URL publicadas 30 días antes de su activación. Esto permite que los clientes que todavía no han automatizado las actualizaciones completen los procesos antes de que se requiera una nueva conectividad. Los puntos de conexión también pueden actualizarse durante el mes si fuera necesario para gestionar escalaciones de soporte técnico, incidentes de seguridad u otros requisitos operativos inmediatos. Los datos que aparecen en la página siguiente se generan desde los servicios web basados en REST. Si usa un dispositivo de red o un script para obtener acceso a estos datos, vaya directamente al [Servicio web](managing-office-365-endpoints.md#webservice).</span><span class="sxs-lookup"><span data-stu-id="1c9a2-p104">Start with [Managing Office 365 endpoints](managing-office-365-endpoints.md) to understand our recommendations for managing network connectivity using this data. Endpoints data is updated at the beginning of each month with new IP Addresses and URLs published 30 days in advance of being active. This allows for customers who do not yet have automated updates to complete their processes before new connectivity is required. Endpoints may also be updated during the month if needed to address support escalations, security incidents, or other immediate operational requirements. The data shown on this page below is all generated from the REST-based web services. If you are using a script or a network device to access this data, you should go to the [Web service](managing-office-365-endpoints.md#webservice) directly.</span></span>

<span data-ttu-id="1c9a2-p105">Los siguientes datos de puntos de conexión enumeran los requisitos para la conectividad del equipo de un usuario a Office 365. No incluye las conexiones de red de Microsoft a una red de clientes, a veces denominadas híbridas o conexiones de red de entrada.</span><span class="sxs-lookup"><span data-stu-id="1c9a2-p105">Endpoint data below lists requirements for connectivity from a user’s machine to Office 365. It does not include network connections from Microsoft into a customer network, sometimes called hybrid or inbound network connections.</span></span>

<span data-ttu-id="1c9a2-p106">Los puntos de conexión se agrupan en cuatro áreas de servicio. Las tres primeras se pueden seleccionar por separado para la conectividad; la cuarta área de servicio es una dependencia común (denominada de Microsoft 365 Common y Office Online) y debe disponer de conectividad de red en todo momento.</span><span class="sxs-lookup"><span data-stu-id="1c9a2-p106">The endpoints are grouped into four service areas. The first three service areas can be independently selected for connectivity. The fourth service area is a common dependency (called Microsoft 365 Common and Office Online) and must always have network connectivity.</span></span>

<span data-ttu-id="1c9a2-127">Estas son columnas de datos que se muestran:</span><span class="sxs-lookup"><span data-stu-id="1c9a2-127">Data columns shown are:</span></span>

- <span data-ttu-id="1c9a2-p107">**ID**: el número de identificación de la fila, también conocido como un conjunto de puntos de conexión. Este identificador es el mismo que devuelve el servicio web para el conjunto de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="1c9a2-p107">**ID**: The ID number of the row, also known as an endpoint set. This ID is the same as is returned by the web service for the endpoint set.</span></span>

- <span data-ttu-id="1c9a2-p108">**Categoría**: muestra si el conjunto de puntos de conexión se clasifica como "Optimizar", "Permitir" o "Predeterminado". Puede leer acerca de estas categorías y encontrar indicaciones para su administración en [http://aka.ms/pnc](http://aka.ms/pnc). Esta columna también muestra los conjuntos de puntos de conexión que deben tener conectividad de red. Para los conjuntos de puntos de conexión que no necesitan conectividad de red, le proporcionamos notas en este campo para indicar qué funcionalidad faltaría si se bloqueara el conjunto de puntos de conexión. Si va a excluir un área de servicio completa, los conjuntos de puntos de conexión enumerados como necesarios no necesitan conectividad.</span><span class="sxs-lookup"><span data-stu-id="1c9a2-p108">**Category**: Shows whether the endpoint set is categorized as “Optimize”, “Allow”, or “Default”. You can read about these categories and guidance for management of them at [http://aka.ms/pnc](http://aka.ms/pnc). This column also lists which endpoint sets are required to have network connectivity. For endpoint sets which are not required to have network connectivity, we provide notes in this field to indicate what functionality would be missing if the endpoint set is blocked. If you are excluding an entire service area, the endpoint sets listed as required do not require connectivity.</span></span>

- <span data-ttu-id="1c9a2-p109">**EMERGENCIA**: aparece como **Sí** si el conjunto de puntos de conexión se admite en Azure ExpressRoute con prefijos de ruta de Office 365. La comunidad de BGP que incluye los prefijos de ruta que aparecen se alinea con el área de servicio que se muestra. Si EMERGENCIA aparece como **No**, esto significa que ExpressRoute no es compatible con este conjunto de puntos de conexión. Sin embargo, no se debe dar por hecho que no se anuncia ninguna ruta para un conjunto de puntos de conexión cuando EMERGENCIA se establezca como **No**.</span><span class="sxs-lookup"><span data-stu-id="1c9a2-p109">**ER**: This is **Yes** if the endpoint set is supported over Azure ExpressRoute with Office 365 route prefixes. The BGP community that includes the route prefixes shown aligns with the service area listed. When ER is **No**, this means that ExpressRoute is not supported for this endpoint set. However, it should not be assumed that no routes are advertised for an endpoint set where ER is **No**.</span></span>

- <span data-ttu-id="1c9a2-p110">**Direcciones**: enumera los FQDN o nombres de dominio con caracteres comodín y los intervalos de direcciones IP para el conjunto de puntos de conexión. Tenga en cuenta que un intervalo de direcciones IP está en formato CIDR y puede incluir varias direcciones IP individuales en la red especificada.</span><span class="sxs-lookup"><span data-stu-id="1c9a2-p110">**Addresses**: Lists the FQDNs or wildcard domain names and IP Address ranges for the endpoint set. Note that an IP Address range is in CIDR format and may include many individual IP Addresses in the specified network.</span></span>
 
- <span data-ttu-id="1c9a2-p111">**Puertos**: muestra los puertos TCP o UDP que se combinan con las direcciones para formar el punto de conexión de la red. Es posible que observe repeticiones de intervalos de direcciones IP cuando se enumeran diferentes puertos.</span><span class="sxs-lookup"><span data-stu-id="1c9a2-p111">**Ports**: Lists the TCP or UDP ports that are combined with the Addresses to form the network endpoint. You may notice some duplication in IP Address ranges where there are different ports listed.</span></span>

[!INCLUDE [Office 365 worldwide endpoints](./includes/office-365-worldwide-endpoints.md)]

## <a name="related-topics"></a><span data-ttu-id="1c9a2-143">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1c9a2-143">Related Topics</span></span>

[<span data-ttu-id="1c9a2-144">Administrar puntos de conexión de Office 365</span><span class="sxs-lookup"><span data-stu-id="1c9a2-144">Office 365 Germany endpoints</span></span>](managing-office-365-endpoints.md)
  
[<span data-ttu-id="1c9a2-145">Solución de problemas de conectividad de Office 365</span><span class="sxs-lookup"><span data-stu-id="1c9a2-145">Office 365 connectivity limits</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d.aspx)
  
[<span data-ttu-id="1c9a2-146">Conectividad de clientes</span><span class="sxs-lookup"><span data-stu-id="1c9a2-146">Client connectivity</span></span>](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[<span data-ttu-id="1c9a2-147">Redes de entrega de contenido</span><span class="sxs-lookup"><span data-stu-id="1c9a2-147">Content delivery networks</span></span>](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[<span data-ttu-id="1c9a2-148">Intervalos IP del centro de datos de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="1c9a2-148">Microsoft Azure Datacenter IP Ranges</span></span>](https://www.microsoft.com/download/details.aspx?id=41653)
  
[<span data-ttu-id="1c9a2-149">Espacio IP público de Microsoft</span><span class="sxs-lookup"><span data-stu-id="1c9a2-149">Microsoft Public IP Space</span></span>](https://www.microsoft.com/download/details.aspx?id=53602)
