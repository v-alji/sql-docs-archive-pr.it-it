---
title: Replica su Internet | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Web publishing [SQL Server replication], about Web publishing
- Web publishing [SQL Server replication]
- Internet [SQL Server replication]
- Internet [SQL Server replication], publishing
ms.assetid: 04e7f4ed-e244-4bbe-ba12-09c33abea09e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 46c61f8a5383c87d46fa0dbda18876b43ffb7739
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624031"
---
# <a name="replication-over-the-internet"></a><span data-ttu-id="c3ea0-102">Replica su Internet</span><span class="sxs-lookup"><span data-stu-id="c3ea0-102">Replication over the Internet</span></span>
  <span data-ttu-id="c3ea0-103">La replica dei dati su Internet consente a utenti remoti e non connessi di accedere ai dati nel momento desiderato tramite una connessione a Internet.</span><span class="sxs-lookup"><span data-stu-id="c3ea0-103">Replicating data over the Internet allows remote, disconnected users to access data when they need it using a connection to the Internet.</span></span> <span data-ttu-id="c3ea0-104">È possibile replicare i dati su Internet utilizzando:</span><span class="sxs-lookup"><span data-stu-id="c3ea0-104">Replicate data over the Internet using:</span></span>  
  
-   <span data-ttu-id="c3ea0-105">Una rete privata virtuale (VPN).</span><span class="sxs-lookup"><span data-stu-id="c3ea0-105">A Virtual Private Network (VPN).</span></span> <span data-ttu-id="c3ea0-106">Per altre informazioni, vedere [Pubblicare i dati su Internet tramite VPN](publish-data-over-the-internet-using-vpn.md).</span><span class="sxs-lookup"><span data-stu-id="c3ea0-106">For more information, see [Publish Data over the Internet Using VPN](publish-data-over-the-internet-using-vpn.md).</span></span>  
  
-   <span data-ttu-id="c3ea0-107">L'opzione di sincronizzazione Web per la replica di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="c3ea0-107">The Web synchronization option for merge replication.</span></span> <span data-ttu-id="c3ea0-108">Per altre informazioni, vedere [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="c3ea0-108">For more information, see [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span></span>  
  
 <span data-ttu-id="c3ea0-109">Tutti i tipi di replica di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possono replicare i dati in una VPN, ma è consigliabile considerare la sincronizzazione Web se si usa la replica di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="c3ea0-109">All types of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication can replicate data over a VPN, but you should consider Web synchronization if you are using merge replication.</span></span>  
  
  
