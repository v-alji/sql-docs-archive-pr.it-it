---
title: 'Attività 8: creazione di una regola di dominio composito | Microsoft Docs'
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: cff3b662-7876-4445-9bdd-96be35b3ca0c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4766a1206eb09e98bb20d3712a63762126b682b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635898"
---
# <a name="task-8-creating-a-composite-domain-rule"></a><span data-ttu-id="231ef-102">Attività 8: Creazione di una regola per un dominio composito</span><span class="sxs-lookup"><span data-stu-id="231ef-102">Task 8: Creating a Composite Domain Rule</span></span>
  <span data-ttu-id="231ef-103">In questa attività viene creata una regola per il dominio composito **Address Validation** .</span><span class="sxs-lookup"><span data-stu-id="231ef-103">In this task, you create a rule for the **Address Validation** composite domain.</span></span> <span data-ttu-id="231ef-104">Si definisce una regola tra domini: se **City** è **Los Angeles**, **state** deve essere **CA** , dove **City** e **state** sono due domini.</span><span class="sxs-lookup"><span data-stu-id="231ef-104">You define a cross-domain rule: if **City** is **Los Angeles**, **State** must be **CA** where **City** and **State** are two domains.</span></span>  
  
1.  <span data-ttu-id="231ef-105">Nel riquadro destro passare alla scheda **CD Rules (regole CD** ).</span><span class="sxs-lookup"><span data-stu-id="231ef-105">In the right pane, switch to the **CD Rules** tab.</span></span>  
  
2.  <span data-ttu-id="231ef-106">Fare clic su **Aggiungi una nuova regola di dominio** dalla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="231ef-106">Click **Add a new domain rule** from the toolbar.</span></span>  
  
3.  <span data-ttu-id="231ef-107">Digitare **City-State Rule** per **Name** e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="231ef-107">Type **City-State Rule** for **Name** and press **ENTER**.</span></span>  
  
4.  <span data-ttu-id="231ef-108">Nel riquadro **Compila una regola** selezionare **città** nell'elenco di domini e selezionare la condizione il **valore è uguale a** e digitare **Los Angeles** come valore.</span><span class="sxs-lookup"><span data-stu-id="231ef-108">In the **Build a Rule** pane, select **City** in the domain list, and select condition **Value is equal to** and type **Los Angeles** for the value.</span></span>  
  
5.  <span data-ttu-id="231ef-109">Nel riquadro **then** selezionare **stato** nell'elenco dominio e selezionare il **valore è uguale a**, digitare **CA** come valore e premere **Tab**.</span><span class="sxs-lookup"><span data-stu-id="231ef-109">In the **Then** pane, select **State** in the domain list, and select **Value is equal to**, type **CA** for the value, and press **TAB**.</span></span>  
  
     <span data-ttu-id="231ef-110">![Regola dominio composito](../../2014/tutorials/media/et-creatingacompositedomainrule.jpg "Regola dominio composito")</span><span class="sxs-lookup"><span data-stu-id="231ef-110">![Composite Domain Rule](../../2014/tutorials/media/et-creatingacompositedomainrule.jpg "Composite Domain Rule")</span></span>  
  
6.  <span data-ttu-id="231ef-111">Fare clic sul pulsante **Chiudi** nella parte inferiore della pagina per passare alla pagina principale del client DQS.</span><span class="sxs-lookup"><span data-stu-id="231ef-111">Click **Close** button at the bottom of the page to switch to the main page of DQS Client.</span></span> <span data-ttu-id="231ef-112">Nella lezione successiva verrà pubblicata la Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="231ef-112">You will publish the knowledge base in the next lesson.</span></span> <span data-ttu-id="231ef-113">Si noti che la Knowledge Base è nello stato bloccato (icona di blocco).</span><span class="sxs-lookup"><span data-stu-id="231ef-113">Notice that the knowledge base is in locked state (lock icon).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="231ef-114">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="231ef-114">Next Step</span></span>  
 [<span data-ttu-id="231ef-115">Attività 9: Configurazione di un servizio dati di riferimento</span><span class="sxs-lookup"><span data-stu-id="231ef-115">Task 9: Configuring a Reference Data Service</span></span>](../../2014/tutorials/task-9-configuring-a-reference-data-service.md)  
  
  
