---
title: Configurare log degli errori di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.configurelogs.configureerrorlogs.f1
ms.assetid: 03f0d463-9b0b-4af9-a853-da936d75e5af
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8acc27150f42049384e2789ef83ae66a737da9bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638101"
---
# <a name="configure-sql-server-error-logs"></a><span data-ttu-id="d5f03-102">Configura log degli errori di SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5f03-102">Configure SQL Server Error Logs</span></span>
  <span data-ttu-id="d5f03-103">In questo argomento viene descritto come visualizzare o modificare la modalità di riciclo dei log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5f03-103">This topic describes how to view or modify the way [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error logs are recycled.</span></span>  
  
## <a name="to-open-the-configure-sql-server-error-logs-dialog-box"></a><span data-ttu-id="d5f03-104">Per aprire la finestra di dialogo Configura log degli errori di SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5f03-104">To open the Configure SQL Server Error Logs dialog box</span></span>  
  
1.  <span data-ttu-id="d5f03-105">In Esplora oggetti espandere l'istanza di SQL Server, espandere **Gestione**, fare clic con il pulsante destro del mouse su **Log di SQL Server**e quindi scegliere **Configura**.</span><span class="sxs-lookup"><span data-stu-id="d5f03-105">In Object Explorer, expand the instance of SQL Server, expand **Management**, right-click **SQL Server Logs**, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="d5f03-106">Nella finestra di dialogo **Configura log degli errori di SQL Server** , scegliere dalle opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d5f03-106">In the **Configure SQL Server Error Logs** dialog box, choose from the following options.</span></span>  
  
     <span data-ttu-id="d5f03-107">**Limita il numero di file di log degli errori creati prima di essere riciclati**</span><span class="sxs-lookup"><span data-stu-id="d5f03-107">**Limit the number of the error log files before they are recycled**</span></span>  
     <span data-ttu-id="d5f03-108">Selezionare questa opzione per limitare il numero di log degli errori creati prima di essere riciclati.</span><span class="sxs-lookup"><span data-stu-id="d5f03-108">Check to limit the number of error logs created before they are recycled.</span></span> <span data-ttu-id="d5f03-109">Ogni volta che viene avviata un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene creato un nuovo log degli errori.</span><span class="sxs-lookup"><span data-stu-id="d5f03-109">A new error log is created each time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d5f03-110">mantiene backup dei sei log precedenti, a meno che non si selezioni questa opzione e non si specifichi un diverso numero massimo di log degli errori tramite l'opzione seguente.</span><span class="sxs-lookup"><span data-stu-id="d5f03-110">retains backups of the previous six logs, unless you check this option, and specify a different maximum number of error log files below.</span></span>  
  
     <span data-ttu-id="d5f03-111">**Numero massimo di file di log degli errori**</span><span class="sxs-lookup"><span data-stu-id="d5f03-111">**Maximum number of error log files**</span></span>  
     <span data-ttu-id="d5f03-112">Consente di specificare il numero massimo di log degli errori creati prima di essere riciclati.</span><span class="sxs-lookup"><span data-stu-id="d5f03-112">Specify the maximum number of error log files created before they are recycled.</span></span> <span data-ttu-id="d5f03-113">Il valore predefinito è 6 che corrisponde al numero di log di backup precedenti mantenuti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prima che vengano riciclati.</span><span class="sxs-lookup"><span data-stu-id="d5f03-113">The default is 6, which is the number of previous backup logs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retains before recycling them.</span></span>  
  
  
