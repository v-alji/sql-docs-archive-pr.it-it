---
title: Procedura di modifica delle proprietà dell'istanza di CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7a6c719a-3735-43b7-b3ab-dfadd325eca2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b02785a32fa1f64d5da0c3202acd7916da1e65ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712288"
---
# <a name="how-to-edit-the-cdc-instance-properties"></a><span data-ttu-id="9ff64-102">Procedura di modifica delle proprietà dell'istanza di CDC</span><span class="sxs-lookup"><span data-stu-id="9ff64-102">How to Edit the CDC Instance Properties</span></span>
  <span data-ttu-id="9ff64-103">In questa procedura viene illustrato come utilizzare CDC Designer Console per modificare le proprietà di configurazione per un'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="9ff64-103">This procedure describes how to use the CDC Designer Console to edit the configuration properties for a CDC instance.</span></span>  
  
### <a name="to-edit-the-cdc-instance-configuration-properties"></a><span data-ttu-id="9ff64-104">Per modificare le proprietà di configurazione di un'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="9ff64-104">To edit the CDC instance configuration properties</span></span>  
  
1.  <span data-ttu-id="9ff64-105">Scegliere **CDC Designer Console** dal menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="9ff64-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="9ff64-106">Nel riquadro sinistro espandere **Change Data Capture** , quindi espandere il servizio che contiene l'istanza con le proprietà che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="9ff64-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance with the properties that you want to edit.</span></span>  
  
3.  <span data-ttu-id="9ff64-107">Selezionare il nome dell'istanza in cui si desidera modificare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="9ff64-107">Select the name of the instance where you want to edit the properties.</span></span>  
  
4.  <span data-ttu-id="9ff64-108">Nel riquadro Actions sul lato destro di CDC Designer Console, fare clic su **Properties**.</span><span class="sxs-lookup"><span data-stu-id="9ff64-108">From the Actions pane on the right side of the CDC Designer Console, click **Properties**.</span></span>  
  
     <span data-ttu-id="9ff64-109">È inoltre possibile fare clic con il pulsante destro del mouse sull'istanza in cui si desidera modificare le proprietà e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9ff64-109">You can also right-click the instance where you want to edit the properties and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="9ff64-110">Nell'editor delle proprietà modificare le proprietà nelle schede seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ff64-110">In the Properties editor, edit the properties in the following tabs:</span></span>  
  
    -   <span data-ttu-id="9ff64-111">**Oracle**: utilizzare la scheda **Oracle** nell'editor delle proprietà per modificare la descrizione fornita nella pagina Create CDC database della New Instance Wizard e le informazioni di connessione al database di log mining Oracle.</span><span class="sxs-lookup"><span data-stu-id="9ff64-111">**Oracle**: Use the **Oracle** tab in the Properties editor to make changes to the description you provided in the Create CDC database page in the New Instance wizard and to make changes to the Oracle Log Mining database connection information.</span></span>  
  
         <span data-ttu-id="9ff64-112">Per informazioni sul contenuto di questa scheda che è possibile modificare, vedere [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9ff64-112">For information about what you can edit in this tab, see [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span></span>  
  
    -   <span data-ttu-id="9ff64-113">**Tables**: utilizzare la scheda **Tables** per apportare modifiche alle tabelle e alle colonne selezionate dal database di origine Oracle.</span><span class="sxs-lookup"><span data-stu-id="9ff64-113">**Tables**: Use the **Tables** tab to make changes to the tables and columns that you selected from the Oracle source database.</span></span>  
  
         <span data-ttu-id="9ff64-114">Per informazioni sul contenuto di questa scheda che è possibile modificare, vedere [Edit Tables](edit-tables.md).</span><span class="sxs-lookup"><span data-stu-id="9ff64-114">For information about what you can edit in this tab, see Edit [Edit Tables](edit-tables.md)</span></span>  
  
    -   <span data-ttu-id="9ff64-115">**Script**: usare la scheda **Script** per eseguire o rieseguire uno script nel database di origine Oracle per la configurazione della registrazione supplementare.</span><span class="sxs-lookup"><span data-stu-id="9ff64-115">**Scripts**: Use the **Scripts** tab to run or re-run a script on the Oracle source database that will set up supplemental logging.</span></span>  
  
         <span data-ttu-id="9ff64-116">Per informazioni sulle operazioni possibili in questa scheda, vedere [Review and Generate Supplemental Logging Scripts](review-and-generate-supplemental-logging-scripts.md).</span><span class="sxs-lookup"><span data-stu-id="9ff64-116">For information about what you can do in this tab, see [Review and Generate Supplemental Logging Scripts](review-and-generate-supplemental-logging-scripts.md).</span></span>  
  
    -   <span data-ttu-id="9ff64-117">**Advanced**: utilizzare la scheda **Advanced** per aggiungere proprietà speciali all'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="9ff64-117">**Advanced**: Use the **Advanced** tab to add special properties to the CDC instance.</span></span>  
  
         <span data-ttu-id="9ff64-118">Per informazioni sulle operazioni possibili in questa scheda, vedere [Edit the Advanced Properties](edit-the-advanced-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9ff64-118">For information about what you can do in this tab, see [Edit the Advanced Properties](edit-the-advanced-properties.md).</span></span>  
  
  
