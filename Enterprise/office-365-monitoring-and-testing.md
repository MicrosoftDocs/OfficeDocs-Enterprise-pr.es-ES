---
title: Office 365 supervisión y pruebas de los límites de inquilino
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
description: 'Resumen: una explicación de cómo Microsoft supervisa y comprueba los límites de inquilino para Office 365.'
ms.openlocfilehash: f8ba20bd75d9cefa1457191373515f3ca68a2948
ms.sourcegitcommit: 55a046bdf49bf7c62ab74da73be1fd1cf6f0ad86
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37067791"
---
# <a name="monitoring-and-testing-tenant-boundaries"></a><span data-ttu-id="d6c64-103">Supervisar y probar los límites de inquilinos</span><span class="sxs-lookup"><span data-stu-id="d6c64-103">Monitoring and Testing Tenant Boundaries</span></span>
<span data-ttu-id="d6c64-104">Microsoft supervisa y comprueba explícitamente los puntos débiles y las vulnerabilidades en los límites de los inquilinos, incluida la supervisión de intrusiones, intentos de infracción de permisos y inanición de recursos.</span><span class="sxs-lookup"><span data-stu-id="d6c64-104">Microsoft continuously monitors and explicitly tests for weaknesses and vulnerabilities in tenant boundaries, including monitoring for intrusion, permission violation attempts, and resource starvation.</span></span> <span data-ttu-id="d6c64-105">También usamos varios sistemas internos para supervisar continuamente la utilización de recursos inadecuados, que, si se detectan, desencadena una limitación integrada.</span><span class="sxs-lookup"><span data-stu-id="d6c64-105">We also use multiple internal systems to continuously monitor for inappropriate resource utilization, which if detected, triggers built-in throttling.</span></span>

<span data-ttu-id="d6c64-106">Office 365 tiene sistemas de supervisión internos que supervisan continuamente los errores y la recuperación automática cuando se detecta un error.</span><span class="sxs-lookup"><span data-stu-id="d6c64-106">Office 365 has internal monitoring systems that continuously monitor for any failure and drive automated recovery when failure is detected.</span></span> <span data-ttu-id="d6c64-107">Office 365 sistemas analizan las desviaciones en el comportamiento del servicio e inician procesos de recuperación automática integrados en el sistema.</span><span class="sxs-lookup"><span data-stu-id="d6c64-107">Office 365 systems analyze deviations in service behavior and initiate self-healing processes that are built into the system.</span></span> <span data-ttu-id="d6c64-108">Office 365 también usa una supervisión externa en la que la supervisión se realiza desde varias ubicaciones, desde servicios de terceros de confianza (para la comprobación de SLA independiente) y nuestros propios centros de recursos para generar alertas.</span><span class="sxs-lookup"><span data-stu-id="d6c64-108">Office 365 also uses outside-in monitoring in which monitoring is performed from multiple locations both from trusted third-party services (for independent SLA verification) and our own datacenters to raise alerts.</span></span> <span data-ttu-id="d6c64-109">Para los diagnósticos, tenemos un registro, una auditoría y un seguimiento extensivos.</span><span class="sxs-lookup"><span data-stu-id="d6c64-109">For diagnostics, we have extensive logging, auditing, and tracing.</span></span> <span data-ttu-id="d6c64-110">El seguimiento y la supervisión granular nos ayudan a aislar los problemas y realizar un análisis rápido y eficaz de la causa de origen.</span><span class="sxs-lookup"><span data-stu-id="d6c64-110">Granular tracing and monitoring helps us isolate issues and perform fast and effective root cause analysis.</span></span>

<span data-ttu-id="d6c64-111">Aunque Office 365 tiene acciones de recuperación automatizadas siempre que sea posible, los ingenieros de llamadas de Microsoft están disponibles 24 horas al día, para investigar todas las escalaciones de seguridad de gravedad 1, y las revisiones post mortem de cada incidente de servicio contribuye a un aprendizaje continuo y desarrollo.</span><span class="sxs-lookup"><span data-stu-id="d6c64-111">While Office 365 has automated recovery actions where possible, Microsoft on-call engineers are available 24x7 to investigate all Severity 1 security escalations, and post-mortem reviews of every service incident contributes to continuous learning and improvement.</span></span> <span data-ttu-id="d6c64-112">Este equipo incluye ingenieros de soporte técnico, desarrolladores de productos, administradores de programas, jefes de producto y liderazgo Senior.</span><span class="sxs-lookup"><span data-stu-id="d6c64-112">This team includes support engineers, product developers, program managers, product managers, and senior leadership.</span></span> <span data-ttu-id="d6c64-113">Nuestros profesionales de la llamada proporcionan una copia de seguridad oportuna y a menudo pueden automatizar las acciones de recuperación, de modo que la próxima vez que se produzca un evento, se puede solucionar por sí misma.</span><span class="sxs-lookup"><span data-stu-id="d6c64-113">Our on-call professionals provide timely backup and often can automate recovery actions, so that next time an event occurs, it can be self-healed.</span></span>

<span data-ttu-id="d6c64-114">Microsoft realiza una revisión exhaustiva posterior al incidente cada vez que se produce un incidente de seguridad de Office 365 independientemente de la magnitud del impacto.</span><span class="sxs-lookup"><span data-stu-id="d6c64-114">Microsoft performs a thorough post-incident review each time an Office 365 security incident occurs regardless of the magnitude of impact.</span></span> <span data-ttu-id="d6c64-115">Una revisión posterior al incidente consiste en un análisis de lo ocurrido, cómo respondemos y cómo evitaría incidentes similares en el futuro.</span><span class="sxs-lookup"><span data-stu-id="d6c64-115">A post-incident review consists of an analysis of what happened, how we responded and how we prevent similar incidents in the future.</span></span> <span data-ttu-id="d6c64-116">En aras de la transparencia y la responsabilidad, compartimos la revisión posterior al incidente por cualquier incidente importante del servicio con los clientes afectados.</span><span class="sxs-lookup"><span data-stu-id="d6c64-116">In the interest of transparency and accountability, we share post-incident review for any major service incidents with affected customers.</span></span> <span data-ttu-id="d6c64-117">Para obtener detalles específicos, consulte [Office 365 Security Incident Management](http://aka.ms/Office365SIM).</span><span class="sxs-lookup"><span data-stu-id="d6c64-117">For specific details, see [Office 365 Security Incident Management](http://aka.ms/Office365SIM).</span></span>

## <a name="assume-breach-methodology"></a><span data-ttu-id="d6c64-118">Asumir una metodología de infracciones</span><span class="sxs-lookup"><span data-stu-id="d6c64-118">Assume Breach Methodology</span></span>
<span data-ttu-id="d6c64-119">Basándose en análisis detallados de tendencias de seguridad, Microsoft defiende y destaca la necesidad de inversiones adicionales en procesos y tecnologías de seguridad reactivos que se centran en la detección y la respuesta a amenazas emergentes, en lugar de en la única prevención de esas amenazas.</span><span class="sxs-lookup"><span data-stu-id="d6c64-119">Based on detailed analysis of security trends, Microsoft advocates and highlights the need for additional investments in reactive security processes and technologies that focus on detection and response to emerging threats, rather than solely the prevention of those threats.</span></span> <span data-ttu-id="d6c64-120">Debido a los cambios en el panorama de las amenazas y el análisis exhaustivo, Microsoft ha refinado su estrategia de seguridad más allá de sólo evitar infracciones de seguridad a un mejor equipado para enfrentarse a las brechas en caso de que se produzcan (una estrategia que considere eventos de seguridad principales) que no como una cuestión de IF, pero cuando.</span><span class="sxs-lookup"><span data-stu-id="d6c64-120">Because of changes in the threat landscape and in-depth analysis, Microsoft refined its security strategy beyond just preventing security breaches to one better equipped to deal with breaches when they do occur – a strategy which considers major security events not as a matter of if, but when.</span></span>

<span data-ttu-id="d6c64-121">Mientras que Microsoft [asume](https://www.microsoft.com/en-us/TrustCenter/Security/default.aspx) que se han implementado prácticas de violación durante muchos años, muchos clientes no conocen el trabajo que se realiza en segundo plano para reforzar la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6c64-121">While Microsoft's [Assume Breach](https://www.microsoft.com/en-us/TrustCenter/Security/default.aspx) practices have been in place for many years, many customers are unaware of the work being done behind the scenes to harden the Microsoft cloud.</span></span> <span data-ttu-id="d6c64-122">Asuma un incumplimiento es una mentalidad que guía las inversiones en seguridad, las decisiones de diseño y las prácticas de seguridad operacional.</span><span class="sxs-lookup"><span data-stu-id="d6c64-122">Assume Breach is a mindset that guides security investments, design decisions and operational security practices.</span></span> <span data-ttu-id="d6c64-123">Supongamos que la infracción de seguridad se aplica a las aplicaciones, servicios, identidades y redes al tratarlas todos (internos y externos) como no seguras y ya en peligro.</span><span class="sxs-lookup"><span data-stu-id="d6c64-123">Assume Breach limits the trust placed in applications, services, identities, and networks by treating them all—internal and external—as insecure and already compromised.</span></span> <span data-ttu-id="d6c64-124">Aunque la estrategia de infracciones no proviene de una infracción real de cualquier servicio de Microsoft Enterprise o de la nube, fue un reconocimiento que muchas organizaciones, en la industria, se violaban a pesar de todos los intentos de evitarlo.</span><span class="sxs-lookup"><span data-stu-id="d6c64-124">Although the Assume Breach strategy was not borne from an actual breach of any Microsoft enterprise or cloud services, it was a recognition that many organizations, across the industry, were being breached despite all attempts to prevent it.</span></span> <span data-ttu-id="d6c64-125">Aunque la prevención de las infracciones es una parte fundamental de las operaciones de la organización, estas prácticas deben probarse y aumentarse continuamente para enfrentarse de manera eficaz a las amenazas modernas adversarios y avanzadas.</span><span class="sxs-lookup"><span data-stu-id="d6c64-125">While preventing breaches is a critical part of any organization’s operations, those practices must be continuously tested and augmented to effectively address modern adversaries and advanced persistent threats.</span></span> <span data-ttu-id="d6c64-126">Para que cualquier organización pueda prepararse para una infracción, primero debe crear y mantener procedimientos de respuesta de seguridad sólidos, repetibles y probados minuciosamente.</span><span class="sxs-lookup"><span data-stu-id="d6c64-126">For any organization to prepare for a breach, they must first build and maintain robust, repeatable, and thoroughly-tested security response procedures.</span></span>

<span data-ttu-id="d6c64-127">Aunque evitar los procesos de seguridad de incumplimiento, como la modelación de amenazas, las revisiones de código y las pruebas de seguridad son muy útiles como parte del [ciclo de vida de desarrollo de seguridad](http://www.microsoft.com/security/sdl/default.aspx), suponer un incumplimiento ofrece numerosas ventajas que ayudan a la seguridad general por ejercitar y medir las capacidades reactivas en caso de infracción.</span><span class="sxs-lookup"><span data-stu-id="d6c64-127">While Prevent Breach security processes, such as threat modeling, code reviews, and security testing are very useful as part of the [Security Development Lifecycle](http://www.microsoft.com/security/sdl/default.aspx), Assume Breach provides numerous advantages that help account for overall security by exercising and measuring reactive capabilities in the event of a breach.</span></span>

<span data-ttu-id="d6c64-128">En Microsoft, nos hemos pensado en lograrlo a través de ejercicios de guerra en curso y pruebas de penetración en el sitio en directo de nuestros planes de respuesta de seguridad con el objetivo de mejorar nuestra capacidad de detección y respuesta.</span><span class="sxs-lookup"><span data-stu-id="d6c64-128">At Microsoft, we set out to accomplish this through ongoing war-games exercises and live site penetration testing of our security response plans with the goal of improving our detection and response capability.</span></span> <span data-ttu-id="d6c64-129">Microsoft simula periódicamente las infracciones en el mundo real, dirige la supervisión de seguridad continua y practica la administración de incidentes de seguridad para validar y mejorar la seguridad de Office 365, Azure y otros servicios en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6c64-129">Microsoft regularly simulates real-world breaches, conducts continuous security monitoring, and practices security incident management to validate and improve the security of Office 365, Azure, and other Microsoft cloud services.</span></span>

<span data-ttu-id="d6c64-130">Microsoft ejecuta su estrategia de seguridad de infracciones con dos grupos principales:</span><span class="sxs-lookup"><span data-stu-id="d6c64-130">Microsoft executes its Assume Breach security strategy using two core groups:</span></span>
- <span data-ttu-id="d6c64-131">Equipos de color rojo (atacantes)</span><span class="sxs-lookup"><span data-stu-id="d6c64-131">Red Teams (attackers)</span></span>
- <span data-ttu-id="d6c64-132">Equipos azules (defensores)</span><span class="sxs-lookup"><span data-stu-id="d6c64-132">Blue Teams (defenders)</span></span>

<span data-ttu-id="d6c64-133">El personal de Microsoft Azure y Office 365 es equipo de equipos rojos y azules independientes a tiempo completo.</span><span class="sxs-lookup"><span data-stu-id="d6c64-133">Both Microsoft Azure and Office 365 staff separate full-time red teams and blue teams.</span></span>

<span data-ttu-id="d6c64-134">Conocido como "[equipo rojo](http://go.microsoft.com/fwlink/?linkid=518599)", el enfoque consiste en probar sistemas y operaciones de Azure y Office 365 con las mismas tácticas, técnicas y procedimientos que los adversarios reales, con la infraestructura de producción activa, sin el foreknowledge del Equipos de ingeniería u operaciones.</span><span class="sxs-lookup"><span data-stu-id="d6c64-134">Referred to as "[Red Teaming](http://go.microsoft.com/fwlink/?linkid=518599)", the approach is to test Azure and Office 365 systems and operations using the same tactics, techniques and procedures as real adversaries, against the live production infrastructure, without the foreknowledge of the Engineering or Operations teams.</span></span> <span data-ttu-id="d6c64-135">Esto prueba las capacidades de detección y respuesta de seguridad de Microsoft y ayuda a identificar las vulnerabilidades de producción, los errores de configuración, los supuestos no válidos y otros problemas de seguridad de manera controlada.</span><span class="sxs-lookup"><span data-stu-id="d6c64-135">This tests Microsoft’s security detection and response capabilities, and helps identify production vulnerabilities, configuration errors, invalid assumptions, and other security issues in a controlled manner.</span></span> <span data-ttu-id="d6c64-136">Cada infracción de equipo en rojo va seguida de una divulgación completa entre los dos equipos para identificar brechas, conclusiones de la dirección y mejora de la respuesta a las infracciones.</span><span class="sxs-lookup"><span data-stu-id="d6c64-136">Every red team breach is followed by full disclosure between both teams to identify gaps, address findings, and improve breach response.</span></span>

<span data-ttu-id="d6c64-137">**Nota**: los datos de los clientes no se destinan deliberadamente durante la formación de equipos rojos o las pruebas de penetración en sitios activos.</span><span class="sxs-lookup"><span data-stu-id="d6c64-137">**NOTE**: No customer data is deliberately targeted during Red Teaming or live site penetration testing.</span></span> <span data-ttu-id="d6c64-138">Las pruebas están relacionadas con las plataformas y la infraestructura de Office 365 y Azure, así como con los propios espacios empresariales, aplicaciones y datos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6c64-138">The tests are against Office 365 and Azure infrastructure and platforms, as well as Microsoft's own tenants, applications, and data.</span></span> <span data-ttu-id="d6c64-139">Los inquilinos de cliente, las aplicaciones y el contenido hospedados en Office 365 o Azure nunca se dirigen.</span><span class="sxs-lookup"><span data-stu-id="d6c64-139">Customer tenants, applications, and content hosted in Office 365 or Azure are never targeted.</span></span>

## <a name="red-teams"></a><span data-ttu-id="d6c64-140">Equipos rojos</span><span class="sxs-lookup"><span data-stu-id="d6c64-140">Red Teams</span></span>
<span data-ttu-id="d6c64-141">El equipo de color rojo es un grupo de personal a tiempo completo dentro de Microsoft que se centra en la infracción de la infraestructura, la plataforma y las aplicaciones y los espacios empresariales de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6c64-141">The red team is a group of full-time staff within Microsoft that focuses on breaching Microsoft's infrastructure, platform and Microsoft's own tenants and applications.</span></span> <span data-ttu-id="d6c64-142">Son los adversarios dedicados (un grupo de hackers éticos) que realizan ataques perseguidos y persistentes contra los servicios en línea (infraestructura de Microsoft, plataformas y aplicaciones, pero no a las aplicaciones ni al contenido de los clientes finales).</span><span class="sxs-lookup"><span data-stu-id="d6c64-142">They are the dedicated adversary (a group of ethical hackers) performing targeted and persistent attacks against Online Services (Microsoft infrastructure, platforms, and applications but not end-customers' applications or content).</span></span>

<span data-ttu-id="d6c64-143">El rol del equipo en rojo es atacar y penetrar en entornos con los mismos pasos que un adversario:</span><span class="sxs-lookup"><span data-stu-id="d6c64-143">The role of the red team is to attack and penetrate environments using the same steps as an adversary:</span></span>
 
![Fases de infracción](media/office-365-isolation-breach-stages.png)

<span data-ttu-id="d6c64-145">Entre otras funciones, los equipos rojos intentan específicamente infringir los límites de aislamiento de inquilino para encontrar errores o brechas en nuestro diseño de aislamiento.</span><span class="sxs-lookup"><span data-stu-id="d6c64-145">Among other functions, red teams specifically attempt to breach tenant isolation boundaries to find bugs or gaps in our isolation design.</span></span>

## <a name="blue-teams"></a><span data-ttu-id="d6c64-146">Equipos azules</span><span class="sxs-lookup"><span data-stu-id="d6c64-146">Blue Teams</span></span>
<span data-ttu-id="d6c64-147">El equipo azul se compone de un conjunto dedicado de respondedores o miembros de seguridad a través de las organizaciones de respuesta, ingeniería y operaciones de incidentes de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d6c64-147">The blue team is comprised of either a dedicated set of security responders or members from across the security incident response, Engineering, and Operations organizations.</span></span> <span data-ttu-id="d6c64-148">Independientemente de su forma de componerla, son independientes y operan por separado del equipo de red.</span><span class="sxs-lookup"><span data-stu-id="d6c64-148">Regardless of their make-up, they are independent and operate separately from the red team.</span></span> <span data-ttu-id="d6c64-149">El equipo azul sigue los procesos de seguridad establecidos y usa las últimas herramientas y tecnologías para detectar y responder a los ataques y la penetración.</span><span class="sxs-lookup"><span data-stu-id="d6c64-149">The blue team follows established security processes and uses the latest tools and technologies to detect and respond to attacks and penetration.</span></span> <span data-ttu-id="d6c64-150">Al igual que con los ataques del mundo real, el equipo azul no sabe cuándo o cómo se producirán los ataques del equipo rojo o qué métodos pueden usarse.</span><span class="sxs-lookup"><span data-stu-id="d6c64-150">Just like real-world attacks, the blue team does not know when or how the red team's attacks will occur or what methods may be used.</span></span> <span data-ttu-id="d6c64-151">Su trabajo, ya sea un ataque de equipo en rojo o un asalto real, es detectar y responder a todos los incidentes de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d6c64-151">Their job, whether it is a red team attack or an actual assault, is to detect and respond to all security incidents.</span></span> <span data-ttu-id="d6c64-152">Por este motivo, el equipo azul está continuamente activado y debe reaccionar a las infracciones de equipo en rojo de la misma manera que lo harían para cualquier otra infracción.</span><span class="sxs-lookup"><span data-stu-id="d6c64-152">For this reason, the blue team is continuously on-call and must react to red team breaches the same way they would for any other breach.</span></span>

<span data-ttu-id="d6c64-153">Cuando un adversario, como un equipo de color rojo, ha infringido un entorno, el equipo azul debe:</span><span class="sxs-lookup"><span data-stu-id="d6c64-153">When an adversary, such as a red team, has breached an environment, the blue team must:</span></span>
- <span data-ttu-id="d6c64-154">Recopilar evidencia dejada por el adversario</span><span class="sxs-lookup"><span data-stu-id="d6c64-154">Gather evidence left by the adversary</span></span>
- <span data-ttu-id="d6c64-155">Detectar la evidencia como una indicación de peligro</span><span class="sxs-lookup"><span data-stu-id="d6c64-155">Detect the evidence as an indication of compromise</span></span>
- <span data-ttu-id="d6c64-156">Alertar a los equipos de ingeniería y de funcionamiento apropiados</span><span class="sxs-lookup"><span data-stu-id="d6c64-156">Alert the appropriate Engineering and Operation team(s)</span></span>
- <span data-ttu-id="d6c64-157">Clasifique las alertas para determinar si justifican una mayor investigación</span><span class="sxs-lookup"><span data-stu-id="d6c64-157">Triage the alerts to determine whether they warrant further investigation</span></span>
- <span data-ttu-id="d6c64-158">Recopilar el contexto del entorno para el ámbito de la infracción</span><span class="sxs-lookup"><span data-stu-id="d6c64-158">Gather context from the environment to scope the breach</span></span>
- <span data-ttu-id="d6c64-159">Formar un plan de corrección para contener o expulsar el adversario</span><span class="sxs-lookup"><span data-stu-id="d6c64-159">Form a remediation plan to contain or evict the adversary</span></span>
- <span data-ttu-id="d6c64-160">Ejecutar el plan de corrección y recuperarse de una infracción</span><span class="sxs-lookup"><span data-stu-id="d6c64-160">Execute the remediation plan and recover from breach</span></span>

<span data-ttu-id="d6c64-161">Estos pasos conforman la respuesta al incidente de seguridad que se ejecuta en paralelo con el del adversario, tal como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="d6c64-161">These steps form the security incident response that runs parallel to the adversary's, as shown below:</span></span>
 
![Fases de respuesta a las infracciones](media/office-365-isolation-breach-response-stages.png)

<span data-ttu-id="d6c64-163">Las infracciones de equipo en rojo permiten ejercitar la capacidad del equipo azul para detectar y responder a ataques en el mundo real de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="d6c64-163">Red team breaches allow for exercising the blue team's ability to detect and respond to real-world attacks end-to-end.</span></span> <span data-ttu-id="d6c64-164">Lo más importante es que permite la respuesta al incidente de seguridad antes de una infracción del auténtico.</span><span class="sxs-lookup"><span data-stu-id="d6c64-164">Most importantly, it allows for practiced security incident response prior to a genuine breach.</span></span> <span data-ttu-id="d6c64-165">Además, debido a las infracciones de equipo en rojo, el equipo azul mejora su conciencia de situación que puede ser valiosa al tratar con infracciones futuras (ya sea del equipo de color rojo o de otro adversario).</span><span class="sxs-lookup"><span data-stu-id="d6c64-165">Additionally, because of red team breaches, the blue team enhances their situational awareness which can be valuable when dealing with future breaches (whether from the red team or another adversary).</span></span> <span data-ttu-id="d6c64-166">Durante el proceso de detección y respuesta, el equipo azul produce una inteligencia que requiere acción y obtiene visibilidad de las condiciones reales del entorno o los entornos que intentan defender.</span><span class="sxs-lookup"><span data-stu-id="d6c64-166">Throughout the detection and response process, the blue team produces actionable intelligence and gains visibility into the actual conditions of the environment(s) they are trying to defend.</span></span> <span data-ttu-id="d6c64-167">Con frecuencia, esto se logra a través del análisis de datos y de la investigación, realizado por el equipo azul, cuando responde a los ataques de equipo rojos y estableciendo indicadores de amenazas, como indicadores de peligro.</span><span class="sxs-lookup"><span data-stu-id="d6c64-167">Frequently this is accomplished via data analysis and forensics, performed by the blue team, when responding to red team attacks and by establishing threat indicators, such as indicators of compromise.</span></span> <span data-ttu-id="d6c64-168">De forma similar a cómo el equipo rojo identifica brechas en el caso de seguridad, los equipos azules identifican brechas en su capacidad para detectar y responder.</span><span class="sxs-lookup"><span data-stu-id="d6c64-168">Much like how the red team identifies gaps in the security story, blue teams identify gaps in their ability to detect and respond.</span></span> <span data-ttu-id="d6c64-169">Además, dado que los equipos de color rojo modelan los ataques en el mundo real, el equipo azul puede evaluarse con precisión por su capacidad o incapacidad para tratar con los adversarios determinados y persistentes.</span><span class="sxs-lookup"><span data-stu-id="d6c64-169">Furthermore, since the red teams model real-world attacks, the blue team can be accurately assessed on their ability, or inability, to deal with determined and persistent adversaries.</span></span> <span data-ttu-id="d6c64-170">Por último, las infracciones de equipo en rojo miden tanto la preparación como el impacto de nuestra respuesta a la infracción.</span><span class="sxs-lookup"><span data-stu-id="d6c64-170">Finally, red team breaches measure both readiness and impact of our breach response.</span></span>