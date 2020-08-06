---
title: Configurare il controllo accessi (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- audits [SQL Server], logins
- logins [SQL Server], auditing
ms.assetid: 16961116-57ac-4eef-8037-791b26ade548
author: stevestein
ms.author: sstein
ms.openlocfilehash: b7e05f6c254e098a67a5ce00435c009cd450af44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637560"
---
# <a name="configure-login-auditing-sql-server-management-studio"></a><span data-ttu-id="109e0-102">Configurazione del controllo accessi (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="109e0-102">Configure Login Auditing (SQL Server Management Studio)</span></span>
  <span data-ttu-id="109e0-103">In questo argomento viene descritto come configurare controllo di accesso in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] per eseguire il monitoraggio dell'attività di accesso del [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="109e0-103">This topic describes how to configure login auditing in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] to monitor [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] login activity.</span></span> <span data-ttu-id="109e0-104">È possibile configurare il controllo accessi per scrivere nel log degli errori quando si verificano gli eventi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="109e0-104">Login auditing can be configured to write to the error log on the following events.</span></span>  
  
-   <span data-ttu-id="109e0-105">Accessi non riusciti</span><span class="sxs-lookup"><span data-stu-id="109e0-105">Failed logins</span></span>  
  
-   <span data-ttu-id="109e0-106">Accessi riusciti</span><span class="sxs-lookup"><span data-stu-id="109e0-106">Successful logins</span></span>  
  
-   <span data-ttu-id="109e0-107">Accessi riusciti e non riusciti</span><span class="sxs-lookup"><span data-stu-id="109e0-107">Both failed and successful logins</span></span>  
  
 <span data-ttu-id="109e0-108">Per rendere effettiva questa opzione, è necessario riavviare [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="109e0-108">You must restart [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] before this option will take effect.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="109e0-109">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="109e0-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-login-auditing"></a><span data-ttu-id="109e0-110">Per configurare il controllo accessi</span><span class="sxs-lookup"><span data-stu-id="109e0-110">To configure login auditing</span></span>  
  
1.  <span data-ttu-id="109e0-111">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] tramite Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="109e0-111">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] with Object Explorer.</span></span>  
  
2.  <span data-ttu-id="109e0-112">In Esplora oggetti fare clic con il pulsante destro del mouse sul nome del server e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="109e0-112">In Object Explorer, right-click the server name, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="109e0-113">Nella pagina **Sicurezza** selezionare l'opzione desiderata in **Controllo accessi** e chiudere la pagina **Proprietà server** .</span><span class="sxs-lookup"><span data-stu-id="109e0-113">On the **Security** page, under **Login** auditing, click the desired option and close the **Server Properties** page.</span></span>  
  
4.  <span data-ttu-id="109e0-114">In Esplora oggetti fare clic con il pulsante destro del mouse sul nome del server e scegliere **Riavvia**.</span><span class="sxs-lookup"><span data-stu-id="109e0-114">In Object Explorer, right-click the server name, and then click **Restart**.</span></span>  
  
  
