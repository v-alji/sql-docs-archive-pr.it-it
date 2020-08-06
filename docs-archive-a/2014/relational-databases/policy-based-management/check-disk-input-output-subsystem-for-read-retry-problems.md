---
title: Controllare il sottosistema di output di input del disco per i problemi di lettura dei tentativi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: cedf4097-5b73-4964-9935-74a101847019
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19809b1554e435600eb4eeae424bed17dc27bdbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711907"
---
# <a name="check-disk-input-output-subsystem-for-read-retry-problems"></a><span data-ttu-id="b2215-102">Verifica dei problemi relativi ai tentativi di lettura nel sottosistema di input/output del disco</span><span class="sxs-lookup"><span data-stu-id="b2215-102">Check Disk Input Output Subsystem for Read Retry Problems</span></span>
  <span data-ttu-id="b2215-103">Questa regola consente di controllare il messaggio di errore 825 di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="b2215-103">This rule checks the event log for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message 825.</span></span> <span data-ttu-id="b2215-104">Tale messaggio indica che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è stato in grado per di leggere dati dal disco al primo tentativo.</span><span class="sxs-lookup"><span data-stu-id="b2215-104">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was unable to read data from the disk on the first try.</span></span> <span data-ttu-id="b2215-105">Il messaggio indica un problema grave relativo al sottosistema di I/O del disco</span><span class="sxs-lookup"><span data-stu-id="b2215-105">This message indicates a major problem with the disk I/O subsystem.</span></span> <span data-ttu-id="b2215-106">Questo messaggio non indica attualmente un problema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2215-106">This message does not currently indicate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] problem.</span></span> <span data-ttu-id="b2215-107">Se non viene risolto, tuttavia, il problema del disco potrebbe provocare la perdita di dati o il danneggiamento del database.</span><span class="sxs-lookup"><span data-stu-id="b2215-107">However, the disk problem could cause data loss or database corruption if it is not resolved.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="b2215-108">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="b2215-108">Best Practices Recommendations</span></span>  
 <span data-ttu-id="b2215-109">Le azioni seguenti possono contribuire a individuare e risolvere il problema hardware sottostante:</span><span class="sxs-lookup"><span data-stu-id="b2215-109">The following actions might help you discover and resolve the underlying hardware problem:</span></span>  
  
-   <span data-ttu-id="b2215-110">Esaminare il log degli errori e il testo delle variabili di questo messaggio per individuare eventuali indizi che consentano di spiegare il problema.</span><span class="sxs-lookup"><span data-stu-id="b2215-110">Review the error log and the variable text in this message for clues that explain the problem.</span></span>  
  
-   <span data-ttu-id="b2215-111">Controllare il sistema di dischi.</span><span class="sxs-lookup"><span data-stu-id="b2215-111">Check the disk system.</span></span> <span data-ttu-id="b2215-112">Il problema potrebbe essere correlato ai dischi, ai controller dei dischi, alle schede di array o ai driver dei dischi.</span><span class="sxs-lookup"><span data-stu-id="b2215-112">The problem could be related to the disks, the disk controllers, array cards, or disk drivers.</span></span>  
  
-   <span data-ttu-id="b2215-113">Contattare il produttore dei dischi e richiedere le utilità più recenti per verificare lo stato del sistema di dischi.</span><span class="sxs-lookup"><span data-stu-id="b2215-113">Contact the disk manufacturer for the latest utilities for checking the status of the disk system.</span></span>  
  
-   <span data-ttu-id="b2215-114">Contattare il produttore dei dischi e richiedere gli ultimi aggiornamenti dei driver.</span><span class="sxs-lookup"><span data-stu-id="b2215-114">Contact the disk manufacturer for the latest driver updates.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="b2215-115">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="b2215-115">For More Information</span></span>  
 [<span data-ttu-id="b2215-116">MSSQLSERVER_825</span><span class="sxs-lookup"><span data-stu-id="b2215-116">MSSQLSERVER_825</span></span>](../errors-events/mssqlserver-825-database-engine-error.md)  
  
 <span data-ttu-id="b2215-117">[SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="b2215-117">[SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span></span>  
  
  
