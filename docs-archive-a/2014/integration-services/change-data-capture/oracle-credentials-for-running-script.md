---
title: Credenziali Oracle per l'esecuzione di script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4a301cb0-2f5b-41ba-81bf-46b41d07f137
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 683b313e5b1065c3709c4637ddf968641612cc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712263"
---
# <a name="oracle-credentials-for-running-script"></a><span data-ttu-id="c4f8c-102">Oracle Credentials for Running Script</span><span class="sxs-lookup"><span data-stu-id="c4f8c-102">Oracle Credentials for Running Script</span></span>
  <span data-ttu-id="c4f8c-103">Per eseguire lo script di registrazione supplementare di Oracle da CDC Designer Console, vengono richieste le credenziali dell'utente Oracle che esegue lo script.</span><span class="sxs-lookup"><span data-stu-id="c4f8c-103">To run the Oracle supplemental logging script from the Oracle CDC Designer console, the program prompts you for the credentials of the Oracle user who is running the script.</span></span> <span data-ttu-id="c4f8c-104">Per eseguire questo script, l'utente Oracle deve disporre dell'autorizzazione ALTER TABLE per tutte le tabelle da acquisire e dell'autorizzazione SELECT per la vista DBA_LOG_GROUPS.</span><span class="sxs-lookup"><span data-stu-id="c4f8c-104">To run this script, the Oracle user must have ALTER TABLE permission for all the tables to be captured and SELECT permission on the DBA_LOG_GROUPS view.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="c4f8c-105">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="c4f8c-105">Task List</span></span>  
 <span data-ttu-id="c4f8c-106">Immettere quanto segue nella finestra di dialogo:</span><span class="sxs-lookup"><span data-stu-id="c4f8c-106">Enter the following in this dialog box:</span></span>  
  
 <span data-ttu-id="c4f8c-107">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="c4f8c-107">**Authentication**</span></span>  
  
 <span data-ttu-id="c4f8c-108">Selezionare uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4f8c-108">Select one of the following:</span></span>  
  
-   <span data-ttu-id="c4f8c-109">**Windows Authentication**: selezionare questa opzione per utilizzare le credenziali del dominio Windows correnti.</span><span class="sxs-lookup"><span data-stu-id="c4f8c-109">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="c4f8c-110">È possibile utilizzare questa opzione solo se il database Oracle è configurato per l'utilizzo dell'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="c4f8c-110">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="c4f8c-111">**Oracle Authentication**: se si seleziona questa opzione, è necessario digitare il **nome utente** e la **password** dell'utente nel database Oracle di origine a cui si effettua la connessione.</span><span class="sxs-lookup"><span data-stu-id="c4f8c-111">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Source Oracle database you are connecting to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f8c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4f8c-112">See Also</span></span>  
 <span data-ttu-id="c4f8c-113">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="c4f8c-113">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="c4f8c-114">Rivedere e generare script di registrazione supplementare</span><span class="sxs-lookup"><span data-stu-id="c4f8c-114">Review and Generate Supplemental Logging Scripts</span></span>](review-and-generate-supplemental-logging-scripts.md)  
  
  
