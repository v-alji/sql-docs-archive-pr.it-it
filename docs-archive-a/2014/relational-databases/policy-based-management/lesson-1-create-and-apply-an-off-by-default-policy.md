---
title: 'Lezione 1: Creare e applicare criteri Disattivata per impostazione predefinita | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: d31367db-b7db-44c4-8df2-f1240474cf78
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9a76df1a72b93d09c5c1c199cb0246dbb51c9cbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624672"
---
# <a name="lesson-1-create-and-apply-an-off-by-default-policy"></a><span data-ttu-id="462e5-102">Lezione 1: Creare e applicare criteri Disattivata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="462e5-102">Lesson 1: Create and Apply an Off By Default Policy</span></span>
  <span data-ttu-id="462e5-103">Tramite i criteri della gestione basata su criteri è possibile amministrare una o più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], uno o più oggetti dell'istanza, una o più istanze del server, uno o più database o uno o più oggetti di database.</span><span class="sxs-lookup"><span data-stu-id="462e5-103">Using Policy-Based Management policies, you can administer one or more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], one or more instance objects, server instances, one or more databases, or one or more database objects.</span></span> <span data-ttu-id="462e5-104">Gli amministratori del database desiderano impedire che in determinati server sia abilitato Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="462e5-104">As the database administrator, you want to ensure that certain servers do not have Database Mail enabled.</span></span> <span data-ttu-id="462e5-105">In questa lezione verranno creati una condizione e i criteri per l'impostazione dell'opzione server in questione.</span><span class="sxs-lookup"><span data-stu-id="462e5-105">In this lesson, you will create a condition and a policy that sets that server option.</span></span> <span data-ttu-id="462e5-106">Il server verrà quindi testato per verificarne la conformità ai criteri.</span><span class="sxs-lookup"><span data-stu-id="462e5-106">You will test the server to see whether it complies with the policy.</span></span> <span data-ttu-id="462e5-107">Si utilizzeranno infine i criteri per riconfigurare il server per renderlo conforme.</span><span class="sxs-lookup"><span data-stu-id="462e5-107">Then, you will use the policy to reconfigure the server to bring the server into compliance.</span></span>  
  
 <span data-ttu-id="462e5-108">In questa lezione sono inclusi gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="462e5-108">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="462e5-109">Creazione di criteri Disattivata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="462e5-109">Create the Off By Default Policy</span></span>](lesson-1-1-create-the-off-by-default-policy.md)  
  
-   [<span data-ttu-id="462e5-110">Configurazione di un server per l'esecuzione di criteri Disattivata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="462e5-110">Configure a Server to Run the Off By Default Policy</span></span>](lesson-1-2-configure-a-server-to-run-the-off-by-default-policy.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="462e5-111">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="462e5-111">Next Task in Lesson</span></span>  
 [<span data-ttu-id="462e5-112">Creazione di criteri Disattivata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="462e5-112">Create the Off By Default Policy</span></span>](lesson-1-1-create-the-off-by-default-policy.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="462e5-113">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="462e5-113">Next Lesson</span></span>  
 [<span data-ttu-id="462e5-114">Lezione 2: Creare e applicare criteri per gli standard di denominazione</span><span class="sxs-lookup"><span data-stu-id="462e5-114">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
  
  
