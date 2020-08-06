---
title: Opzioni di convalida delle sottoscrizioni (sottoscrizioni transazionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.options.f1
helpviewer_keywords:
- Subscription Validation Options dialog box
ms.assetid: fd66ad1f-df01-4240-9e89-8f41bff12c1e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 40a617dd1beff24f8f072f5d139bec7c1ca65f33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725435"
---
# <a name="subscription-validation-options-transactional-subscriptions"></a><span data-ttu-id="f429c-102">Opzioni di convalida delle sottoscrizioni (sottoscrizioni transazionali)</span><span class="sxs-lookup"><span data-stu-id="f429c-102">Subscription Validation Options (Transactional Subscriptions)</span></span>
  <span data-ttu-id="f429c-103">La finestra di dialogo **Opzioni di convalida delle sottoscrizioni** consente di specificare se la convalida deve utilizzare solo un conteggio di righe o un conteggio di righe e un checksum binario.</span><span class="sxs-lookup"><span data-stu-id="f429c-103">Use the **Subscription Validation Options** dialog box to specify whether validation should use a row count only, or a row count and a binary checksum.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f429c-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f429c-104">Options</span></span>  
 <span data-ttu-id="f429c-105">**Verificare che il Sottoscrittore includa lo stesso numero di righe di dati replicati del server di pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="f429c-105">**Verify that the Subscriber has the same number of rows of replicated data as the Publisher**</span></span>  
 <span data-ttu-id="f429c-106">Consente di selezionare il tipo di convalida del conteggio di righe da eseguire.</span><span class="sxs-lookup"><span data-stu-id="f429c-106">Select the type of row count validation to perform.</span></span> <span data-ttu-id="f429c-107">Per le pubblicazioni Oracle, l'unica opzione disponibile è **Esegui il conteggio di righe effettivo tramite una query diretta nelle tabelle**.</span><span class="sxs-lookup"><span data-stu-id="f429c-107">For Oracle publications, the only available option is **Compute an actual row count by querying the tables directly**.</span></span>  
  
 <span data-ttu-id="f429c-108">**Confronta i valori di checksum per la verifica dei dati delle righe**</span><span class="sxs-lookup"><span data-stu-id="f429c-108">**Compare checksums to verify row data**</span></span>  
 <span data-ttu-id="f429c-109">Oltre al conteggio delle righe nel server di pubblicazione e nel Sottoscrittore, viene calcolato un checksum di tutti i dati utilizzando l'algoritmo di checksum binario.</span><span class="sxs-lookup"><span data-stu-id="f429c-109">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="f429c-110">In caso di esito negativo durante il conteggio delle righe il checksum non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="f429c-110">If the row count fails, the checksum is not performed.</span></span>  
  
 <span data-ttu-id="f429c-111">**Arresta l'agente di distribuzione al termine della convalida**</span><span class="sxs-lookup"><span data-stu-id="f429c-111">**Stop the Distribution Agent after the validation has completed**</span></span>  
 <span data-ttu-id="f429c-112">Per impostazione predefinita, l'agente di distribuzione viene eseguito in modo continuativo.</span><span class="sxs-lookup"><span data-stu-id="f429c-112">By default, the Distribution Agent runs continuously.</span></span> <span data-ttu-id="f429c-113">Selezionare questa opzione per arrestare l'agente dopo l'esecuzione della convalida.</span><span class="sxs-lookup"><span data-stu-id="f429c-113">Select this option to stop the agent after validation is performed.</span></span> <span data-ttu-id="f429c-114">In tal modo è possibile controllare se la convalida è riuscita prima di continuare la replica dei dati nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="f429c-114">This allows you to check whether validation was successful before continuing to replicate data to the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f429c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f429c-115">See Also</span></span>  
 <span data-ttu-id="f429c-116">[Convalida dei dati nel Sottoscrittore](validate-data-at-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="f429c-116">[Validate Data at the Subscriber](validate-data-at-the-subscriber.md) </span></span>  
 [<span data-ttu-id="f429c-117">Convalida dei dati replicati</span><span class="sxs-lookup"><span data-stu-id="f429c-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
