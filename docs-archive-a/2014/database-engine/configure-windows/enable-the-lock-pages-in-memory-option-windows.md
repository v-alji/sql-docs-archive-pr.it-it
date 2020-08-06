---
title: Abilitare l'opzione Blocco di pagine in memoria (Windows) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Lock Pages in Memory option
ms.assetid: cd581fbc-4747-439e-87f9-2f18e39c5bb9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 13290940c3a94a7ba79582d892a5e28670f24b29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628979"
---
# <a name="enable-the-lock-pages-in-memory-option-windows"></a><span data-ttu-id="9048b-102">Abilitazione dell'opzione Blocco di pagine in memoria (Windows)</span><span class="sxs-lookup"><span data-stu-id="9048b-102">Enable the Lock Pages in Memory Option (Windows)</span></span>
  <span data-ttu-id="9048b-103">Questi criteri di Windows determinano gli account autorizzati a usare un processo per mantenere i dati nella memoria fisica, impedendo al sistema di eseguire il paging dei dati nella memoria virtuale su disco.</span><span class="sxs-lookup"><span data-stu-id="9048b-103">This Windows policy determines which accounts can use a process to keep data in physical memory, preventing the system from paging the data to virtual memory on disk.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9048b-104">Bloccando le pagine in memoria è possibile migliorare le prestazioni nei casi in cui è previsto il paging della memoria su disco.</span><span class="sxs-lookup"><span data-stu-id="9048b-104">Locking pages in memory may boost performance when paging memory to disk is expected.</span></span>  
  
 <span data-ttu-id="9048b-105">Utilizzare lo strumento Criteri di gruppo di Windows (gpedit.msc) per abilitare questi criteri per l'account utilizzato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9048b-105">Use the Windows Group Policy tool (gpedit.msc) to enable this policy for the account used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9048b-106">Per modificare i criteri, è necessario essere un amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="9048b-106">You must be a system administrator to change this policy.</span></span>  
  
### <a name="to-enable-the-lock-pages-in-memory-option"></a><span data-ttu-id="9048b-107">Per abilitare l'opzione Blocco di pagine in memoria</span><span class="sxs-lookup"><span data-stu-id="9048b-107">To enable the lock pages in memory option</span></span>  
  
1.  <span data-ttu-id="9048b-108">Fare clic sul menu **Start** e scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="9048b-108">On the **Start** menu, click **Run**.</span></span> <span data-ttu-id="9048b-109">Nella casella **Apri** Digitare `gpedit.msc` .</span><span class="sxs-lookup"><span data-stu-id="9048b-109">In the **Open** box, type `gpedit.msc`.</span></span>  
  
2.  <span data-ttu-id="9048b-110">Nella console **Editor Criteri di gruppo locali** espandere **Configurazione computer**, quindi **Impostazioni di Windows**.</span><span class="sxs-lookup"><span data-stu-id="9048b-110">On the **Local Group Policy Editor** console, expand **Computer Configuration**, and then expand **Windows Settings**.</span></span>  
  
3.  <span data-ttu-id="9048b-111">Espandere **Impostazioni sicurezza**e quindi espandere **Criteri locali**.</span><span class="sxs-lookup"><span data-stu-id="9048b-111">Expand **Security Settings**, and then expand **Local Policies**.</span></span>  
  
4.  <span data-ttu-id="9048b-112">Selezionare la cartella **Assegnazione diritti utente** .</span><span class="sxs-lookup"><span data-stu-id="9048b-112">Select the **User Rights Assignment** folder.</span></span>  
  
     <span data-ttu-id="9048b-113">I criteri verranno visualizzati nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="9048b-113">The policies will be displayed in the details pane.</span></span>  
  
5.  <span data-ttu-id="9048b-114">Nel riquadro fare doppio clic su **Blocco di pagine in memoria**.</span><span class="sxs-lookup"><span data-stu-id="9048b-114">In the pane, double-click **Lock pages in memory**.</span></span>  
  
6.  <span data-ttu-id="9048b-115">Nella finestra di dialogo **Impostazioni di sicurezza locali - Blocco di pagine in memoria** fare clic su **Aggiungi utente o gruppo**.</span><span class="sxs-lookup"><span data-stu-id="9048b-115">In the **Local Security Setting - Lock pages in memory** dialog box, click **Add User or Group**.</span></span>  
  
7.  <span data-ttu-id="9048b-116">Nella finestra di dialogo **Selezione utenti, computer, account del servizio o gruppi** aggiungere un account con privilegi per l'esecuzione di sqlservr.exe.</span><span class="sxs-lookup"><span data-stu-id="9048b-116">In the **Select Users, Service Accounts, or Groups** dialog box, add an account with privileges to run sqlservr.exe.</span></span>  
  
8.  <span data-ttu-id="9048b-117">Effettuare la disconnessione e nuovamente l'accesso per rendere operativa questa modifica.</span><span class="sxs-lookup"><span data-stu-id="9048b-117">Log out and then log back in for this change to take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9048b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9048b-118">See Also</span></span>  
 [<span data-ttu-id="9048b-119">Opzioni di configurazione del server Server Memory</span><span class="sxs-lookup"><span data-stu-id="9048b-119">Server Memory Server Configuration Options</span></span>](server-memory-server-configuration-options.md)  
  
  
