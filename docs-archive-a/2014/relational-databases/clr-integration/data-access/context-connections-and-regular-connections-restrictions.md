---
title: Restrizioni relative alle connessioni normali e di contesto | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: 0c6fe4cb-d846-40b5-8884-35a9c770f5e8
author: rothja
ms.author: jroth
ms.openlocfilehash: 52f50347a27cdaffe83b252d86c56382b5ef4f31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629872"
---
# <a name="restrictions-on-regular-and-context-connections"></a><span data-ttu-id="33607-102">Restrizioni relative alle connessioni normali e di contesto</span><span class="sxs-lookup"><span data-stu-id="33607-102">Restrictions on Regular and Context Connections</span></span>
  <span data-ttu-id="33607-103">In questo argomento vengono illustrate le restrizioni associate all'esecuzione del codice nel [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] processo tramite il contesto e le connessioni regolari.</span><span class="sxs-lookup"><span data-stu-id="33607-103">This topic discusses the restrictions associated with code executing in the [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] process through context and regular connections.</span></span>  
  
## <a name="restrictions-on-context-connections"></a><span data-ttu-id="33607-104">Restrizioni relative alle connessioni di contesto</span><span class="sxs-lookup"><span data-stu-id="33607-104">Restrictions on Context Connections</span></span>  
 <span data-ttu-id="33607-105">Quando si sviluppa l'applicazione, tenere presenti le restrizioni seguenti che si applicano alle connessioni di contesto:</span><span class="sxs-lookup"><span data-stu-id="33607-105">When developing your application, take into account the following restrictions that apply to context connections:</span></span>  
  
-   <span data-ttu-id="33607-106">È possibile tenere aperta una sola connessione di contesto per volta per una determinata connessione.</span><span class="sxs-lookup"><span data-stu-id="33607-106">You can have only one context connection open at a given time for a given connection.</span></span> <span data-ttu-id="33607-107">Se vengono eseguite contemporaneamente più istruzioni in connessioni separate, ognuna di esse può avere la propria connessione di contesto.</span><span class="sxs-lookup"><span data-stu-id="33607-107">If you have multiple statements running concurrently in separate connections, each one of them can get their own context connection.</span></span> <span data-ttu-id="33607-108">La restrizione non influisce sulle richieste simultanee provenienti da connessioni diverse ma solo su una specifica richiesta in una determinata connessione.</span><span class="sxs-lookup"><span data-stu-id="33607-108">The restriction does not affect concurrent requests from different connections; it only affects a given request on a given connection.</span></span>  
  
-   <span data-ttu-id="33607-109">Non è supportato il servizio MARS (Multiple Active Result Sets).</span><span class="sxs-lookup"><span data-stu-id="33607-109">Multiple Active Result Sets (MARS) is not supported in a context connection.</span></span>  
  
-   <span data-ttu-id="33607-110">La classe `SqlBulkCopy` non funziona.</span><span class="sxs-lookup"><span data-stu-id="33607-110">The `SqlBulkCopy` class does not operate in a context connection.</span></span>  
  
-   <span data-ttu-id="33607-111">Non è supportata l'esecuzione di batch di aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="33607-111">Update batching in a context connection is not supported</span></span>  
  
-   <span data-ttu-id="33607-112">Non è possibile utilizzare `SqlNotificationRequest` con comandi che vengono eseguiti su una connessione di contesto.</span><span class="sxs-lookup"><span data-stu-id="33607-112">`SqlNotificationRequest` cannot be used with commands that execute against a context connection.</span></span>  
  
-   <span data-ttu-id="33607-113">Non è supportato l'annullamento di comandi che vengono eseguiti su una connessione di contesto.</span><span class="sxs-lookup"><span data-stu-id="33607-113">Canceling commands that are running against the context connection is not supported.</span></span> <span data-ttu-id="33607-114">Il metodo `SqlCommand.Cancel` ignora la richiesta senza avvisare.</span><span class="sxs-lookup"><span data-stu-id="33607-114">The `SqlCommand.Cancel` method silently ignores the request.</span></span>  
  
-   <span data-ttu-id="33607-115">Quando si utilizza "context connection=true", non è possibile utilizzare altre parole chiave della stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="33607-115">No other connection string keywords can be used when you use "context connection=true".</span></span>  
  
-   <span data-ttu-id="33607-116">La proprietà `SqlConnection.DataSource` restituisce null invece del nome dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se la stringa di connessione per l'oggetto `SqlConnection` è "context connection=true".</span><span class="sxs-lookup"><span data-stu-id="33607-116">The `SqlConnection.DataSource` property returns null if the connection string for the `SqlConnection` is "context connection=true", instead of the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="33607-117">L'impostazione della proprietà `SqlCommand.CommandTimeout` non ha effetto quando il comando viene eseguito su una connessione di contesto.</span><span class="sxs-lookup"><span data-stu-id="33607-117">Setting the `SqlCommand.CommandTimeout` property has no effect when the command is executed against a context connection.</span></span>  
  
## <a name="restrictions-on-regular-connections"></a><span data-ttu-id="33607-118">Restrizioni relative alle connessioni normali</span><span class="sxs-lookup"><span data-stu-id="33607-118">Restrictions on Regular Connections</span></span>  
 <span data-ttu-id="33607-119">Quando si sviluppa l'applicazione, tenere presenti le restrizioni seguenti che si applicano alle connessioni normali:</span><span class="sxs-lookup"><span data-stu-id="33607-119">When developing your application, take into account the following restrictions that apply to regular connections:</span></span>  
  
-   <span data-ttu-id="33607-120">Non è supportata l'esecuzione asincrona di comandi su server interni.</span><span class="sxs-lookup"><span data-stu-id="33607-120">Asynchronous command execution against internal servers is not supported.</span></span> <span data-ttu-id="33607-121">Se si include "async=true" nella stringa di connessione di un comando, quindi si esegue il comando, viene generata l'eccezione `System.NotSupportedException`.</span><span class="sxs-lookup"><span data-stu-id="33607-121">Including "async=true" in the connection string of a command, and then executing the command, results in `System.NotSupportedException` being thrown.</span></span> <span data-ttu-id="33607-122">Viene visualizzato il messaggio "Asynchronous Processing non è supportato se eseguito in un processo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]".</span><span class="sxs-lookup"><span data-stu-id="33607-122">This message appears: "Asynchronous processing is not supported when running inside the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process."</span></span>  
  
-   <span data-ttu-id="33607-123">Non è supportato l'oggetto `SqlDependency`.</span><span class="sxs-lookup"><span data-stu-id="33607-123">`SqlDependency` object is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33607-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33607-124">See Also</span></span>  
 [<span data-ttu-id="33607-125">Connessione di contesto</span><span class="sxs-lookup"><span data-stu-id="33607-125">Context Connection</span></span>](context-connection.md)  
  
  
