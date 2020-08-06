---
title: Script di registrazione supplementare Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5e6ee618-b89b-46c7-92ad-4fc5ef7b777a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0aa55e71c17574eba9e25e098a3881b0eb4c9e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712260"
---
# <a name="oracle-supplemental-logging-script"></a><span data-ttu-id="d3829-102">Script di registrazione supplementare Oracle</span><span class="sxs-lookup"><span data-stu-id="d3829-102">Oracle Supplemental Logging Script</span></span>
  <span data-ttu-id="d3829-103">Questa finestra di dialogo contiene lo script della registrazione supplementare Oracle.</span><span class="sxs-lookup"><span data-stu-id="d3829-103">This dialog box shows the script the Oracle supplemental logging script.</span></span>  
  
 <span data-ttu-id="d3829-104">Quando si prepara un'istanza di CDC per l'utilizzo, nella finestra di progettazione di CDC viene creato uno script SQL Oracle per la configurazione della registrazione supplementare per le tabelle da acquisire.</span><span class="sxs-lookup"><span data-stu-id="d3829-104">When you prepare a CDC Instance for use, the CDC Designer creates an Oracle SQL script that sets up supplemental logging for the tables to be captured.</span></span> <span data-ttu-id="d3829-105">Nello script di registrazione supplementare è indicato quando una tabella specifica viene aggiornata. I record delle modifiche scritti nel log delle transazioni dovrebbero contenere i dati di tutte le colonne di interesse, non solo quelle modificate.</span><span class="sxs-lookup"><span data-stu-id="d3829-105">The supplemental logging script tells Oracle that when a specific table is updated, the change records it writes to the transaction log should contain the data of all columns of interest, not just the columns that changed.</span></span>  
  
 <span data-ttu-id="d3829-106">A seconda dei criteri DBA Oracle nell'organizzazione, l'esecuzione dello script di registrazione supplementare potrebbe richiedere l'esame e l'approvazione da parte di un amministratore di database Oracle.</span><span class="sxs-lookup"><span data-stu-id="d3829-106">Depending on the Oracle DBA policies in your organization, running the supplemental logging script may require a review and approval by an Oracle DBA.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d3829-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d3829-107">Options</span></span>  
 <span data-ttu-id="d3829-108">Di seguito sono riportate le opzioni disponibili relative all'esecuzione dello script.</span><span class="sxs-lookup"><span data-stu-id="d3829-108">The following are the available options for how to execute the script.</span></span>  
  
 <span data-ttu-id="d3829-109">**Esegui script**</span><span class="sxs-lookup"><span data-stu-id="d3829-109">**Run Script**</span></span>  
 <span data-ttu-id="d3829-110">Tramite questa opzione è possibile eseguire lo script di registrazione supplementare nelle tabelle definite per l'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="d3829-110">Runs the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="d3829-111">Per eseguire questo script, l'utente Oracle deve disporre dell'autorizzazione ALTER TABLE per tutte le tabelle da acquisire e dell'autorizzazione SELECT per la vista DBA_LOG_GROUPS.</span><span class="sxs-lookup"><span data-stu-id="d3829-111">To run this script, the Oracle user must have ALTER TABLE permission for all the tables to be captured and SELECT permission on the DBA_LOG_GROUPS view.</span></span> <span data-ttu-id="d3829-112">L'utente Oracle deve inoltre disporre delle credenziali per utilizzare il database Oracle con le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="d3829-112">In addition, the Oracle user must have the credentials for an Oracle database use with the required permissions.</span></span> <span data-ttu-id="d3829-113">Il programma richiederà l'immissione delle credenziali Oracle per l'esecuzione dello script.</span><span class="sxs-lookup"><span data-stu-id="d3829-113">You can let the program prompt you for the Oracle credentials and then have it run the script.</span></span>  
  
 <span data-ttu-id="d3829-114">**Save As**</span><span class="sxs-lookup"><span data-stu-id="d3829-114">**Save As**</span></span>  
 <span data-ttu-id="d3829-115">Tramite questa opzione è possibile salvare lo script in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="d3829-115">Saves the script to a text file.</span></span> <span data-ttu-id="d3829-116">Utilizzare se un amministratore di database Oracle (DBA) deve esaminare ed eseguire lo script di registrazione supplementare. Salvando lo script in un file di testo sarà infatti possibile inviare quest'ultimo all'amministratore di database Oracle tramite posta elettronica o altro affinché possa essere eseguito in un secondo momento (tramite l'utilità Oracle SQL\*Plus o altro strumento per l'esecuzione di script in un database Oracle).</span><span class="sxs-lookup"><span data-stu-id="d3829-116">This is used if an Oracle database administrator (DBA) needs to examine and execute the supplemental logging script, the program lets you save the script to a text file that you can later send to the Oracle DBA by email or by other means to be execute later (by using the SQL\*Plus Oracle utility or other tool for running scripts on an Oracle database).</span></span>  
  
 <span data-ttu-id="d3829-117">**Copia**</span><span class="sxs-lookup"><span data-stu-id="d3829-117">**Copy**</span></span>  
 <span data-ttu-id="d3829-118">Tramite questa opzione è possibile copiare lo script negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="d3829-118">Copies the script to the clipboard.</span></span> <span data-ttu-id="d3829-119">Incollare lo script in un percorso desiderato qualora un amministratore di database Oracle (DBA) debba esaminare ed eseguire lo script di registrazione supplementare.</span><span class="sxs-lookup"><span data-stu-id="d3829-119">When ready you can paste the script in any location you need in case an Oracle database administrator (DBA) needs to examine and execute the supplemental logging script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3829-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3829-120">See Also</span></span>  
 <span data-ttu-id="d3829-121">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="d3829-121">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="d3829-122">Gestire un'istanza di CDC</span><span class="sxs-lookup"><span data-stu-id="d3829-122">Manage a CDC Instance</span></span>](manage-a-cdc-instance.md)  
  
  
