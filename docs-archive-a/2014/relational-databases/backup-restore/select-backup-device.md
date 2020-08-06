---
title: Seleziona dispositivo di backup | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.selectbackupdevice.f1
ms.assetid: 7887c9fd-15ce-4cc8-b069-845c1d09088c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8a848f9188eec0ebb09931bca460b0389b9570ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721508"
---
# <a name="select-backup-device"></a><span data-ttu-id="622ce-102">Seleziona dispositivo di backup</span><span class="sxs-lookup"><span data-stu-id="622ce-102">Select Backup Device</span></span>
  <span data-ttu-id="622ce-103">Utilizzare la finestra di dialogo **Seleziona dispositivo di backup** per selezionare un dispositivo di backup logico per l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="622ce-103">Use the **Select Backup Device** dialog box to select a logical backup device for the restore operation.</span></span>  
  
 <span data-ttu-id="622ce-104">Un dispositivo di backup logico è un dispositivo logico definito dall'utente che corrisponde a un dispositivo fisico, un'unità nastro o un'unità disco, disponibile tramite il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="622ce-104">A logical backup device is a user-defined logical device that corresponds to a physical device, either a tape drive or a disk drive, that is provided by the operating system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="622ce-105">Se un backup utilizza più dispositivi di backup, è necessario che tutti corrispondano a un unico tipo di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="622ce-105">If a backup uses multiple backup devices, they all must correspond to a single type of device.</span></span>  
  
 <span data-ttu-id="622ce-106">**Per utilizzare SQL Server Management Studio per visualizzare il contenuto di un dispositivo di backup**</span><span class="sxs-lookup"><span data-stu-id="622ce-106">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="622ce-107">Visualizzare il contenuto di un nastro o di un file di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="622ce-107">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="622ce-108">Visualizzare le proprietà e il contenuto di un dispositivo di backup logico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="622ce-108">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="622ce-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="622ce-109">Options</span></span>  
 <span data-ttu-id="622ce-110">**Dispositivo di backup**</span><span class="sxs-lookup"><span data-stu-id="622ce-110">**Backup device**</span></span>  
 <span data-ttu-id="622ce-111">Nella casella di riepilogo selezionare il nome di un dispositivo di backup logico dal quale si desidera eseguire il ripristino.</span><span class="sxs-lookup"><span data-stu-id="622ce-111">In the list box, select the name of a logical backup device from which you want to restore.</span></span>  
  
 <span data-ttu-id="622ce-112">Per informazioni su come visualizzare il contenuto di un dispositivo di backup, vedere [Visualizzare le proprietà e il contenuto di un dispositivo di backup logico &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="622ce-112">For information about how to view the contents of a backup device, see [View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="622ce-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="622ce-113">Remarks</span></span>  
 <span data-ttu-id="622ce-114">Se nell'elenco non è visualizzato un dispositivo di backup logico contenente il backup di interesse, è possibile che il backup sia stato scritto direttamente su uno o più file o unità nastro.</span><span class="sxs-lookup"><span data-stu-id="622ce-114">If you do not see a logical backup device that contains the backup you are seeking on the list, the backup might have been written directly to one or more files or tape drives.</span></span> <span data-ttu-id="622ce-115">In questo caso, chiudere la finestra di dialogo **Seleziona dispositivo di backup** e selezionare **File** o **Nastro** nella casella di riepilogo **Supporti di backup** della finestra di dialogo **Seleziona backup** .</span><span class="sxs-lookup"><span data-stu-id="622ce-115">If this is the case, cancel the **Select Backup Device** dialog box; and in the **Specify Backup** dialog box, select **File** or **Tape** in the **Backup media** list box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="622ce-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="622ce-116">See Also</span></span>  
 [<span data-ttu-id="622ce-117">Dispositivi di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="622ce-117">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
