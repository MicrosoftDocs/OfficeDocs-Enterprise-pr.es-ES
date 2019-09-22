---
title: Office 365 principales principios de defensa contra ataques por denegación de servicio
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
description: Modo en que Microsoft usa los principios principales de absorción, detección y mitigación en su defensa contra ataques por denegación de servicio (DoS).
ms.openlocfilehash: abfb0efda679930c22d9ce87709aded9a2880f06
ms.sourcegitcommit: 55a046bdf49bf7c62ab74da73be1fd1cf6f0ad86
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37067848"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="5d988-103">Principios básicos de la defensa contra ataques por denegación de servicio</span><span class="sxs-lookup"><span data-stu-id="5d988-103">Core Principles of Defense Against Denial-of-Service Attacks</span></span>

<span data-ttu-id="5d988-104">Los tres principios básicos para defenderse contra los ataques DoS basados en la red son la absorción, la detección y la mitigación.</span><span class="sxs-lookup"><span data-stu-id="5d988-104">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation.</span></span> <span data-ttu-id="5d988-105">La absorción se produce antes de la detección y la detección se produce antes de la mitigación.</span><span class="sxs-lookup"><span data-stu-id="5d988-105">Absorption happens before detection, and detection happens before mitigation.</span></span> <span data-ttu-id="5d988-106">La absorción es la mejor protección contra un ataque DoS.</span><span class="sxs-lookup"><span data-stu-id="5d988-106">Absorption is the best defense against a DoS attack.</span></span> <span data-ttu-id="5d988-107">Si el ataque no se puede detectar, no se puede mitigar.</span><span class="sxs-lookup"><span data-stu-id="5d988-107">If the attack can't be detected, it can't be mitigated.</span></span> <span data-ttu-id="5d988-108">Pero, incluso si no se puede absorber el ataque a DoS más pequeño, los servicios no se mantendrán durante el tiempo suficiente para que se detecte el ataque.</span><span class="sxs-lookup"><span data-stu-id="5d988-108">But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="5d988-109">La mayoría de las organizaciones no son viables económicamente para adquirir la capacidad excesiva para absorber ataques de DoS, ya que esto requiere una gran inversión en la tecnología y las habilidades técnicas.</span><span class="sxs-lookup"><span data-stu-id="5d988-109">It is not economically feasible for most organizations to purchase excess capacity to absorb DoS attacks, as this requires a considerable investment in technology and technical skills.</span></span> <span data-ttu-id="5d988-110">Esto destaca una de las ventajas de seguridad de usar los servicios en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5d988-110">This highlights one of the security benefits of using Microsoft cloud services.</span></span> <span data-ttu-id="5d988-111">La gran escala de los servicios de Microsoft proporciona una sólida protección de red a los clientes de la nube de una manera rentable.</span><span class="sxs-lookup"><span data-stu-id="5d988-111">The sheer scale of Microsoft services provides strong network protection to cloud customers in a cost-effective manner.</span></span> <span data-ttu-id="5d988-112">Pero incluso a gran escala, debe haber un equilibrio entre la absorción, la detección y la mitigación.</span><span class="sxs-lookup"><span data-stu-id="5d988-112">But even at a large scale, there must be a balance between absorption, detection, and mitigation.</span></span> <span data-ttu-id="5d988-113">Para encontrar ese saldo, Microsoft estudia las tasas de crecimiento de los ataques para calcular la cantidad que necesita absorber Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5d988-113">To find that balance, Microsoft studies attack growth rates to estimate how much Microsoft needs to absorb.</span></span>

<span data-ttu-id="5d988-114">La detección es un juego de gato y de mouse.</span><span class="sxs-lookup"><span data-stu-id="5d988-114">Detection is a cat-and-mouse game.</span></span> <span data-ttu-id="5d988-115">Debe buscar constantemente nuevas formas de que los usuarios sean atacados e intenten derrotar a sus sistemas.</span><span class="sxs-lookup"><span data-stu-id="5d988-115">You must constantly look for new ways people are attack and try to defeat your systems.</span></span> <span data-ttu-id="5d988-116">Detect-> mitigate-> detecte-> mitigate, etc., es un estado persistente permanente que sigue indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="5d988-116">Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that continues indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="5d988-117">Defensa contra ataques DoS</span><span class="sxs-lookup"><span data-stu-id="5d988-117">Defending Against DoS Attacks</span></span>

<span data-ttu-id="5d988-118">Para defenderse correctamente contra un ataque DoS, la detección temprana es esencial.</span><span class="sxs-lookup"><span data-stu-id="5d988-118">To successfully defend against a DoS attack, early detection is essential.</span></span> <span data-ttu-id="5d988-119">Al detectar un ataque antes de que el sistema esté saturado, los defensores pueden ejecutar un plan de respuesta.</span><span class="sxs-lookup"><span data-stu-id="5d988-119">By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="5d988-120">La siguiente fórmula ayuda a aproximar el tiempo de impacto de un ataque DoS:</span><span class="sxs-lookup"><span data-stu-id="5d988-120">The following formula helps approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="5d988-121">**Capacidad máxima (en bytes/s)/velocidad de crecimiento (en bytes/s) = tiempo de impacto (en bytes/s)**</span><span class="sxs-lookup"><span data-stu-id="5d988-121">**Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in bytes/sec)**</span></span>

<span data-ttu-id="5d988-122">Si el tiempo de detección se produce después del tiempo de impacto, es probable que el ataque de DoS se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="5d988-122">If the time-to-detection occurs after time-to-impact, it is likely the DoS attack will be successful.</span></span> <span data-ttu-id="5d988-123">Si el tiempo de detección se produce antes del tiempo de impacto, los servicios atacados deben permanecer en línea y ser accesibles si se usan estrategias de mitigación.</span><span class="sxs-lookup"><span data-stu-id="5d988-123">If the time-to-detection occurs before time-to-impact, the attacked services should remain online and accessible if mitigation strategies are used.</span></span> <span data-ttu-id="5d988-124">Por lo tanto, solo se pueden hacer dos cosas para defenderse contra ataques DoS:</span><span class="sxs-lookup"><span data-stu-id="5d988-124">Thus, there are only two things that can be done to defend against DoS attacks:</span></span>

- <span data-ttu-id="5d988-125">Aumente la capacidad para aumentar el límite máximo de capacidad (lo que, a su vez, proporciona más tiempo para detectar un ataque); o</span><span class="sxs-lookup"><span data-stu-id="5d988-125">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="5d988-126">Reducir el tiempo de detección.</span><span class="sxs-lookup"><span data-stu-id="5d988-126">Decrease the time to detect.</span></span>

<span data-ttu-id="5d988-127">El aumento de la capacidad tiene un impacto fiscal directo.</span><span class="sxs-lookup"><span data-stu-id="5d988-127">Increasing capacity has a direct fiscal impact.</span></span> <span data-ttu-id="5d988-128">Microsoft recomienda que los clientes desarrollen una capacidad de absorción básica mínima para garantizar que pueden sobrevivir a algún ataque de DoS niveles.</span><span class="sxs-lookup"><span data-stu-id="5d988-128">Microsoft recommends that customers develop at least basic absorption capacity to ensure that they can survive some level of DoS attack.</span></span> <span data-ttu-id="5d988-129">La capacidad de absorción real varía de un cliente a un cliente, ya que cada cliente tiene sus propios umbrales para la exposición, el riesgo y la inversión financiera.</span><span class="sxs-lookup"><span data-stu-id="5d988-129">The actual absorption capacity varies from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay.</span></span> <span data-ttu-id="5d988-130">Por motivos económicos, las inversiones en investigación y tiempo para reducir el tiempo de detección suelen ser la defensa más rentable.</span><span class="sxs-lookup"><span data-stu-id="5d988-130">For economic reasons, investments in research and time for ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>