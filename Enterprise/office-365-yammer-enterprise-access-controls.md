---
title: Controles de acceso empresarial de Office 365 Yammer
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
description: 'Resumen: un breve resumen sobre los controles de acceso empresarial de Yammer en el entorno de producción.'
ms.openlocfilehash: 19910ec0771b3034e7a290190ae7045ffc8651cf
ms.sourcegitcommit: 55a046bdf49bf7c62ab74da73be1fd1cf6f0ad86
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37067827"
---
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="1728b-103">Controles de acceso de Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="1728b-103">Yammer Enterprise Access Controls</span></span> 

<span data-ttu-id="1728b-104">El acceso físico y lógico al entorno de producción de Yammer está restringido a un pequeño conjunto de personas (infraestructura y operaciones).</span><span class="sxs-lookup"><span data-stu-id="1728b-104">Physical and logical access to the Yammer production environment is restricted to a small set of people (infrastructure and operations).</span></span> <span data-ttu-id="1728b-105">Como con otros ingenieros de Office 365, los ingenieros de Yammer tienen un acceso sin igual a los datos de los clientes.</span><span class="sxs-lookup"><span data-stu-id="1728b-105">As with other Office 365 engineers, Yammer engineers have zero standing access to Customer Data.</span></span> <span data-ttu-id="1728b-106">El acceso debe solicitarse mediante un sistema de control de acceso Just-in-Time basado en aprobaciones similar a Lockbox con un número limitado de aprobadores.</span><span class="sxs-lookup"><span data-stu-id="1728b-106">Access must be requested using an approval-based just-in-time access control system similar to Lockbox with a limited number of approvers.</span></span> <span data-ttu-id="1728b-107">Los aprobadores comprueban la solicitud (por ejemplo, comprueban si la solicitud es legítima según la necesidad, el caso de negocio, la hora, etc.) y, a continuación, aprueba o deniega la solicitud.</span><span class="sxs-lookup"><span data-stu-id="1728b-107">Approvers verify the request (for example, they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request.</span></span> <span data-ttu-id="1728b-108">Si se aprueba la solicitud, se concede el acceso JIT durante un tiempo definido y limitado.</span><span class="sxs-lookup"><span data-stu-id="1728b-108">If the request is approved, JIT access is granted for a defined and limited time.</span></span> <span data-ttu-id="1728b-109">Una vez que se ha superado el tiempo de acceso, el acceso expira automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1728b-109">After access time is exceeded, the access automatically expires.</span></span>

<span data-ttu-id="1728b-110">Como con otros servicios de Office 365, todos los accesos al entorno de producción de Yammer usan la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="1728b-110">As with other Office 365 services, all access to the Yammer production environment uses multi-factor authentication.</span></span> <span data-ttu-id="1728b-111">Todo el historial de acceso y comandos se atribuye a un usuario y ha sido registrado y revisado con regularidad por el equipo de seguridad de Yammer.</span><span class="sxs-lookup"><span data-stu-id="1728b-111">All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="1728b-112">Para obtener más información acerca de la administración y administración de Yammer, consulte [ayuda del administrador de Yammer](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="1728b-112">For more information about Yammer administration and management, see [Yammer Admin Help](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span></span>