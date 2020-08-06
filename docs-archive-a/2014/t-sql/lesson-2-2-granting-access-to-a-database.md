---
title: Concessione dell'accesso a un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database access
ms.assetid: 686edfe2-3650-48a6-a2da-9d46fa211ad8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 45b6d6c8dcd9c04d18489807271802aafee785b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636990"
---
# <a name="granting-access-to-a-database"></a><span data-ttu-id="bfa00-102">Concessione dell'accesso a un database</span><span class="sxs-lookup"><span data-stu-id="bfa00-102">Granting Access to a Database</span></span>
  <span data-ttu-id="bfa00-103">L'utente Mary dispone ora dell'accesso all'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], ma non delle autorizzazioni necessarie per accedere ai database.</span><span class="sxs-lookup"><span data-stu-id="bfa00-103">Mary now has access to this instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but does not have permission to access the databases.</span></span> <span data-ttu-id="bfa00-104">L'utente non dispone inoltre dell'accesso al proprio database predefinito **TestData** a meno che non lo si autorizzi in qualità di utente del database.</span><span class="sxs-lookup"><span data-stu-id="bfa00-104">She does not even have access to her default database **TestData** until you authorize her as a database user.</span></span>  
  
 <span data-ttu-id="bfa00-105">Per concedere l'accesso all'utente Mary, passare al database **TestData** e quindi utilizzare l'istruzione CREATE USER per eseguire il mapping dell'account utente a un utente denominato Mary.</span><span class="sxs-lookup"><span data-stu-id="bfa00-105">To grant Mary access, switch to the **TestData** database, and then use the CREATE USER statement to map her login to a user named Mary.</span></span>  
  
### <a name="to-create-a-user-in-a-database"></a><span data-ttu-id="bfa00-106">Per creare un utente in un database</span><span class="sxs-lookup"><span data-stu-id="bfa00-106">To create a user in a database</span></span>  
  
1.  <span data-ttu-id="bfa00-107">Digitare ed eseguire le istruzioni seguenti sostituendo `computer_name` con il nome del computer in uso per concedere all'utente `Mary` l'accesso al database `TestData` .</span><span class="sxs-lookup"><span data-stu-id="bfa00-107">Type and execute the following statements (replacing `computer_name` with the name of your computer) to grant `Mary` access to the `TestData` database.</span></span>  
  
    ```  
    USE [TestData];  
    GO  
  
    CREATE USER [Mary] FOR LOGIN [computer_name\Mary];  
    GO  
  
    ```  
  
     <span data-ttu-id="bfa00-108">L'utente Mary dispone ora dell'accesso a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e al database `TestData` .</span><span class="sxs-lookup"><span data-stu-id="bfa00-108">Now, Mary has access to both [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and the `TestData` database.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="bfa00-109">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="bfa00-109">Next Task in Lesson</span></span>  
 [<span data-ttu-id="bfa00-110">Creazione di viste e stored procedure</span><span class="sxs-lookup"><span data-stu-id="bfa00-110">Creating Views and Stored Procedures</span></span>](lesson-2-3-creating-views-and-stored-procedures.md)  
  
  
