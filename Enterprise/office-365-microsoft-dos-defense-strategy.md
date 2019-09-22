---
title: Estrategia de defensa DoS de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Información general sobre la estrategia de defensa de Microsoft para ataques por denegación de servicio (DoS).
ms.openlocfilehash: eacfd9d908eb8408d592fc70cd1a888c7c44aff2
ms.sourcegitcommit: 55a046bdf49bf7c62ab74da73be1fd1cf6f0ad86
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37067803"
---
# <a name="office-365-denial-of-service-defense-strategy"></a><span data-ttu-id="260ac-103">Estrategia de defensa de denegación de servicio de Office 365</span><span class="sxs-lookup"><span data-stu-id="260ac-103">Office 365 Denial-of-Service Defense Strategy</span></span>

<span data-ttu-id="260ac-104">La estrategia de Microsoft para defenderse contra los ataques de denegación de servicio (DoS) basados en red es única debido a nuestra escala y a la superficie global.</span><span class="sxs-lookup"><span data-stu-id="260ac-104">Microsoft's strategy to defend against network-based denial-of-service (DoS) attacks is unique due to our scale and global footprint.</span></span> <span data-ttu-id="260ac-105">Esta escala permite a Microsoft usar estrategias y técnicas para que puedan coincidir algunas organizaciones, proveedores o organizaciones de clientes.</span><span class="sxs-lookup"><span data-stu-id="260ac-105">This scale allows Microsoft to utilize strategies and techniques few organizations, providers, or customer organizations can match.</span></span> <span data-ttu-id="260ac-106">La piedra angular de la estrategia DoS es nuestra presencia global.</span><span class="sxs-lookup"><span data-stu-id="260ac-106">The cornerstone of the DoS strategy is our global presence.</span></span> <span data-ttu-id="260ac-107">Microsoft se compromete con los proveedores de Internet, los proveedores de emparejamiento (públicos y privados) y las corporaciones privadas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="260ac-107">Microsoft engages with Internet providers, peering providers (public and private), and private corporations all over the world.</span></span> <span data-ttu-id="260ac-108">Esto proporciona a Microsoft una presencia importante en Internet y permite a Microsoft absorber ataques en un área de gran superficie.</span><span class="sxs-lookup"><span data-stu-id="260ac-108">This gives Microsoft a significant Internet presence and enables Microsoft to absorb attacks across a large surface area.</span></span>

<span data-ttu-id="260ac-109">Teniendo en cuentan esta naturaleza única, Microsoft usa procesos de detección y mitigación que difieren de los usados por grandes empresas.</span><span class="sxs-lookup"><span data-stu-id="260ac-109">Given this unique nature, Microsoft uses detection and mitigation processes that differ from ones used by large enterprises.</span></span> <span data-ttu-id="260ac-110">La estrategia se basa en una separación de detección y mitigación global distribuida a través de muchos perímetros de red.</span><span class="sxs-lookup"><span data-stu-id="260ac-110">The strategy is based on a separation of detection and global distributed mitigation through many network edges.</span></span> <span data-ttu-id="260ac-111">Muchas empresas usan soluciones de terceros para detectar y mitigar los ataques en el perímetro.</span><span class="sxs-lookup"><span data-stu-id="260ac-111">Many enterprises use third-party solutions to detect and mitigate attacks at the edge.</span></span> <span data-ttu-id="260ac-112">A medida que aumentaba la capacidad de la periferia de Microsoft, se denominó la importancia de cualquier ataque contra contornos individuales o específicos.</span><span class="sxs-lookup"><span data-stu-id="260ac-112">As the edge capacity for Microsoft grew, it became clear the significance of any attack against individual or particular edges was low.</span></span> <span data-ttu-id="260ac-113">Debido a esta configuración única, Microsoft separó los componentes de detección y mitigación.</span><span class="sxs-lookup"><span data-stu-id="260ac-113">Because of this unique configuration, Microsoft separated the detection and mitigation components.</span></span> <span data-ttu-id="260ac-114">Microsoft implementa sistemas de detección de varios niveles para detectar ataques más cercanos a sus puntos de saturación, a la vez que mantiene una mitigación global en el perímetro.</span><span class="sxs-lookup"><span data-stu-id="260ac-114">Microsoft deploys multi-tiered detection systems to detect attacks closer to their saturation points while maintaining global mitigation at the edge.</span></span> <span data-ttu-id="260ac-115">Esta estrategia garantiza que se puedan controlar varios ataques simultáneos.</span><span class="sxs-lookup"><span data-stu-id="260ac-115">This strategy ensures we can handle multiple simultaneous attacks.</span></span>

<span data-ttu-id="260ac-116">Una de las defensas más eficaces y de bajo costo utilizadas por Microsoft contra ataques DoS es reducir las superficies de ataque al servicio.</span><span class="sxs-lookup"><span data-stu-id="260ac-116">One of the most effective and low-cost defenses employed by Microsoft against DoS attacks is reducing service attack surfaces.</span></span> <span data-ttu-id="260ac-117">El tráfico no deseado se descarta en el perímetro de la red en lugar de analizar, procesar y limpiar los datos en línea.</span><span class="sxs-lookup"><span data-stu-id="260ac-117">Unwanted traffic is dropped at the network edge instead of analyzing, processing, and scrubbing the data inline.</span></span>

<span data-ttu-id="260ac-118">En la interfaz con la red pública, Microsoft usa dispositivos de seguridad de propósito especial para el firewall, la traducción de direcciones de red y las funciones de filtrado IP.</span><span class="sxs-lookup"><span data-stu-id="260ac-118">At the interface with the public network, Microsoft uses special-purpose security devices for firewall, network address translation, and IP filtering functions.</span></span> <span data-ttu-id="260ac-119">Microsoft también usa el enrutamiento global de igualdad de costos (ECMP).</span><span class="sxs-lookup"><span data-stu-id="260ac-119">Microsoft also uses global equal-cost multi-path (ECMP) routing.</span></span> <span data-ttu-id="260ac-120">El enrutamiento de ECMP global es un marco de red para garantizar que hay varias rutas globales para llegar a un servicio.</span><span class="sxs-lookup"><span data-stu-id="260ac-120">Global ECMP routing is a network framework to ensure that there are multiple global paths to reach a service.</span></span> <span data-ttu-id="260ac-121">Con estas varias rutas, los ataques contra los servicios se limitan a la región desde la que se origina el ataque.</span><span class="sxs-lookup"><span data-stu-id="260ac-121">With these multiple paths, attacks against services are limited to the region from which the attack originates.</span></span> <span data-ttu-id="260ac-122">Otras regiones no deberían verse afectadas por este ataque, ya que los usuarios finales usarían otras rutas para llegar al servicio en esas regiones.</span><span class="sxs-lookup"><span data-stu-id="260ac-122">Other regions should be unaffected by this attack, as end users would use other paths to reach the service in those regions.</span></span> <span data-ttu-id="260ac-123">Microsoft también ha desarrollado sistemas de correlación y detección de DoS internos que usan datos de flujo, métricas de rendimiento y otra información.</span><span class="sxs-lookup"><span data-stu-id="260ac-123">Microsoft has also developed internal DoS correlation and detection systems that use flow data, performance metrics, and other information.</span></span> <span data-ttu-id="260ac-124">Se trata de un servicio en la nube de hiperescala en Microsoft Azure, que analiza los datos recopilados de varios puntos de los servicios y las redes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="260ac-124">This is a hyperscale cloud service in Microsoft Azure, which analyzes data collected from various points on Microsoft networks and services.</span></span> <span data-ttu-id="260ac-125">Un equipo de respuesta ante incidentes entre cargas de trabajo en DoS identifica los roles y las responsabilidades en Teams, los criterios de escalabilidad y los protocolos para la contratación de varios equipos y el tratamiento de incidentes.</span><span class="sxs-lookup"><span data-stu-id="260ac-125">A cross-workload DoS incident response team identifies the roles and responsibilities across teams, the criteria for escalations, and the protocols for engaging various teams and for incident handling.</span></span> <span data-ttu-id="260ac-126">Estas soluciones proporcionan protección basada en red contra ataques DoS.</span><span class="sxs-lookup"><span data-stu-id="260ac-126">These solutions provide network-based protection against DoS attacks.</span></span>

<span data-ttu-id="260ac-127">Por último, las cargas de trabajo basadas en la nube se configuran con umbrales optimizados basados en su Protocolo y el uso de ancho de banda debe proteger la carga de trabajo de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="260ac-127">Finally, cloud-based workloads are configured with optimized thresholds based on their protocol and bandwidth usage needs to uniquely protect that workload.</span></span>