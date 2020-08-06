---
title: Destinazione DataReader | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.datareaderdest.f1
helpviewer_keywords:
- DataReader destination
- destinations [Integration Services], DataReader
ms.assetid: 56fcc4bf-c901-42c3-a71d-110039293431
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 40cfe5d99c33eb19d415f204173005a64bde7855
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726143"
---
# <a name="datareader-destination"></a><span data-ttu-id="19e50-102">DataReader - destinazione</span><span class="sxs-lookup"><span data-stu-id="19e50-102">DataReader Destination</span></span>
  <span data-ttu-id="19e50-103">La destinazione DataReader espone i dati in un flusso di dati utilizzando l'interfaccia `DataReader` di ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="19e50-103">The DataReader destination exposes the data in a data flow by using the ADO.NET `DataReader` interface.</span></span> <span data-ttu-id="19e50-104">I dati possono essere quindi utilizzati da altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="19e50-104">The data can then be consumed by other applications.</span></span> <span data-ttu-id="19e50-105">È ad esempio possibile configurare l'origine dati di un report di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in modo da usare i risultati dell'esecuzione di un pacchetto di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19e50-105">For example, you can configure the data source of a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report to use the result of running a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="19e50-106">A tale scopo è necessario creare un flusso di dati che implementa la destinazione DataReader.</span><span class="sxs-lookup"><span data-stu-id="19e50-106">To do this, you create a data flow that implements the DataReader destination.</span></span>  
  
 <span data-ttu-id="19e50-107">Per informazioni sull'accesso e la lettura di valori nella destinazione DataReader a livello di programmazione, vedere [Caricamento dell'output di un pacchetto locale](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md).</span><span class="sxs-lookup"><span data-stu-id="19e50-107">For information about accessing and reading values in the DataReader destination programmatically, see [Loading the Output of a Local Package](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md).</span></span>  
  
## <a name="configuration-of-the-datareader-destination"></a><span data-ttu-id="19e50-108">Configurazione della destinazione DataReader</span><span class="sxs-lookup"><span data-stu-id="19e50-108">Configuration of the DataReader Destination</span></span>  
 <span data-ttu-id="19e50-109">È possibile specificare un valore di timeout per la destinazione DataReader e indicare se tale destinazione genera errori in caso di timeout.</span><span class="sxs-lookup"><span data-stu-id="19e50-109">You can specify a time-out value for the DataReader destination and indicate whether the destination should fail if a time-out occurs.</span></span> <span data-ttu-id="19e50-110">Si verifica un timeout se l'applicazione non richiede dati entro l'intervallo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="19e50-110">A time-out occurs if the application does not ask for data within the specified time.</span></span>  
  
 <span data-ttu-id="19e50-111">La destinazione DataReader include un input.</span><span class="sxs-lookup"><span data-stu-id="19e50-111">The DataReader destination has one input.</span></span> <span data-ttu-id="19e50-112">Non supporta un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="19e50-112">It does not support an error output.</span></span>  
  
 <span data-ttu-id="19e50-113">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="19e50-113">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="19e50-114">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="19e50-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="19e50-115">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="19e50-115">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="19e50-116">Proprietà personalizzate della destinazione DataReader</span><span class="sxs-lookup"><span data-stu-id="19e50-116">DataReader Destination Custom Properties</span></span>](datareader-destination-custom-properties.md)  
  
 <span data-ttu-id="19e50-117">Per altre informazioni su come impostare le proprietà, vedere [Impostazione delle proprietà di un componente del flusso di dati](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="19e50-117">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
