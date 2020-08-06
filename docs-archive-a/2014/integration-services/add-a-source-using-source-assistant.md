---
title: Aggiungere un'origine tramite Assistente origine | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5e850b7c-4b89-42ad-b0a6-d63ac7cc9568
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b58b10508765580e0cffe9bd62099f3e2d69863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627967"
---
# <a name="add-a-source-using-source-assistant"></a><span data-ttu-id="da26f-102">Aggiunta di un'origine tramite Assistente origine</span><span class="sxs-lookup"><span data-stu-id="da26f-102">Add a Source using Source Assistant</span></span>
  <span data-ttu-id="da26f-103">Questo argomento illustra i passaggi necessari per aggiungere una nuova origine usando Assistente origine ed elenca le opzioni disponibili nella finestra di dialogo **Aggiungi nuova origine** che viene visualizzata quando si trascina Assistente origine in Progettazione SSIS.</span><span class="sxs-lookup"><span data-stu-id="da26f-103">This topic provides steps to add a new source using the Source Assistant and also lists the options that are available on the **Add New Source** dialog, which you will see when you drag-drop the Source Assistant to the SSIS Designer.</span></span>  
  
### <a name="to-use-source-assistant-to-add-a-source"></a><span data-ttu-id="da26f-104">Per utilizzare Assistente origine per aggiungere un'origine</span><span class="sxs-lookup"><span data-stu-id="da26f-104">To use Source Assistant to add a source</span></span>  
  
1.  <span data-ttu-id="da26f-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il pacchetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] a cui si vuole aggiungere un componente di origine.</span><span class="sxs-lookup"><span data-stu-id="da26f-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that you want to add a source component to.</span></span>  
  
2.  <span data-ttu-id="da26f-106">Trascinare il componente **Assistente origine** dalla casella degli strumenti di SSIS alla scheda **Flusso di dati** . Verrà visualizzata la finestra di dialogo **Aggiungi nuova origine** .</span><span class="sxs-lookup"><span data-stu-id="da26f-106">Drag the **Source Assistant** component from the SSIS Toolbox to the **Data Flow** tab. You should see the **Add New Source** dialog box.</span></span> <span data-ttu-id="da26f-107">Nella sezione successiva vengono forniti i dettagli relativi alle opzioni disponibili nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="da26f-107">The next section provides you details about the options available in the dialog box.</span></span>  
  
3.  <span data-ttu-id="da26f-108">Selezionare il tipo della destinazione nell'elenco **Tipi**.</span><span class="sxs-lookup"><span data-stu-id="da26f-108">Select the type of the destination in the **Types** list.</span></span>  
  
4.  <span data-ttu-id="da26f-109">Selezionare una gestione connessione esistente nell'elenco **Gestioni connessioni** oppure selezionare **\<New>** per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="da26f-109">Select an existing connection manager in the **Connection Managers** list or select **\<New>** to create a new connection manager.</span></span>  
  
5.  <span data-ttu-id="da26f-110">Se si seleziona una gestione connessione esistente, fare clic su **OK** per chiudere la finestra di dialogo **Aggiungi nuova destinazione**.</span><span class="sxs-lookup"><span data-stu-id="da26f-110">If you select an existing connection manager, click **OK** to close the **Add New Destination** dialog box.</span></span> <span data-ttu-id="da26f-111">La destinazione e le gestioni connessioni verranno aggiunte al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="da26f-111">You should see the destination and connection managers added to the data flow.</span></span>  
  
6.  <span data-ttu-id="da26f-112">Se si fa clic su **\<New>** per creare una nuova gestione connessione, verrà visualizzata la finestra di dialogo **Gestione connessione** in cui specificare i parametri per la connessione.</span><span class="sxs-lookup"><span data-stu-id="da26f-112">If you click **\<New>** to create a new connection manager, you should see a **Connection Manager** dialog box, which lets you specify parameters for the connection.</span></span> <span data-ttu-id="da26f-113">Dopo avere completato la creazione della nuova gestione connessione, la destinazione e la gestione connessione saranno visibili in Progettazione SSIS.</span><span class="sxs-lookup"><span data-stu-id="da26f-113">After you are done with creating the new connection manager, you will see the destination and the connection manager in SSIS Designer.</span></span>  
  
  
