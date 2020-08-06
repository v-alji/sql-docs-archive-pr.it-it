---
title: Proprietà SQL Server Agent (pagina Connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.connection.f1
ms.assetid: d6a677ff-60ad-47ba-a0cb-df4193b165e0
author: stevestein
ms.author: sstein
ms.openlocfilehash: ec9ae575f1ced510d95256d6827435e5b6ad89d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636519"
---
# <a name="sql-server-agent-properties-connection-page"></a><span data-ttu-id="0d074-102">Proprietà SQL Server Agent (pagina Connessione)</span><span class="sxs-lookup"><span data-stu-id="0d074-102">SQL Server Agent Properties (Connection Page)</span></span>
  <span data-ttu-id="0d074-103">Utilizzare questa pagina per visualizzare e modificare le impostazioni per la connessione dal [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servizio Agent a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d074-103">Use this page to view and modify the settings for the connection from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="0d074-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0d074-104">Options</span></span>  
 <span data-ttu-id="0d074-105">**Alias server host locale**</span><span class="sxs-lookup"><span data-stu-id="0d074-105">**Alias local host server**</span></span>  
 <span data-ttu-id="0d074-106">Consente di specificare l'alias da utilizzare per la connessione all'istanza locale di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d074-106">Specifies the alias to use to connect to the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0d074-107">Se non è possibile utilizzare le opzioni di connessione predefinite per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, definire un alias per l'istanza e specificarlo qui.</span><span class="sxs-lookup"><span data-stu-id="0d074-107">If you cannot use the default connection options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, define an alias for the instance and specify the alias here.</span></span>  
  
 <span data-ttu-id="0d074-108">**Usa autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="0d074-108">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="0d074-109">Consente di impostare l'autenticazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows come metodo di autenticazione predefinito per la connessione all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d074-109">Sets [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication as the authentication method used to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0d074-110">Agent si connette come l'account con cui viene eseguito il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="0d074-110">Agent connects as the account that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service runs as.</span></span>  
  
 <span data-ttu-id="0d074-111">**Usa autenticazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="0d074-111">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="0d074-112">Consente di impostare l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] come metodo di autenticazione predefinito per la connessione all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d074-112">Sets [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication as the authentication method used to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0d074-113">L'autenticazione è disponibile per garantire la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="0d074-113">Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="0d074-114">Per un livello di sicurezza migliore, utilizzare l'autenticazione di Windows, se possibile.</span><span class="sxs-lookup"><span data-stu-id="0d074-114">For improved security, use Windows Authentication if possible.</span></span>  
  
 <span data-ttu-id="0d074-115">**Accesso**</span><span class="sxs-lookup"><span data-stu-id="0d074-115">**Login**</span></span>  
 <span data-ttu-id="0d074-116">Consente di specificare il nome dell'account di accesso per la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d074-116">Specifies the login name to use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0d074-117">**Password**</span><span class="sxs-lookup"><span data-stu-id="0d074-117">**Password**</span></span>  
 <span data-ttu-id="0d074-118">Consente di specificare la password per la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d074-118">Specifies the password to use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
  
