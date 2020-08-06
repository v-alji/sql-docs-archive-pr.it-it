---
title: 'Lezione 2: Configurazione delle autorizzazioni per gli oggetti di database | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
helpviewer_keywords:
- database permissions
ms.assetid: f964b66a-ec32-44c2-a185-6a0f173bfa22
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: fcc6ee3ddf9be072b51bd568fd3e72eb6c871785
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724332"
---
# <a name="lesson-2-configuring-permissions-on-database-objects"></a><span data-ttu-id="d40c5-102">Lezione 2: Configurazione delle autorizzazioni per gli oggetti di database</span><span class="sxs-lookup"><span data-stu-id="d40c5-102">Lesson 2: Configuring Permissions on Database Objects</span></span>
  <span data-ttu-id="d40c5-103">La concessione di un accesso utente a un database consiste in tre passaggi.</span><span class="sxs-lookup"><span data-stu-id="d40c5-103">Granting a user access to a database involves three steps.</span></span> <span data-ttu-id="d40c5-104">Viene innanzitutto creato un account di accesso,</span><span class="sxs-lookup"><span data-stu-id="d40c5-104">First, you create a login.</span></span> <span data-ttu-id="d40c5-105">il quale consente all'utente di connettersi a [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d40c5-105">The login lets the user connect to the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="d40c5-106">L'account di accesso viene quindi configurato come utente nel database specificato.</span><span class="sxs-lookup"><span data-stu-id="d40c5-106">Then you configure the login as a user in the specified database.</span></span> <span data-ttu-id="d40c5-107">Viene infine concessa l'autorizzazione utente per gli oggetti di database.</span><span class="sxs-lookup"><span data-stu-id="d40c5-107">And finally, you grant that user permission to database objects.</span></span> <span data-ttu-id="d40c5-108">In questa lezione vengono illustrati tali passaggi e viene descritto come creare due oggetti, ovvero una vista e una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d40c5-108">This lesson shows you these three steps, and shows you how to create a view and a stored procedure as the object.</span></span>  
  
 <span data-ttu-id="d40c5-109">In questa lezione sono inclusi gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d40c5-109">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="d40c5-110">Creazione di un account di accesso</span><span class="sxs-lookup"><span data-stu-id="d40c5-110">Creating a Login</span></span>](lesson-2-1-creating-a-login.md)  
  
-   [<span data-ttu-id="d40c5-111">Concessione dell'accesso a un database</span><span class="sxs-lookup"><span data-stu-id="d40c5-111">Granting Access to a Database</span></span>](lesson-2-2-granting-access-to-a-database.md)  
  
-   [<span data-ttu-id="d40c5-112">Creazione di viste e stored procedure</span><span class="sxs-lookup"><span data-stu-id="d40c5-112">Creating Views and Stored Procedures</span></span>](lesson-2-3-creating-views-and-stored-procedures.md)  
  
-   [<span data-ttu-id="d40c5-113">Concessione dell'accesso a un oggetto di database</span><span class="sxs-lookup"><span data-stu-id="d40c5-113">Granting Access to a Database Object</span></span>](lesson-2-4-granting-access-to-a-database-object.md)  
  
-   [<span data-ttu-id="d40c5-114">Riepilogo: Configurazione delle autorizzazioni per gli oggetti di database</span><span class="sxs-lookup"><span data-stu-id="d40c5-114">Summary: Configuring Permissions on Database Objects</span></span>](lesson-2-5-summary-configuring-permissions-on-database-objects.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="d40c5-115">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="d40c5-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="d40c5-116">Creazione di un account di accesso</span><span class="sxs-lookup"><span data-stu-id="d40c5-116">Creating a Login</span></span>](lesson-2-1-creating-a-login.md)  
  
  
