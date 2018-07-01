---
title: Respuesta de incidente de seguridad de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/27/2018
ms.audience: ITPro
ms.topic: overview
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: o365-solutions
localization_priority: Normal
ms.custom: ''
ms.assetid: ''
description: Esta solución le indica qué los más comunes cyber-seguridad ataques podrían ser similar en Office 365 y cómo responder a ellos
ms.openlocfilehash: b9800070bde662603c731e2b8d64609b4f821cce
ms.sourcegitcommit: a4322cac992ce64b92f0335bf005a7420195d9be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="office-365-security-incident-response"></a><span data-ttu-id="feba5-103">Respuesta de incidente de seguridad de Office 365</span><span class="sxs-lookup"><span data-stu-id="feba5-103">Office 365 Security Incident Response</span></span>

 <span data-ttu-id="feba5-104">**Resumen:** Esta solución le indica cuáles son los indicadores para los ataques de seguridad informática más comunes en Office 365, cómo positiva confirmar cualquier ataque determinado y cómo responder a él.</span><span class="sxs-lookup"><span data-stu-id="feba5-104">**Summary:** This solution tells you what the indicators are for the most common cyber-security attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>
  
## <a name="overview"></a><span data-ttu-id="feba5-105">Información general</span><span class="sxs-lookup"><span data-stu-id="feba5-105">Overview</span></span>
<span data-ttu-id="feba5-p101">No todos los ataques de Internet quedan eliminados. Los atacantes buscan constantemente nuevos puntos débiles en la estrategia de defensa o aprovechamiento de los antiguos. Saber cómo reconocer un ataque permite responder más rápidamente a ella, lo que reduce la duración de la incidencia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="feba5-p101">Not all cyber attacks can be thwarted. Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones. Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="feba5-p102">En esta serie de artículo le ayuda a entender la apariencia que podría tener un determinado tipo de ataque en Office 365 y le proporciona los pasos que puede seguir para responder. Son puntos de entrada rápida a Descripción:</span><span class="sxs-lookup"><span data-stu-id="feba5-p102">This series of article helps you understand what a particular type of attack might look like in Office 365 and gives you steps you can take to respond. They are quick entry points to understanding:</span></span>
 
- <span data-ttu-id="feba5-111">El ataque de qué es y cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="feba5-111">What the attack is and how it works.</span></span>
- <span data-ttu-id="feba5-112">Los signos, denominados indicadores de compromiso (IOC), para buscar y cómo se van a buscar.</span><span class="sxs-lookup"><span data-stu-id="feba5-112">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>
- <span data-ttu-id="feba5-113">Procedimiento para confirmar el ataque de forma positiva.</span><span class="sxs-lookup"><span data-stu-id="feba5-113">How to positively confirm the attack.</span></span>
- <span data-ttu-id="feba5-114">Pasos que deben seguirse para cortar el ataque y mejor protección de la organización en el futuro.</span><span class="sxs-lookup"><span data-stu-id="feba5-114">Steps to take to cut off the attack and better protect your organization in the future.</span></span>
- <span data-ttu-id="feba5-115">Vínculos a información detallada acerca de cada uno de ellos para atacar tipo.</span><span class="sxs-lookup"><span data-stu-id="feba5-115">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="feba5-116">Vuelva a comprobar todos los meses tal y como se agregarán más artículos a través del tiempo.</span><span class="sxs-lookup"><span data-stu-id="feba5-116">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="feba5-117">Detectar y corregir los artículos</span><span class="sxs-lookup"><span data-stu-id="feba5-117">Detect and Remediate Articles</span></span>
- [<span data-ttu-id="feba5-118">Detectar y corregir concede a consentimiento ilegal en Office 365</span><span class="sxs-lookup"><span data-stu-id="feba5-118">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)
- [<span data-ttu-id="feba5-119">Detectar y corregir las reglas de Outlook y los ataques de inserciones de formularios personalizados en Office 365</span><span class="sxs-lookup"><span data-stu-id="feba5-119">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)
 
## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="feba5-120">Seguro de Office 365 como una ciberseguridad pro</span><span class="sxs-lookup"><span data-stu-id="feba5-120">Secure Office 365 like a cybersecurity pro</span></span>
<span data-ttu-id="feba5-p103">Su suscripción de Office 365 incluye un conjunto eficaz de características de seguridad que puede utilizar para proteger los datos y los usuarios.  Usar el [Guía de seguridad de Office 365: principales prioridades para los primeros 30 días, 90 días y más allá de](https://support.office.com/en-us/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) para implementar Microsoft procedimientos recomendado para proteger el inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="feba5-p103">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.  Use the [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](https://support.office.com/en-us/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>
- <span data-ttu-id="feba5-p104">Tareas de llevar a cabo en los primeros 30 días.  Estos tienen un efecto inmediato y están bajo impacto para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="feba5-p104">Tasks to accomplish in the first 30 days.  These have immediate affect and are low-impact to your users.</span></span>
- <span data-ttu-id="feba5-p105">Tareas de llevar a cabo en 90 días. Estos tardan un poco más en planear e implementar pero mejorar considerablemente el nivel de seguridad</span><span class="sxs-lookup"><span data-stu-id="feba5-p105">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture</span></span>
- <span data-ttu-id="feba5-p106">Más allá de 90 días. Estas mejoras se basan en su primer trabajo de 90 días.</span><span class="sxs-lookup"><span data-stu-id="feba5-p106">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>





