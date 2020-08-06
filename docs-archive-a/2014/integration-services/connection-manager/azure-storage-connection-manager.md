---
title: Gestione connessione dell'archiviazione di Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpstorageconn.f1
- sql11.dts.designer.afpstorageconn.f1
ms.assetid: 68bd1d04-d20f-4357-a34e-7c9c76457062
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 47580d8d1d961df9fbcbed0bd7164f1c54792b86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628934"
---
# <a name="azure-storage-connection-manager"></a><span data-ttu-id="ae957-102">Gestione connessione dell'archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="ae957-102">Azure Storage Connection Manager</span></span>
  <span data-ttu-id="ae957-103">Il componente Gestione connessione dell'archiviazione di Azure consente di connettere un pacchetto SSIS a un account di archiviazione di Azure usando i valori specificati per le proprietà: Nome dell'account di archiviazione e Chiave dell'account.</span><span class="sxs-lookup"><span data-stu-id="ae957-103">The Azure Storage connection manager enables an SSIS package to connect to an Azure Storage account by using the values you specify for the properties: Storage Account Name and Account Key.</span></span>  
  
1.  <span data-ttu-id="ae957-104">Nella finestra di dialogo **Aggiungi gestione connessione SSIS** selezionare **Sottoscrizione di Azure**, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ae957-104">In the **Add SSIS Connection Manager** dialog box, select **AzureStorage**, and click **Add**.</span></span>  
  
2.  <span data-ttu-id="ae957-105">Nella finestra di dialogo Editor gestione connessione di archiviazione di Azure, scegliere **Usa account Azure** per connettersi a un servizio di archiviazione di Azure con Internet o scegliere **Usa account per sviluppatore locale** per connettersi al servizio locale ospitato dall'emulatore di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="ae957-105">In the Azure Storage Connection Manager Editor dialog box, choose **Use Azure account** to connect to an Azure Storage Service via internet or choose **Use local developer account** to connect to the local service hosted by the Azure Storage Emulator.</span></span>  
  
3.  <span data-ttu-id="ae957-106">Se si seleziona l'opzione **Usa account Azure** , eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="ae957-106">If you selected **Use Azure account** option, do the following:</span></span>  
  
    1.  <span data-ttu-id="ae957-107">Specificare i valori per i campi **Nome dell'account di archiviazione** e **Chiave dell'account** .</span><span class="sxs-lookup"><span data-stu-id="ae957-107">Specify values for the **Storage account name** and **Account key** field.</span></span> <span data-ttu-id="ae957-108">Questi valori vengono archiviati come dati sensibili nel pacchetto SSIS.</span><span class="sxs-lookup"><span data-stu-id="ae957-108">These values will be stored as sensitive data in SSIS package.</span></span>  
  
    2.  <span data-ttu-id="ae957-109">Selezionare **Usa HTTPS** per usare HTTPS anziché HTTP per connettersi al servizio di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="ae957-109">Select **Use HTTPS** if you want to use HTTPS instead of HTTP to connect to the Azure Storage Service.</span></span>  
  
4.  <span data-ttu-id="ae957-110">Scegliere **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="ae957-110">Click **OK** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="ae957-111">È possibile visualizzare le proprietà del componente Gestione connessione create nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="ae957-111">You can see the properties of the connection manager you created in the **Properties** window.</span></span>  
  
  
