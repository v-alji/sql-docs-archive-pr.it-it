---
title: Opzioni di convalida delle sottoscrizioni (sottoscrizioni di tipo merge) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.mergeoptions.f1
helpviewer_keywords:
- Subscription Validation Options dialog box
ms.assetid: 4958c4ab-2025-42ce-b836-6fb4e9e6f24d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 458da0387dbaa1b366348c374748c42946893feb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725439"
---
# <a name="subscription-validation-options-merge-subscriptions"></a><span data-ttu-id="0dd6d-102">Opzioni di convalida delle sottoscrizioni (sottoscrizioni di tipo merge)</span><span class="sxs-lookup"><span data-stu-id="0dd6d-102">Subscription Validation Options (Merge Subscriptions)</span></span>
  <span data-ttu-id="0dd6d-103">Utilizzare la finestra di dialogo **Opzioni di convalida delle sottoscrizioni** per specificare se la convalida deve utilizzare solo un conteggio di righe o un conteggio di righe e un checksum binario.</span><span class="sxs-lookup"><span data-stu-id="0dd6d-103">Use the **Subscription Validation Options** dialog box to specify whether validation should use a row count only or a row count and a binary checksum.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0dd6d-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0dd6d-104">Options</span></span>  
 <span data-ttu-id="0dd6d-105">**Verifica solo il conteggio delle righe**</span><span class="sxs-lookup"><span data-stu-id="0dd6d-105">**Verify the row counts only**</span></span>  
 <span data-ttu-id="0dd6d-106">Consente di verificare che la tabella nel Sottoscrittore abbia lo stesso numero di righe della tabella nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0dd6d-106">Select to validate whether the table at the Subscriber has the same number of rows as the table at the Publisher.</span></span> <span data-ttu-id="0dd6d-107">Questa opzione non convalida la corrispondenza del contenuto delle righe.</span><span class="sxs-lookup"><span data-stu-id="0dd6d-107">This method does not validate that the content of the rows matches.</span></span> <span data-ttu-id="0dd6d-108">La convalida del conteggio delle righe è un controllo non approfondito che consente comunque di evidenziare eventuali problemi dei dati.</span><span class="sxs-lookup"><span data-stu-id="0dd6d-108">Row count validation provides a lightweight approach to validation that can make you aware of issues with your data.</span></span>  
  
 <span data-ttu-id="0dd6d-109">**Verifica il conteggio delle righe e confronta i valori di checksum per la verifica dei dati delle righe**</span><span class="sxs-lookup"><span data-stu-id="0dd6d-109">**Verify the row counts and compare checksums to verify the row data**</span></span>  
 <span data-ttu-id="0dd6d-110">Oltre al conteggio delle righe nel server di pubblicazione e nel Sottoscrittore, viene calcolato un checksum di tutti i dati utilizzando l'algoritmo di checksum binario.</span><span class="sxs-lookup"><span data-stu-id="0dd6d-110">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="0dd6d-111">In caso di esito negativo durante il conteggio delle righe il checksum non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="0dd6d-111">If the row count fails, the checksum is not performed.</span></span> <span data-ttu-id="0dd6d-112">Questa opzione non è valida per [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssEW](../../includes/ssew-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0dd6d-112">This option is not valid for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dd6d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0dd6d-113">See Also</span></span>  
 <span data-ttu-id="0dd6d-114">[Convalida dei dati nel Sottoscrittore](validate-data-at-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="0dd6d-114">[Validate Data at the Subscriber](validate-data-at-the-subscriber.md) </span></span>  
 [<span data-ttu-id="0dd6d-115">Convalida dei dati replicati</span><span class="sxs-lookup"><span data-stu-id="0dd6d-115">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
