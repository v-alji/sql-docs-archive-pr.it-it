---
title: CDC Instance Deployment Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8fa82822-ac99-48ef-a18d-f4f3a77105b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6deea884168c2329e312eeaa2be16c28a955cca3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724879"
---
# <a name="cdc-instance-deployment-script"></a><span data-ttu-id="7d399-102">CDC Instance Deployment Script</span><span class="sxs-lookup"><span data-stu-id="7d399-102">CDC Instance Deployment Script</span></span>
  <span data-ttu-id="7d399-103">Nella finestra di dialogo CDC Instance Deployment Script viene visualizzato lo script di distribuzione dell'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="7d399-103">The CDC Instance Deployment Script dialog box that displays the CDC instance deployment script.</span></span> <span data-ttu-id="7d399-104">Questo script può essere usato per ricreare il database CDC con tutti i relativi elementi in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] diversa.</span><span class="sxs-lookup"><span data-stu-id="7d399-104">This script can be used to re-create the CDC database with all of its artifacts on a different [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="7d399-105">Al completamento dello script di distribuzione, è necessario accertare le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d399-105">At the completion of the deployment script, you should make sure of the following:</span></span>  
  
-   <span data-ttu-id="7d399-106">Lo script di distribuzione presuppone che l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di destinazione sia stata preparata per Oracle CDC, tramite Oracle CDC Service Configuration Console o lo **script di preparazione** creato dal programma.</span><span class="sxs-lookup"><span data-stu-id="7d399-106">The deployment script assumes that the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance was prepared for Oracle CDC, by using the Oracle CDC Service Configuration Console or by using **prepare script** that program creates.</span></span>  
  
-   <span data-ttu-id="7d399-107">La parte dello script utilizzata per abilitare il database per CDC deve essere eseguita con il ruolo `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="7d399-107">The part of the script that is used to enable the database for CDC needs to be run by a `sysadmin`.</span></span>  
  
-   <span data-ttu-id="7d399-108">Nello script non viene memorizzata la password di log mining di Oracle.</span><span class="sxs-lookup"><span data-stu-id="7d399-108">The script does not preserve the Oracle log-mining password.</span></span> <span data-ttu-id="7d399-109">Questa operazione deve essere eseguita manualmente dopo l'esecuzione dello script e l'avvio del servizio CDC.</span><span class="sxs-lookup"><span data-stu-id="7d399-109">This needs to be set manually after the script is run and the Oracle CDC Service is started.</span></span>  
  
 <span data-ttu-id="7d399-110">Selezionare le opzioni seguenti nella finestra di dialogo **CDC Instance Deployment Script** .</span><span class="sxs-lookup"><span data-stu-id="7d399-110">Select the following options in the **CDC Instance Deployment Script** dialog box.</span></span>  
  
 <span data-ttu-id="7d399-111">**Save As**</span><span class="sxs-lookup"><span data-stu-id="7d399-111">**Save As**</span></span>  
 <span data-ttu-id="7d399-112">Tramite questa opzione è possibile salvare lo script in un file di testo nel percorso desiderato.</span><span class="sxs-lookup"><span data-stu-id="7d399-112">Saves the script in a text file that you can save in any location you want.</span></span> <span data-ttu-id="7d399-113">È possibile copiare il file con lo script in qualsiasi altro server si desideri eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="7d399-113">You can copy the file with the script to any other server to run it there.</span></span>  
  
 <span data-ttu-id="7d399-114">**Copia**</span><span class="sxs-lookup"><span data-stu-id="7d399-114">**Copy**</span></span>  
 <span data-ttu-id="7d399-115">Tramite questa opzione è possibile copiare lo script negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="7d399-115">Copies the script to the clipboard.</span></span> <span data-ttu-id="7d399-116">Sarà quindi possibile incollare lo script in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o in qualsiasi editor di testo per eseguirlo in un momento successivo.</span><span class="sxs-lookup"><span data-stu-id="7d399-116">You can then paste the script into the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any text editor to run the scripts later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d399-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d399-117">See Also</span></span>  
 [<span data-ttu-id="7d399-118">Preparare SQL Server per CDC</span><span class="sxs-lookup"><span data-stu-id="7d399-118">Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
