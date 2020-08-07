---
title: Server di pubblicazione | Microsoft Docs
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configuredistributionwizard.enablepublishers.f1
ms.assetid: 116cd6a5-32ac-4273-81a2-d184408e0f07
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 879fa3cc2ecadf56914928c6ae83600f513f6ddb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623142"
---
# <a name="publishers"></a><span data-ttu-id="785d3-102">Autori</span><span class="sxs-lookup"><span data-stu-id="785d3-102">Publishers</span></span>
  <span data-ttu-id="785d3-103">È possibile concedere ad altri server di pubblicazione l'autorizzazione per l'utilizzo del server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="785d3-103">You can give permission for other Publishers to use this Distributor.</span></span> <span data-ttu-id="785d3-104">Tenere presente che, se si abilita un server di pubblicazione per l'utilizzo di questo server come server di distribuzione remoto, il server non diventerà un server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="785d3-104">Be aware that enabling a Publisher to use this server as its remote Distributor does not make that server a Publisher.</span></span> <span data-ttu-id="785d3-105">È infatti necessario connettersi al server di pubblicazione, configurarlo per la pubblicazione e selezionare questo server come server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="785d3-105">You must connect to the Publisher, configure it for publishing, and choose this server as the Distributor.</span></span> <span data-ttu-id="785d3-106">Utilizzando la Creazione guidata nuova pubblicazione è possibile configurare il server di pubblicazione e selezionare un server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="785d3-106">You can configure the Publisher and choose a Distributor through the New Publication Wizard.</span></span>  
  
 <span data-ttu-id="785d3-107">I server selezionati come server di pubblicazione utilizzeranno il database di distribuzione specificato nella pagina **Database di distribuzione** della creazione guidata.</span><span class="sxs-lookup"><span data-stu-id="785d3-107">The servers you select as Publishers will use the distribution database specified on the **Distribution Database** page of this wizard.</span></span> <span data-ttu-id="785d3-108">Se si desidera utilizzare un database di distribuzione diverso, non abilitare il server di pubblicazione in questa fase.</span><span class="sxs-lookup"><span data-stu-id="785d3-108">If you want to use a different distribution database, do not enable the Publisher at this time.</span></span> <span data-ttu-id="785d3-109">Utilizzare invece la finestra di dialogo **Proprietà server di distribuzione** per aggiungere i server di pubblicazione dopo aver completato la Configurazione guidata distribuzione.</span><span class="sxs-lookup"><span data-stu-id="785d3-109">Instead, use the **Distributor Properties** dialog box to add Publishers after you complete the Configure Distribution Wizard.</span></span>  
  
## <a name="options"></a><span data-ttu-id="785d3-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="785d3-110">Options</span></span>  
 <span data-ttu-id="785d3-111">**Server di pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="785d3-111">**Publishers**</span></span>  
 <span data-ttu-id="785d3-112">Consente di selezionare i server autorizzati all'utilizzo del server di distribuzione corrente.</span><span class="sxs-lookup"><span data-stu-id="785d3-112">Select the servers that are allowed to use this Distributor.</span></span> <span data-ttu-id="785d3-113">Fare clic sul pulsante delle proprietà ( **...** ) accanto al server di pubblicazione per visualizzare e impostare proprietà aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="785d3-113">Click the properties button (**...**) next to a Publisher to view and set additional properties.</span></span>  
  
 <span data-ttu-id="785d3-114">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="785d3-114">**Add**</span></span>  
 <span data-ttu-id="785d3-115">Se il server desiderato non è incluso nell'elenco, fare clic su **Aggiungi** per aggiungere un server di pubblicazione [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o Oracle all'elenco dei server di pubblicazione disponibili.</span><span class="sxs-lookup"><span data-stu-id="785d3-115">If the server you want to allow is not listed, click **Add** to add a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher or Oracle Publisher to the list of available Publishers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="785d3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="785d3-116">See Also</span></span>  
 <span data-ttu-id="785d3-117">[Configura distribuzione](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="785d3-117">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="785d3-118">[Configurare la pubblicazione e la distribuzione](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="785d3-118">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="785d3-119">[Visualizzare e modificare le proprietà del server di pubblicazione e del database di distribuzione](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="785d3-119">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 [<span data-ttu-id="785d3-120">Creare una pubblicazione</span><span class="sxs-lookup"><span data-stu-id="785d3-120">Create a Publication</span></span>](publish/create-a-publication.md)  
  
  
