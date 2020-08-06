---
title: Sicurezza e protezione di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- security [Reporting Services]
- Reporting Services, security
ms.assetid: 270075c5-bf12-4467-a775-abbda3d954a5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0f8c7a4186c5236260fb27d8de107ce8c97bd363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637074"
---
# <a name="reporting-services-security-and-protection"></a><span data-ttu-id="5fa65-102">Sicurezza e protezione di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5fa65-102">Reporting Services Security and Protection</span></span>
  <span data-ttu-id="5fa65-103">È possibile usare le informazioni contenute in questa sezione per ottenere altre informazioni sulle caratteristiche di sicurezza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fa65-103">You can use information in this section to learn about the security features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="5fa65-104">Questa sezione descrive inoltre i modelli di autorizzazione e i provider di autenticazione supportati in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fa65-104">This section also explains the authorization models and authentication providers supported in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="extended-protection-for-authentication"></a><span data-ttu-id="5fa65-105">Protezione estesa per l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="5fa65-105">Extended Protection for Authentication</span></span>  
 <span data-ttu-id="5fa65-106">A partire da [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], è disponibile il supporto per la protezione estesa per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="5fa65-106">Beginning with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], support for Extended Protection for Authentication is available.</span></span> <span data-ttu-id="5fa65-107">La caratteristica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supporta l'uso del binding di canale e dell'associazione al servizio per migliorare la protezione dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="5fa65-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] feature supports the use of channel binding and service binding to enhance protection of authentication.</span></span> <span data-ttu-id="5fa65-108">Le funzionalità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devono essere utilizzate con un sistema operativo che supporti la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="5fa65-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features need to be used with an operating system that supports Extended Protection.</span></span> <span data-ttu-id="5fa65-109">Per altre informazioni, vedere [Protezione estesa per l'autenticazione con Reporting Services](extended-protection-for-authentication-with-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="5fa65-109">For more information, see [Extended Protection for Authentication with Reporting Services](extended-protection-for-authentication-with-reporting-services.md).</span></span>  
  
## <a name="authentication-and-authorization"></a><span data-ttu-id="5fa65-110">Autenticazione e autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5fa65-110">Authentication and Authorization</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="5fa65-111">offre diversi tipi di autenticazione per utenti e applicazioni client da autenticare con il server di report.</span><span class="sxs-lookup"><span data-stu-id="5fa65-111">provides different authentication types for users and client applications to authenticate with the report server.</span></span> <span data-ttu-id="5fa65-112">L'utilizzo del tipo di autenticazione corretto per il server di report consente all'organizzazione di ottenere il livello di sicurezza appropriato richiesto dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5fa65-112">Using the right authentication type for your report server enables your organization to achieve the appropriate level of security required by your organization.</span></span> <span data-ttu-id="5fa65-113">Per altre informazioni, vedere [Autenticazione con il server di report](authentication-with-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="5fa65-113">For more information, see [Authentication with the Report Server](authentication-with-the-report-server.md).</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="5fa65-114">usa inoltre ruoli e autorizzazioni per controllare l'accesso dell'utente al contenuto nel catalogo del server di report (in altre parole chi può accedere a che cosa e in che modo può accedervi).</span><span class="sxs-lookup"><span data-stu-id="5fa65-114">also employs roles and permissions to control user access to content in the report server catalog (in other words, who can access what, and how s/he can access it).</span></span> <span data-ttu-id="5fa65-115">Per altre informazioni, vedere [Ruoli e autorizzazioni &#40;Reporting Services&#41;](roles-and-permissions-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="5fa65-115">For more information, see [Roles and Permissions &#40;Reporting Services&#41;](roles-and-permissions-reporting-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="5fa65-116">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="5fa65-116">Related Tasks</span></span>  
  
|<span data-ttu-id="5fa65-117">Descrizioni delle attività</span><span class="sxs-lookup"><span data-stu-id="5fa65-117">Task Descriptions</span></span>|<span data-ttu-id="5fa65-118">Collegamenti</span><span class="sxs-lookup"><span data-stu-id="5fa65-118">Links</span></span>|  
|-----------------------|-----------|  
|<span data-ttu-id="5fa65-119">Configurare Secure Socket Layer (SSL) per proteggere le connessioni client al server di report.</span><span class="sxs-lookup"><span data-stu-id="5fa65-119">Configure the Secure Socket Layer (SSL) to secure client connections to the report server.</span></span>|[<span data-ttu-id="5fa65-120">Configurare connessioni SSL in un server di report in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="5fa65-120">Configure SSL Connections on a Native Mode Report Server</span></span>](configure-ssl-connections-on-a-native-mode-report-server.md)|  
  
  
