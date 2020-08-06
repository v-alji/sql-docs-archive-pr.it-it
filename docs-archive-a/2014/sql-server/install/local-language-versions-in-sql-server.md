---
title: Versioni in lingua locale di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 20b99363-0490-4aa3-9a3d-262f827d81e8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 646ffaed1e4b709c2c26030379f0a7f223f221e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713716"
---
# <a name="local-language-versions-in-sql-server"></a><span data-ttu-id="7cc83-102">Versioni in lingua locale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="7cc83-102">Local Language Versions in SQL Server</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7cc83-103">supporta tutte le lingue supportate dai sistemi operativi di Windows.</span><span class="sxs-lookup"><span data-stu-id="7cc83-103">supports all languages that are supported by Windows operating systems.</span></span>  
  
## <a name="cross-language-support"></a><span data-ttu-id="7cc83-104">Supporto di lingue diverse</span><span class="sxs-lookup"><span data-stu-id="7cc83-104">Cross-Language Support</span></span>  
  
-   <span data-ttu-id="7cc83-105">La versione in lingua inglese di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è supportata in tutte le versioni localizzate dei sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="7cc83-105">The English-language version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is supported on all localized versions of operating systems.</span></span>  
  
-   <span data-ttu-id="7cc83-106">Le versioni localizzate di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono supportate nei sistemi operativi localizzati nella lingua corrispondente o nelle versioni in lingua inglese dei sistemi operativi supportati tramite l'utilizzo delle impostazioni di Windows Multilingual User Interface Pack (MUI).</span><span class="sxs-lookup"><span data-stu-id="7cc83-106">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are supported on localized operating systems with the corresponding language or on English-language versions of supported operating systems by using the Windows Multilingual User Interface Pack (MUI) settings.</span></span> <span data-ttu-id="7cc83-107">Per altre informazioni, vedere [Configure Operating System to Support Localized Versions](../../../2014/sql-server/install/local-language-versions-in-sql-server.md#BK_ConfigureOS).</span><span class="sxs-lookup"><span data-stu-id="7cc83-107">For more information, see [Configure Operating System to Support Localized Versions](../../../2014/sql-server/install/local-language-versions-in-sql-server.md#BK_ConfigureOS).</span></span>  
  
-   <span data-ttu-id="7cc83-108">Solo le versioni localizzate di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possono essere aggiornate alle versioni localizzate nella stessa lingua e non possono essere aggiornate alla versione in lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="7cc83-108">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can only be upgraded to localized versions of the same language, and cannot be upgraded to the English-language version.</span></span>  
  
-   <span data-ttu-id="7cc83-109">Le versioni localizzate di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possono anche essere installate side-by-side alle istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]in lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="7cc83-109">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can also be installed side by side with English-language instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="configure-operating-system-to-support-localized-versions"></a><a name="BK_ConfigureOS"></a> <span data-ttu-id="7cc83-110">Configure Operating System to Support Localized Versions</span><span class="sxs-lookup"><span data-stu-id="7cc83-110">Configure Operating System to Support Localized Versions</span></span>  
 <span data-ttu-id="7cc83-111">Grazie all'utilizzo delle impostazioni MUI (Multilingual User Interface Pack) di Windows, le versioni localizzate di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono supportate nelle versioni in lingua inglese dei sistemi operativi supportati.</span><span class="sxs-lookup"><span data-stu-id="7cc83-111">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are supported on English-language versions of supported operating systems through the use of Windows Multilingual User Interface Pack (MUI) settings.</span></span>  
  
 <span data-ttu-id="7cc83-112">Tuttavia, prima di installare una versione localizzata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un server in cui viene eseguito un sistema operativo in lingua inglese con un'impostazione MUI non in lingua inglese, è necessario verificare alcune impostazioni del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7cc83-112">However, you must verify certain operating system settings before installing a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a server that is running an English-language operating system with a non-English MUI setting.</span></span> <span data-ttu-id="7cc83-113">È necessario innanzitutto controllare che le impostazioni del sistema operativo riportate di seguito corrispondano alla lingua della versione localizzata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da installare:</span><span class="sxs-lookup"><span data-stu-id="7cc83-113">You need to verify that the following operating system settings match the language of the localized [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be installed:</span></span>  
  
-   <span data-ttu-id="7cc83-114">Impostazione dell'interfaccia utente del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7cc83-114">The operating system user interface setting</span></span>  
  
-   <span data-ttu-id="7cc83-115">Impostazioni locali dell'utente nel sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7cc83-115">The operating system user locale setting</span></span>  
  
-   <span data-ttu-id="7cc83-116">Impostazioni locali del sistema</span><span class="sxs-lookup"><span data-stu-id="7cc83-116">The system locale setting</span></span>  
  
 <span data-ttu-id="7cc83-117">Se le impostazioni non corrispondono alla lingua della versione localizzata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da installare, sarà necessario utilizzare le procedure seguenti per configurare correttamente le impostazioni del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7cc83-117">If the settings do not match the language of the localized [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be installed, then use the following procedures to correctly set these operating system settings.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="7cc83-118">NON sono supportate installazioni di versioni localizzate diverse delle istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="7cc83-118">Installations of different language versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances on the same computer are not supported.</span></span>  
  
#### <a name="to-change-the-operating-system-user-interface-setting"></a><span data-ttu-id="7cc83-119">Per modificare le impostazioni dell'interfaccia utente del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7cc83-119">To change the operating system user interface setting</span></span>  
  
1.  <span data-ttu-id="7cc83-120">Se non è stato già fatto, installare l'interfaccia MUI del sistema operativo che corrisponde alla versione localizzata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cc83-120">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="7cc83-121">Nel Pannello di controllo aprire **Opzioni internazionali e della lingua**.</span><span class="sxs-lookup"><span data-stu-id="7cc83-121">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="7cc83-122">Nella scheda **Lingue** , in **Lingua utilizzata nei menu e nelle finestre di dialogo**selezionare un valore nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7cc83-122">On the **Languages** tab, for **Language used in menus and dialogs**, select a value from the list.</span></span>  
  
     <span data-ttu-id="7cc83-123">Questa impostazione avrà effetto sulla lingua dell'interfaccia utente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], pertanto deve corrispondere alla versione localizzata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cc83-123">This setting will affect the user interface language of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], so it must match your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="7cc83-124">Fare clic su **Applica** per confermare la modifica e quindi su **OK** per chiudere la finestra.</span><span class="sxs-lookup"><span data-stu-id="7cc83-124">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
#### <a name="to-change-the-operating-system-user-locale-setting"></a><span data-ttu-id="7cc83-125">Per modificare le impostazioni locali dell'utente del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="7cc83-125">To change the operating system user locale setting</span></span>  
  
1.  <span data-ttu-id="7cc83-126">Se non è stato già fatto, installare l'interfaccia MUI del sistema operativo che corrisponde alla versione localizzata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cc83-126">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="7cc83-127">Nel Pannello di controllo aprire **Opzioni internazionali e della lingua**.</span><span class="sxs-lookup"><span data-stu-id="7cc83-127">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="7cc83-128">Nella scheda **Opzioni internazionali** , in **Selezionare l'elemento corrispondente alle preferenze**selezionare un valore nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7cc83-128">On the **Regional Options** tab, for **Select an item to match its preferences**, select a value from the list.</span></span>  
  
     <span data-ttu-id="7cc83-129">Questa impostazione avrà effetto sulla formattazione dei dati specifici della lingua.</span><span class="sxs-lookup"><span data-stu-id="7cc83-129">This setting will affect culture-specific data formatting.</span></span>  
  
4.  <span data-ttu-id="7cc83-130">Fare clic su **Applica** per confermare la modifica e quindi su **OK** per chiudere la finestra.</span><span class="sxs-lookup"><span data-stu-id="7cc83-130">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
#### <a name="to-change-the-system-locale-setting"></a><span data-ttu-id="7cc83-131">Per modificare le impostazioni locali del sistema</span><span class="sxs-lookup"><span data-stu-id="7cc83-131">To change the system locale setting</span></span>  
  
1.  <span data-ttu-id="7cc83-132">Se non è stato già fatto, installare l'interfaccia MUI del sistema operativo che corrisponde alla versione localizzata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cc83-132">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="7cc83-133">Nel Pannello di controllo aprire **Opzioni internazionali e della lingua**.</span><span class="sxs-lookup"><span data-stu-id="7cc83-133">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="7cc83-134">Nella scheda **Avanzate** , in **Selezionare una lingua per i programmi non Unicode da utilizzare**selezionare un valore nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7cc83-134">On the **Advanced** tab, for **Select a language to match the language version of the non-Unicode programs you want to use**, select a value from the list.</span></span>  
  
     <span data-ttu-id="7cc83-135">Mediante questa impostazione, nel programma di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verranno selezionate le regole di confronto predefinite ottimali per l'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7cc83-135">This setting will allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to choose the best default collation for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span>  
  
4.  <span data-ttu-id="7cc83-136">Fare clic su **Applica** per confermare la modifica e quindi su **OK** per chiudere la finestra.</span><span class="sxs-lookup"><span data-stu-id="7cc83-136">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cc83-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cc83-137">See Also</span></span>  
 <span data-ttu-id="7cc83-138">[Requisiti hardware e software per l'installazione di SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7cc83-138">[Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md) </span></span>  
 [<span data-ttu-id="7cc83-139">Installare SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="7cc83-139">Install SQL Server 2014</span></span>](../../database-engine/install-windows/install-sql-server.md)  
  
  
