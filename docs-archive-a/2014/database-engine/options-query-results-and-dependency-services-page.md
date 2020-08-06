---
title: Opzioni (pagina risultati query e servizi di dipendenza) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryResults.DependencyServicesGeneral
ms.assetid: dd7f6c31-7d7f-4972-854a-1419a2826dca
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 356714ee933fb40eda7038f4088309b6187f3ed8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636387"
---
# <a name="options-query-results-and-dependency-services-page"></a><span data-ttu-id="46334-102">Opzioni (Risultati delle query e pagina Servizi di dipendenza)</span><span class="sxs-lookup"><span data-stu-id="46334-102">Options (Query Results and Dependency Services Page)</span></span>
  <span data-ttu-id="46334-103">Utilizzare questa pagina per specificare il server a cui connettersi per utilizzare Servizi di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="46334-103">Use this page to specify the server to connect for Dependency Services.</span></span> <span data-ttu-id="46334-104">Servizi di dipendenza consente di estrarre informazioni sulle dipendenze tra oggetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] archiviati in server diversi.</span><span class="sxs-lookup"><span data-stu-id="46334-104">Dependency Services enables you to extract information about dependencies between [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects stored on different servers.</span></span> <span data-ttu-id="46334-105">Per visualizzare le dipendenze degli oggetti, utilizzare la finestra di dialogo **Dipendenze oggetti** in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="46334-105">You view object dependencies by using the **Object Dependencies** dialog box in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="46334-106">**Per saperne di più**</span><span class="sxs-lookup"><span data-stu-id="46334-106">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="46334-107">Aprire la finestra di dialogo Opzioni (pagina Risultati query/Servizi di dipendenza)</span><span class="sxs-lookup"><span data-stu-id="46334-107">Open the Options (Query Results/Dependency Services Page) Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="46334-108">Configurare le opzioni</span><span class="sxs-lookup"><span data-stu-id="46334-108">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-options-query-resultsdependency-services-page-dialog-box"></a><a name="open_dialog"></a><span data-ttu-id="46334-109">Aprire la finestra di dialogo Opzioni (pagina risultati query/servizi di dipendenza)</span><span class="sxs-lookup"><span data-stu-id="46334-109">Open the Options (Query Results/Dependency Services Page) Dialog Box</span></span>  
  
1.  <span data-ttu-id="46334-110">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] fare clic su **Opzioni** nel menu **strumenti** .</span><span class="sxs-lookup"><span data-stu-id="46334-110">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="46334-111">Espandere **Risultati query** e fare clic su **Servizi di dipendenza**.</span><span class="sxs-lookup"><span data-stu-id="46334-111">Expand **Query Results**, and then click **Dependency Services**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="46334-112">Configurare le opzioni</span><span class="sxs-lookup"><span data-stu-id="46334-112">Configure the Options</span></span>  
  
### <a name="options"></a><span data-ttu-id="46334-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="46334-113">Options</span></span>  
 <span data-ttu-id="46334-114">**Server Servizi di dipendenza**</span><span class="sxs-lookup"><span data-stu-id="46334-114">**Dependency Services server**</span></span>  
 <span data-ttu-id="46334-115">Consente di specificare il server in cui è installato Servizi di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="46334-115">Specify the server that Dependency Services is installed on.</span></span>  
  
 <span data-ttu-id="46334-116">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="46334-116">**Authentication**</span></span>  
 <span data-ttu-id="46334-117">Selezionare l'autenticazione di Windows per accedere utilizzando un account utente di Microsoft Windows oppure selezionare l'autenticazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="46334-117">Select Windows Authentication to log on using a Microsoft Windows user account, or select SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="46334-118">Quando un utente si connette con un nome di account di accesso e una password da una connessione non trusted, SQL Server esegue l'autenticazione controllando se è stato impostato un account di accesso di SQL Server e se la password specificata corrisponde a quella registrata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="46334-118">When a user connects with a specified login name and password from a non-trusted connection, SQL Server performs the authentication by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="46334-119">Se SQL Server non è in grado di trovare un account di accesso, l'autenticazione non riesce e viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="46334-119">If SQL Server cannot find the login account, authentication fails, and the user receives an error message.</span></span>  
  
 <span data-ttu-id="46334-120">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="46334-120">**User name**</span></span>  
 <span data-ttu-id="46334-121">Se si utilizza l'autenticazione di SQL Server, specificare un nome utente.</span><span class="sxs-lookup"><span data-stu-id="46334-121">If using SQL Server Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="46334-122">**Password**</span><span class="sxs-lookup"><span data-stu-id="46334-122">**Password**</span></span>  
 <span data-ttu-id="46334-123">Se si utilizza l'autenticazione di SQL Server, specificare una password.</span><span class="sxs-lookup"><span data-stu-id="46334-123">If using SQL Server Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="46334-124">**Test**</span><span class="sxs-lookup"><span data-stu-id="46334-124">**Test**</span></span>  
 <span data-ttu-id="46334-125">Fare clic su questa opzione per testare la connessione.</span><span class="sxs-lookup"><span data-stu-id="46334-125">Click to test the connection.</span></span>