---
title: 'Attività 5: impostazione delle relazioni basate su termini | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6569d512-637d-4f7b-82e1-1e8582278b37
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1589ec5843053baa6c42a0b9b0dec019c887da9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720405"
---
# <a name="task-5-setting-term-based-relationships"></a><span data-ttu-id="ce2b1-102">Attività 5: Impostazione delle relazioni basate su termini</span><span class="sxs-lookup"><span data-stu-id="ce2b1-102">Task 5: Setting Term Based Relationships</span></span>
  <span data-ttu-id="ce2b1-103">In questa attività vengono definite alcune relazioni basate su termini per i valori per il dominio **Supplier Name** .</span><span class="sxs-lookup"><span data-stu-id="ce2b1-103">In this task, you define a few term-based relations for values for the **Supplier Name** domain.</span></span> <span data-ttu-id="ce2b1-104">Una relazione basata su termini consente di effettuare una correzione a un termine che fa parte di un valore in un dominio,</span><span class="sxs-lookup"><span data-stu-id="ce2b1-104">A term-based relation enables you to make a correction to a term that is part of a value in a domain.</span></span> <span data-ttu-id="ce2b1-105">consentendo in questo modo a più valori identici ad eccezione dell'ortografia di una parte in comune tra essi di essere considerati sinonimi identici.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-105">It enables multiple values that are identical except for the spelling of a common part of them to be considered identical synonyms.</span></span> <span data-ttu-id="ce2b1-106">Ad esempio, **Inc.** può essere corretto in **incorporato**.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-106">For example, **Inc.** can be corrected to **Incorporated**.</span></span> <span data-ttu-id="ce2b1-107">Queste relazioni vengono utilizzate da DQS nei processi di individuazione delle informazioni, di pulizia o di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-107">DQS uses these relations in the knowledge discovery, cleansing, or matching processes.</span></span> <span data-ttu-id="ce2b1-108">Per altri dettagli, vedere [creare relazioni basate su termini](https://msdn.microsoft.com/library/hh510404.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ce2b1-108">See [Create Term-based Relations](https://msdn.microsoft.com/library/hh510404.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="ce2b1-109">Selezionare **Supplier Name** nell' **elenco di domini**.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-109">Select **Supplier Name** in the **Domain list**.</span></span>  
  
2.  <span data-ttu-id="ce2b1-110">Passare alla scheda **relazioni basate su termini** nel riquadro di destra.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-110">Switch to the **Term-Based Relationships** tab in the right pane.</span></span>  
  
3.  <span data-ttu-id="ce2b1-111">Fare clic sul pulsante **Aggiungi nuova relazione** sulla barra degli strumenti per aggiungere una relazione alla tabella.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-111">Click **Add new relation** button on the toolbar to add a relation to the table.</span></span>  
  
4.  <span data-ttu-id="ce2b1-112">Digitare **Co.** per il campo **valore** e **società** per il campo **Correggi in** .</span><span class="sxs-lookup"><span data-stu-id="ce2b1-112">Type **Co.** for the **Value** field and **Company** for the **Correct To** field.</span></span>  
  
5.  <span data-ttu-id="ce2b1-113">Ripetere i due passaggi precedenti per i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce2b1-113">Repeat the previous two steps for the following values:</span></span>  
  
    |<span data-ttu-id="ce2b1-114">Valore</span><span class="sxs-lookup"><span data-stu-id="ce2b1-114">Value</span></span>|<span data-ttu-id="ce2b1-115">Correggi in</span><span class="sxs-lookup"><span data-stu-id="ce2b1-115">Correct To</span></span>|  
    |-----------|----------------|  
    |<span data-ttu-id="ce2b1-116">Corp.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-116">Corp.</span></span>|<span data-ttu-id="ce2b1-117">Corporation</span><span class="sxs-lookup"><span data-stu-id="ce2b1-117">Corporation</span></span>|  
    |<span data-ttu-id="ce2b1-118">Inc.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-118">Inc.</span></span>|<span data-ttu-id="ce2b1-119">Incorporated</span><span class="sxs-lookup"><span data-stu-id="ce2b1-119">Incorporated</span></span>|  
  
     <span data-ttu-id="ce2b1-120">![Relazioni basate su termini](../../2014/tutorials/media/et-settingtermbasedrelations.jpg "Relazioni basate su termini")</span><span class="sxs-lookup"><span data-stu-id="ce2b1-120">![Term Based Relations](../../2014/tutorials/media/et-settingtermbasedrelations.jpg "Term Based Relations")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="ce2b1-121">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="ce2b1-121">Next Step</span></span>  
 [<span data-ttu-id="ce2b1-122">Attività 6: Impostazione di sinonimi</span><span class="sxs-lookup"><span data-stu-id="ce2b1-122">Task 6: Setting Synonyms</span></span>](../../2014/tutorials/task-6-setting-synonyms.md)  
  
  
