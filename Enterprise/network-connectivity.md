---
title: Conectividad de red a Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/2/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 64b420ef-0218-48f6-8a34-74bb27633b10
description: Office 365 está diseñado para permitir a los clientes de todo el mundo para conectarse al servicio con una conexión a internet. A medida que evoluciona el servicio, la seguridad, rendimiento y confiabilidad de Office 365 se han mejorado en función de los clientes que usen internet para establecer una conexión al servicio.
ms.openlocfilehash: b72b0a4584542e4c8673c7cf009c66aa97c6b81c
ms.sourcegitcommit: 69d60723e611f3c973a6d6779722aa9da77f647f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22542944"
---
# <a name="network-connectivity-to-office-365"></a><span data-ttu-id="abaf6-104">Conectividad de red a Office 365</span><span class="sxs-lookup"><span data-stu-id="abaf6-104">Network connectivity to Office 365</span></span>

<span data-ttu-id="abaf6-p102">Office 365 está diseñado para permitir a los clientes de todo el mundo para conectarse al servicio con una conexión a internet. A medida que evoluciona el servicio, la seguridad, rendimiento y confiabilidad de Office 365 se han mejorado en función de los clientes que usen internet para establecer una conexión al servicio.</span><span class="sxs-lookup"><span data-stu-id="abaf6-p102">Office 365 is designed to enable customers all over the world to connect to the service using an internet connection. As the service evolves, the security, performance, and reliability of Office 365 are improved based on customers using the internet to establish a connection to the service.</span></span>
  
<span data-ttu-id="abaf6-p103">Los clientes que planean usar Office 365 deben evaluar sus necesidades de conectividad de internet existentes y previstas como parte del proyecto de implementación. Para las implementaciones de clase empresarial confiable y tamaño adecuado la conectividad a internet es una parte fundamental de consumo de escenarios y las características de Office 365.</span><span class="sxs-lookup"><span data-stu-id="abaf6-p103">Customers planning to use Office 365 should assess their existing and forecasted internet connectivity needs as a part of the deployment project. For enterprise class deployments reliable and appropriately sized internet connectivity is a critical part of consuming Office 365 features and scenarios.</span></span>
  
<span data-ttu-id="abaf6-p104">Muchas personas diferentes y las organizaciones según el tamaño y las preferencias se pueden realizar las evaluaciones de la red. El ámbito de la evaluación de red también puede variar dependiendo de dónde está en proceso de implementación de. Para ayudar a obtener una mejor comprensión de lo que se necesita para realizar una evaluación de la red, nos hemos producido una guía de evaluación de la red para ayudarle a comprender las opciones disponibles para usted. Esta evaluación determina qué pasos y recursos deben agregarse al proyecto de implementación para que pueda adoptar correctamente Office 365.</span><span class="sxs-lookup"><span data-stu-id="abaf6-p104">Network evaluations can be performed by many different people and organizations depending on your size and preferences. The network scope of the assessment can also vary depending on where you're at in your deployment process. To help you get a better understanding of what it takes to perform a network assessment, we've produced a network assessment guide to help you understand the options available to you. This assessment will determine what steps and resources need to be added to the deployment project to enable you to successfully adopt Office 365.</span></span>
  
<span data-ttu-id="abaf6-p105">Una evaluación integral de la red, al igual que esos DCI prescritos el [Skype Operations Framework](https://www.skypeoperationsframework.com/) proporcionará las posibles soluciones para redes retos de diseño junto con los detalles de la implementación. La mayoría de las evaluaciones de red que le indicará que se puede acomodar más conectividad de red a Office 365 con [configuración secundaria o cambios de diseño](https://aka.ms/manageo365endpoints) a la red existente y la infraestructura de salida de internet.</span><span class="sxs-lookup"><span data-stu-id="abaf6-p105">A comprehensive network assessment, like those prescribed inn the [Skype Operations Framework](https://www.skypeoperationsframework.com/) will provide possible solutions to networking design challenges along with implementation details. Most network assessments will indicate network connectivity to Office 365 can be accommodated with [minor configuration or design changes](https://aka.ms/manageo365endpoints) to the existing network and internet egress infrastructure.</span></span>

<span data-ttu-id="abaf6-p106">Algunos evaluaciones indicará la conectividad de red a Office 365 requiere las inversiones adicionales en componentes de red. Por ejemplo, las inversiones en infraestructura de enrutamiento optimizada para admitir la conectividad a internet a Office 365 o ancho de banda de WAN. En ocasiones, una evaluación indicará la conectividad de red a Office 365 está influenciada por Reglamento o el rendimiento de los requisitos para escenarios como [Skype para calidad de medios en línea de negocio](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917). Estos requisitos adicionales que puede producir las inversiones en infraestructura de conectividad a internet, optimización de enrutamiento y la conectividad directa especializada.</span><span class="sxs-lookup"><span data-stu-id="abaf6-p106">Some assessments will indicate network connectivity to Office 365 will require additional investments in networking components. For example, investments in WAN bandwidth or optimized routing infrastructure to support internet connectivity to Office 365. Occasionally an assessment will indicate network connectivity to Office 365 is influenced by regulation or performance requirements for scenarios such as [Skype for Business Online media quality](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917). These additional requirements may lead to investments in internet connectivity infrastructure, routing optimization, and specialized direct connectivity.</span></span>
  
> [!NOTE]
> <span data-ttu-id="abaf6-p107">Microsoft puede cambiar cómo se revisa el dominio de enrutamiento de Microsoft Peering para ExpressRoute de Azure. Iniciar el 31 de julio de 2017, todos los clientes de Azure ExpressRoute pueden habilitar Microsoft Peering directamente desde la consola administrativa de Azure o a través de PowerShell. Después de habilitar Microsoft Peering, cualquier cliente puede crear filtros de ruta para recibir los anuncios de rutas BGP para las aplicaciones de contratación del cliente de Dynamics 365 (anteriormente conocidos como CRM Online). Los clientes que necesitan ExpressRoute de Azure para Office 365 deben obtener la revisión de Microsoft antes de que pueden crear filtros de ruta para Office 365. Póngase en contacto con su equipo de Account de Microsoft para obtener más información acerca de cómo solicitar una revisión para habilitar ExpressRoute de Office 365. Las suscripciones no autorizadas intenta crear filtros de ruta para Office 365 recibirá un [mensaje de error](https://support.microsoft.com/kb/3181709).</span><span class="sxs-lookup"><span data-stu-id="abaf6-p107">Microsoft changed how the Microsoft Peering routing domain is reviewed for Azure ExpressRoute. Starting July 31st, 2017, all Azure ExpressRoute customers can enable Microsoft Peering directly from the Azure Administrative console or via PowerShell. After enabling Microsoft Peering, any customer can create route filters to receive BGP route advertisements for Dynamics 365 Customer Engagement applications (formerly known as CRM Online). Customers needing Azure ExpressRoute for Office 365 must obtain review from Microsoft before they can create route filters for Office 365. Please contact your Microsoft Account team to learn about how to request a review for enabling Office 365 ExpressRoute. Unauthorized subscriptions trying to create route filters for Office 365 will receive an [error message](https://support.microsoft.com/kb/3181709).</span></span>
  
<span data-ttu-id="abaf6-125">Puntos claves a tener en cuenta al planear la evaluación de la red para Office 365:</span><span class="sxs-lookup"><span data-stu-id="abaf6-125">Key points to consider when planning your network assessment for Office 365:</span></span>
  
- <span data-ttu-id="abaf6-p108">Office 365 es un servicio segura, confiable y de alto rendimiento que se ejecuta a través de internet pública. Se seguirán invertir para mejorar estos aspectos del servicio. Todos los servicios de Office 365 están disponibles a través de la conectividad a internet.</span><span class="sxs-lookup"><span data-stu-id="abaf6-p108">Office 365 is a secure, reliable, high performance service that runs over the public internet. We continue to invest to enhance these aspects of the service. All Office 365 services are available via internet connectivity.</span></span>

- <span data-ttu-id="abaf6-p109">Constantemente estamos optimizando principales llegar aspectos de Office 365 como la disponibilidad, global y rendimiento para internet en función de conectividad. Por ejemplo, muchos de los servicios de Office 365 sacar provecho de un conjunto de expansión de internet conexión a nodos perimetrales. Esta red perimetral ofrece la mejor proximidad y rendimiento para conexiones procedentes a través de internet.</span><span class="sxs-lookup"><span data-stu-id="abaf6-p109">We are continually optimizing core aspects of Office 365 such as availability, global reach, and performance for internet based connectivity. For example, many Office 365 services leverage an expanding set of internet facing edge nodes. This edge network offers the best proximity and performance to connections coming over the internet.</span></span>

- <span data-ttu-id="abaf6-p110">Cuando se plantee con Office 365 para cualquiera de los servicios incluidos como Skype para capacidades de vídeo o convocatorias de reunión en línea de negocio de voz, los clientes deben completar una evaluación de la red de extremo a extremo y cumplir los requisitos de uso de nuestro Skype Operations Framework. Estos clientes dispone de varias opciones para satisfacer los requisitos específicos para la conectividad de la nube, incluyendo ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="abaf6-p110">When considering using Office 365 for any of the included services such as Skype for Business Online voice, video, or meeting capabilities, customers must complete an end to end network assessment and meet requirements using our Skype Operations Framework. These customers will have several options to meet specific requirements for cloud connectivity, including ExpressRoute.</span></span>

<span data-ttu-id="abaf6-p111">Eche un vistazo a estudio de caso de Microsoft [optimizar el rendimiento de red para Microsoft Office 365](https://msdn.microsoft.com/en-us/library/mt450488.aspx). Si va a evaluar Office 365 y no está seguro de que dónde empezar con la evaluación de la red o han encontrado el diseño de la red desafíos que necesita ayuda para superar, trabajar con su equipo de cuentas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="abaf6-p111">Have a look at Microsoft's case study [Optimizing network performance for Microsoft Office 365](https://msdn.microsoft.com/en-us/library/mt450488.aspx). If you're evaluating Office 365 and aren't sure where to begin with your network assessment or have found network design challenges that you need assistance to overcome, please work with your Microsoft account team.</span></span>
  
<span data-ttu-id="abaf6-p112">Además, lea [Principios de conectividad de red de Office 365](https://aka.ms/o365networkingprinciples) para comprender los principios de conectividad para administrar de forma segura el tráfico de Office 365 y obtener el mejor rendimiento posible. En este artículo le ayudará a comprender las instrucciones más reciente para optimizar de forma segura conectividad de red de Office 365.</span><span class="sxs-lookup"><span data-stu-id="abaf6-p112">Also, read [Office 365 Network Connectivity Principles](https://aka.ms/o365networkingprinciples) to understand the connectivity principles for securely managing Office 365 traffic and getting the best possible performance. This article will help you understand the most recent guidance for securely optimizing Office 365 network connectivity.</span></span>
  
<span data-ttu-id="abaf6-138">Éste es un vínculo corto que puede usar para volver: [ https://aka.ms/o365networkconnectivity.](https://aka.ms/o365networkconnectivity)</span><span class="sxs-lookup"><span data-stu-id="abaf6-138">Here's a short link you can use to come back: [https://aka.ms/o365networkconnectivity.](https://aka.ms/o365networkconnectivity)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="abaf6-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="abaf6-139">See also</span></span>

[<span data-ttu-id="abaf6-140">Administración de extremos de Office 365</span><span class="sxs-lookup"><span data-stu-id="abaf6-140">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[<span data-ttu-id="abaf6-141">Preguntas más frecuentes de los extremos de Office 365</span><span class="sxs-lookup"><span data-stu-id="abaf6-141">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
  
[<span data-ttu-id="abaf6-142">Red de Office 365 y ajuste del rendimiento</span><span class="sxs-lookup"><span data-stu-id="abaf6-142">Office 365 network and performance tuning</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="abaf6-143">Azure ExpressRoute para Office 365</span><span class="sxs-lookup"><span data-stu-id="abaf6-143">Azure ExpressRoute for Office 365</span></span>](azure-expressroute.md)
  
[<span data-ttu-id="abaf6-144">Enrutamiento con ExpressRoute para Office 365</span><span class="sxs-lookup"><span data-stu-id="abaf6-144">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)
  
[<span data-ttu-id="abaf6-145">Planeamiento de red con ExpressRoute para Office 365</span><span class="sxs-lookup"><span data-stu-id="abaf6-145">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)
  
[<span data-ttu-id="abaf6-146">Uso de las Comunidades BGP en ExpressRoute para escenarios de Office 365 (vista previa)</span><span class="sxs-lookup"><span data-stu-id="abaf6-146">Using BGP communities in ExpressRoute for Office 365 scenarios (preview)</span></span>](bgp-communities-in-expressroute.md)
  
[<span data-ttu-id="abaf6-147">Calidad de medios y el rendimiento de conectividad de red en Skype para la empresa en línea</span><span class="sxs-lookup"><span data-stu-id="abaf6-147">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[<span data-ttu-id="abaf6-148">Direcciones URL e intervalos de direcciones IP de Office 365</span><span class="sxs-lookup"><span data-stu-id="abaf6-148">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[<span data-ttu-id="abaf6-149">Principios de conectividad de red de Office 365</span><span class="sxs-lookup"><span data-stu-id="abaf6-149">Office 365 Network Connectivity Principles</span></span>](https://aka.ms/o365networkingprinciples)