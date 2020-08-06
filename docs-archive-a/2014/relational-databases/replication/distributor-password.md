---
title: Password server di distribuzione | Microsoft Docs
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configuredistributionwizard.distributorpassword.f1
ms.assetid: 52787c5e-c9ef-440e-a000-0787111b7dbb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 63e635903793bfa63d12b8a4cd2985178f9c4837
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624626"
---
# <a name="distributor-password"></a><span data-ttu-id="268ad-102">Password server di distribuzione</span><span class="sxs-lookup"><span data-stu-id="268ad-102">Distributor Password</span></span>
  <span data-ttu-id="268ad-103">Se nella pagina **Server di pubblicazione** di questa procedura guidata uno più server di pubblicazione sono stati abilitati all'utilizzo del server corrente come server di distribuzione remoto, è necessario specificare una password per la connessione eseguita dalla replica tra il server di pubblicazione e il server di distribuzione remoto utilizzando l'account di accesso **distributor_admin** .</span><span class="sxs-lookup"><span data-stu-id="268ad-103">If, on the **Publishers** page of this wizard, you enabled one or more Publishers to use this server as a remote Distributor, you must specify a password for the connection replication makes between the Publisher and the remote Distributor using the **distributor_admin** login.</span></span> <span data-ttu-id="268ad-104">È necessario specificare la stessa password per ogni server di pubblicazione che utilizza questo server di distribuzione remoto nella pagina **Password amministrativa** della Creazione guidata nuova pubblicazione o della Configurazione guidata distribuzione.</span><span class="sxs-lookup"><span data-stu-id="268ad-104">The same password must be entered for each Publisher that uses this remote Distributor on the **Administrative Password** page of the New Publication Wizard or the Configure Distribution Wizard.</span></span> <span data-ttu-id="268ad-105">Per altre informazioni sulla sicurezza dei database di distribuzione, vedere [Proteggere il database di distribuzione](security/secure-the-distributor.md).</span><span class="sxs-lookup"><span data-stu-id="268ad-105">For more information on security for Distributors, see [Secure the Distributor](security/secure-the-distributor.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="268ad-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="268ad-106">Options</span></span>  
 <span data-ttu-id="268ad-107">**Password**</span><span class="sxs-lookup"><span data-stu-id="268ad-107">**Password**</span></span>  
 <span data-ttu-id="268ad-108">Consente di immettere una password complessa per la connessione tra il server di pubblicazione e il server di distribuzione remoto.</span><span class="sxs-lookup"><span data-stu-id="268ad-108">Enter a strong password for the connection between the Publisher and the remote Distributor.</span></span>  
  
 <span data-ttu-id="268ad-109">**Conferma password**</span><span class="sxs-lookup"><span data-stu-id="268ad-109">**Confirm Password**</span></span>  
 <span data-ttu-id="268ad-110">Consente di immettere nuovamente la password per verificarne la corretta immissione.</span><span class="sxs-lookup"><span data-stu-id="268ad-110">Re-enter the password to confirm it was entered correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="268ad-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="268ad-111">See Also</span></span>  
 <span data-ttu-id="268ad-112">[Configura distribuzione](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="268ad-112">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="268ad-113">Configurare la pubblicazione e la distribuzione</span><span class="sxs-lookup"><span data-stu-id="268ad-113">Configure Publishing and Distribution</span></span>](configure-publishing-and-distribution.md)  
  
  
