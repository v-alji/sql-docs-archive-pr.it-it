---
title: Cartella snapshot | Microsoft Docs
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replicationutilities.specifysnapshotfolder.f1
ms.assetid: 3eb1b73f-ddb3-4d09-be6e-811c414698e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 48b490c65662edf65018e98dd1bc3339f6aae6b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637747"
---
# <a name="snapshot-folder"></a><span data-ttu-id="b5228-102">Cartella snapshot</span><span class="sxs-lookup"><span data-stu-id="b5228-102">Snapshot Folder</span></span>
  <span data-ttu-id="b5228-103">La pagina **Cartella snapshot** viene visualizzata nella Configurazione guidata distribuzione e nella Creazione guidata nuova pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="b5228-103">The **Snapshot Folder** page appears in the Configure Distribution Wizard and in the New Publication Wizard.</span></span> <span data-ttu-id="b5228-104">Il percorso specificato per la cartella snapshot verrà utilizzato come percorso predefinito per tutti i server di pubblicazione abilitati nella procedura guidata. La cartella snapshot predefinita non si applica ai server di pubblicazione abilitati successivamente tramite la finestra di dialogo **Proprietà server di distribuzione** .</span><span class="sxs-lookup"><span data-stu-id="b5228-104">The location you specify for the snapshot folder will be used as the default for all Publishers enabled in this wizard (the default snapshot folder does not apply to Publishers that are later enabled using the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="b5228-105">Questa impostazione predefinita può essere sostituita per qualsiasi server di pubblicazione nella pagina **Server di pubblicazione** della Configurazione guidata distribuzione o della finestra di dialogo **Proprietà server di distribuzione** .</span><span class="sxs-lookup"><span data-stu-id="b5228-105">You can override this default for any Publisher on the **Publishers** page of the Configure Distribution Wizard or the **Distributor Properties** dialog box.</span></span>  
  
 <span data-ttu-id="b5228-106">La cartella snapshot è semplicemente una directory designata come condivisione. Gli agenti che eseguono letture e scritture in questa cartella devono disporre di autorizzazioni sufficienti per accedervi.</span><span class="sxs-lookup"><span data-stu-id="b5228-106">The snapshot folder is simply a directory that you have designated as a share; agents that read from and write to this folder must have sufficient permissions to access it.</span></span> <span data-ttu-id="b5228-107">Per altre informazioni sulle impostazioni di sicurezza appropriate per la cartella, vedere [Proteggere la cartella snapshot](security/secure-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="b5228-107">For more information about securing the folder appropriately, see [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md).</span></span> <span data-ttu-id="b5228-108">Prima di implementare la replica è necessario verificare che gli agenti di replica possano connettersi alla cartella snapshot.</span><span class="sxs-lookup"><span data-stu-id="b5228-108">Prior to implementing replication, test that the replication agents will be able to connect to the snapshot folder.</span></span> <span data-ttu-id="b5228-109">Accedere con l'account che verrà utilizzato da ogni agente e quindi tentare di accedere alla cartella snapshot.</span><span class="sxs-lookup"><span data-stu-id="b5228-109">Log on under the account that will be used by each agent and then attempt to access the snapshot folder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b5228-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b5228-110">Options</span></span>  
 <span data-ttu-id="b5228-111">**Cartella snapshot**</span><span class="sxs-lookup"><span data-stu-id="b5228-111">**Snapshot folder**</span></span>  
 <span data-ttu-id="b5228-112">Consente di immettere il percorso della cartella in cui archiviare i file di snapshot.</span><span class="sxs-lookup"><span data-stu-id="b5228-112">Enter the path for the folder where you want snapshot files stored.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="b5228-113">consiglia di usare una condivisione di rete come percorso della cartella snapshot.</span><span class="sxs-lookup"><span data-stu-id="b5228-113">recommends that you use a network share as a snapshot folder location.</span></span> <span data-ttu-id="b5228-114">I percorsi locali, ovvero quelli che iniziano con una lettera di unità, ad esempio C:\\, non sono accessibili agli agenti in altri computer.</span><span class="sxs-lookup"><span data-stu-id="b5228-114">Local paths (those starting with a drive letter, such as C:\\) are not accessible to agents on other computers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5228-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5228-115">See Also</span></span>  
 <span data-ttu-id="b5228-116">[Percorsi alternativi cartella snapshot](alternate-snapshot-folder-locations.md) </span><span class="sxs-lookup"><span data-stu-id="b5228-116">[Alternate Snapshot Folder Locations](alternate-snapshot-folder-locations.md) </span></span>  
 <span data-ttu-id="b5228-117">[Configura distribuzione](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="b5228-117">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="b5228-118">[Configurare la pubblicazione e la distribuzione](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="b5228-118">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="b5228-119">[Visualizzare e modificare le proprietà del server di pubblicazione e del database di distribuzione](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b5228-119">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 [<span data-ttu-id="b5228-120">Inizializzare una sottoscrizione con uno snapshot</span><span class="sxs-lookup"><span data-stu-id="b5228-120">Initialize a Subscription with a Snapshot</span></span>](initialize-a-subscription-with-a-snapshot.md)  
  
  
