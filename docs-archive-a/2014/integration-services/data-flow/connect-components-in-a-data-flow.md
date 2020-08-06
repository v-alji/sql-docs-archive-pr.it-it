---
title: Connettere componenti in un flusso di dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], connections
- connections [Integration Services], data flow components
ms.assetid: 70616a58-8921-4218-85bf-f3e90c5a9dbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8fc4a2fa81e9b110c27ea63b16d835d069bf12cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712255"
---
# <a name="connect-components-in-a-data-flow"></a><span data-ttu-id="84d79-102">Connessione di componenti in un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="84d79-102">Connect Components in a Data Flow</span></span>
  <span data-ttu-id="84d79-103">Questa procedura descrive la connessione dell'output dei componenti di un flusso di dati ad altri componenti dello stesso flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="84d79-103">This procedure describes how to connect the output of components in a data flow to other components within the same data flow.</span></span>  
  
### <a name="to-connect-components-in-a-data-flow"></a><span data-ttu-id="84d79-104">Per connettere componenti in un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="84d79-104">To connect components in a data flow</span></span>  
  
1.  <span data-ttu-id="84d79-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="84d79-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="84d79-106">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="84d79-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="84d79-107">Fare clic sulla scheda **Flusso di controllo** , quindi fare doppio clic sull'attività Flusso di dati che contiene il flusso di dati in cui si desidera connettere i componenti.</span><span class="sxs-lookup"><span data-stu-id="84d79-107">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow in which you want to connect components.</span></span>  
  
4.  <span data-ttu-id="84d79-108">Nell'area di progettazione della scheda **Flusso di dati** selezionare la trasformazione o l'origine da connettere.</span><span class="sxs-lookup"><span data-stu-id="84d79-108">On the design surface of the **Data Flow** tab, select the transformation or source that you want to connect.</span></span>  
  
5.  <span data-ttu-id="84d79-109">Trascinare la freccia verde dell'output di un'origine o trasformazione a una destinazione o trasformazione.</span><span class="sxs-lookup"><span data-stu-id="84d79-109">Drag the green output arrow of a transformation or a source to a transformation or to a destination.</span></span> <span data-ttu-id="84d79-110">In alcuni componenti flussi di dati sono inclusi output degli errori che è possibile connettere allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="84d79-110">Some data flow components have error outputs that you can connect in the same way.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="84d79-111">Alcuni componenti flussi di dati possono includere più output ed è possibile connettere ogni output a una trasformazione o destinazione diversa.</span><span class="sxs-lookup"><span data-stu-id="84d79-111">Some data flow components can have multiple outputs and you can connect each output to a different transformation or destination.</span></span>  
  
6.  <span data-ttu-id="84d79-112">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="84d79-112">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d79-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84d79-113">See Also</span></span>  
 <span data-ttu-id="84d79-114">[Aggiunta o eliminazione di un componente in un flusso di dati](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="84d79-114">[Add or Delete a Component in a Data Flow](data-flow.md) </span></span>  
 <span data-ttu-id="84d79-115">[Configurare un output degli errori in un componente flusso di dati](../configure-an-error-output-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="84d79-115">[Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="84d79-116">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="84d79-116">Data Flow</span></span>](data-flow.md)  
  
  
