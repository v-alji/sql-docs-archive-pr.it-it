---
title: Connettersi a un'origine dati (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.conndatasource.f1
ms.assetid: 1e2b17e9-092b-4af1-8a58-c52b8fe10ff1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4fe7f7d5b31118369b8ce2a855b955e44f661dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625734"
---
# <a name="connect-to-a-data-source-ssas"></a><span data-ttu-id="438fb-102">Connessione a un'origine dati (SSAS)</span><span class="sxs-lookup"><span data-stu-id="438fb-102">Connect to a Data Source (SSAS)</span></span>
  <span data-ttu-id="438fb-103">Questa pagina dell' **Importazione guidata tabella** consente di creare una nuova connessione a diverse origini dati, ad esempio database relazionali, feed di dati e file.</span><span class="sxs-lookup"><span data-stu-id="438fb-103">This page of the **Table Import Wizard** enables you to create a new data source connection to a variety of data sources, such as relational databases, data feeds, and files.</span></span> <span data-ttu-id="438fb-104">Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="438fb-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="438fb-105">Per connettersi a un'origine dati, è necessario che nel computer sia installato il provider appropriato.</span><span class="sxs-lookup"><span data-stu-id="438fb-105">To connect to a data source, you must have the appropriate provider installed on your machine.</span></span> <span data-ttu-id="438fb-106">È necessario che sia installato anche il provider appropriato sul server di database dell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="438fb-106">You must also have the appropriate provider installed on the workspace database server.</span></span> <span data-ttu-id="438fb-107">Per i server a 32 bit (x86), devono essere installati provider a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="438fb-107">For 32-bit (x86) servers, 32-bit providers must be installed.</span></span> <span data-ttu-id="438fb-108">Per i server a 64 bit (x64), devono essere installati provider a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="438fb-108">For 64-bit (x64) servers, 64-bit providers must be installed.</span></span>  
  
 [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] <span data-ttu-id="438fb-109">è sempre in esecuzione in un processo a 32 bit, indipendentemente dall'architettura.</span><span class="sxs-lookup"><span data-stu-id="438fb-109">always runs in a 32-bit process, regardless of architecture.</span></span> <span data-ttu-id="438fb-110">Quando si esegue [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] su un computer a 64 bit, è necessario tenere presente quanto indicato di seguito in caso di installazione di provider di dati:</span><span class="sxs-lookup"><span data-stu-id="438fb-110">When running [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] on a 64-bit machine, you should be aware of the following when installing data providers:</span></span>  
  
-   <span data-ttu-id="438fb-111">Per provider che supportano l'installazione side-by-side di provider a 32 e a 64 bit, è necessario installare entrambi i provider.</span><span class="sxs-lookup"><span data-stu-id="438fb-111">For providers that support side-by-side installation of 32-bit and 64-bit providers, you should install both providers.</span></span>  
  
-   <span data-ttu-id="438fb-112">Per il provider ACE, è necessario installare la versione a 64 bit del provider.</span><span class="sxs-lookup"><span data-stu-id="438fb-112">For the ACE provider, you must install the 64-bit version of the provider.</span></span> <span data-ttu-id="438fb-113">Poiché tramite Office viene installato automaticamente il provider ACE, non è necessario eseguire una versione a 32 bit di Microsoft Office su un computer a 64 bit in cui viene ospitato il server di database dell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="438fb-113">Because Office automatically installs the ACE provider, you should not run a 32-bit version of Microsoft Office on a 64-bit machine hosting the workspace database server.</span></span>  
  
     <span data-ttu-id="438fb-114">Il provider ACE viene utilizzato per importazioni da file di testo, di Excel e di Access.</span><span class="sxs-lookup"><span data-stu-id="438fb-114">The ACE provider is used to import from Text, Excel, and Access files.</span></span> <span data-ttu-id="438fb-115">Se il supporto per queste origini dati non è necessario, è possibile eseguire quindi una versione a 32 bit di Microsoft Office su un computer che esegue un server di database dell'area di lavoro a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="438fb-115">If support for these data sources is not needed, you can then run a 32-bit version of Microsoft Office on a machine running a 64-bit workspace database server.</span></span>  
  
-   <span data-ttu-id="438fb-116">Per altri provider che non supportano l'installazione side-by-side di provider a 32 e a 64 bit, è necessario installare il provider a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="438fb-116">For other providers that do not support side-by-side installation of 32-bit and 64-bit providers, you must install the 32-bit provider.</span></span> <span data-ttu-id="438fb-117">Se sono disponibili solo computer a 64 bit, è necessario utilizzare un computer remoto con un provider a 64 bit installato come server di database dell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="438fb-117">If only 64-bit machines are available, you must use a remote machine with a 64-bit provider installed as the workspace database server.</span></span>  
  
  
