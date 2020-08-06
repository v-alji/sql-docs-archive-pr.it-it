---
title: Configurare WMI per mostrare lo stato del server in Strumenti SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- WMI Provider for Server Events, setting permissions
- WMI permissions [SQL Server]
ms.assetid: 7e97197b-ed4d-40d1-9a52-9ab1d92401d7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 138abbe2b7b819d6afd6da62135f7cd7ce86496f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722176"
---
# <a name="configure-wmi-to-show-server-status-in-sql-server-tools"></a><span data-ttu-id="eedd3-102">Configurazione di WMI per mostrare lo stato del server in Strumenti SQL Server</span><span class="sxs-lookup"><span data-stu-id="eedd3-102">Configure WMI to Show Server Status in SQL Server Tools</span></span>
  <span data-ttu-id="eedd3-103">In questo argomento viene descritto come configurare WMI per mostrare lo stato del server negli strumenti di SQL Server in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eedd3-103">This topic describes how to configure WMI to show the server status in SQL Server tools in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="eedd3-104">Durante la connessione ai server i componenti Server registrati e Esplora oggetti di [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], nonché Gestione configurazione [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , utilizzano Strumentazione gestione Windows (WMI) per ottenere lo stato dei servizi [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (MSSQLSERVER) e [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="eedd3-104">When connecting to servers, both the Registered Servers and Object Explorer components of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], as well as [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager, use Windows Management Instrumentation (WMI) to obtain the status of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (MSSQLSERVER) and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent (MSSQLSERVER) services.</span></span> <span data-ttu-id="eedd3-105">Per visualizzare lo stato del servizio, l'utente deve disporre dei diritti per accedere in remoto all'oggetto WMI.</span><span class="sxs-lookup"><span data-stu-id="eedd3-105">To display the status of the service, the user must have rights to remotely access the WMI object.</span></span> <span data-ttu-id="eedd3-106">Per configurare questa autorizzazione, nel server deve essere installato WMI.</span><span class="sxs-lookup"><span data-stu-id="eedd3-106">The server must have WMI installed to configure this permission.</span></span>  
  
##  <a name="to-configure-wmi-permission"></a><a name="SSMSProcedure"></a><span data-ttu-id="eedd3-107">Per configurare l'autorizzazione WMI</span><span class="sxs-lookup"><span data-stu-id="eedd3-107">To configure WMI permission</span></span>  
  
1.  <span data-ttu-id="eedd3-108">Scegliere **Esegui** dal menu **Start**nel server remoto.</span><span class="sxs-lookup"><span data-stu-id="eedd3-108">On the **Start** menu on the remote server, click **Run**.</span></span>  
  
2.  <span data-ttu-id="eedd3-109">Nella casella **Apri** Digitare `wmimgmt.msc` , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="eedd3-109">In the **Open** box type `wmimgmt.msc`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="eedd3-110">Nel programma **Windows Management Infrastructure** fare clic con il pulsante destro del mouse su **Controllo WMI (Locale)** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="eedd3-110">In the **Windows Management Infrastructure** program, right-click **WMI Control (Local)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="eedd3-111">Nella scheda **Sicurezza** della finestra di dialogo **Proprietà - Controllo WMI (Locale)** espandere **Radice**e fare clic su **CIMV2**.</span><span class="sxs-lookup"><span data-stu-id="eedd3-111">In the **WMI Control (Local) Properties** dialog box, on the **Security** tab, expand **Root**, and then click **CIMV2**.</span></span>  
  
5.  <span data-ttu-id="eedd3-112">Fare clic sul pulsante **Sicurezza** per aprire la finestra di dialogo **Sicurezza per ROOT\CIMV2** .</span><span class="sxs-lookup"><span data-stu-id="eedd3-112">Click **Security** to open the **Security for ROOT\CIMV2** dialog box.</span></span>  
  
6.  <span data-ttu-id="eedd3-113">Aggiungere un gruppo o un utente alla casella **Nomi utente o gruppo** e selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="eedd3-113">Add a group or user to the **Group or user names** box and select it.</span></span>  
  
7.  <span data-ttu-id="eedd3-114">Nella casella **Autorizzazioni per** _\<group or user>_ , selezionare la colonna **Consenti** per l'autorizzazione **Abilita remoto** relativa agli utenti per i quali si vuole rilevare in remoto lo stato del servizio.</span><span class="sxs-lookup"><span data-stu-id="eedd3-114">In the **Permissions for**_\<group or user>_ box, select the **Allow** column, for the **Remote Enable** permission, for users whom you wish to remotely detect the service status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eedd3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eedd3-115">See Also</span></span>  
 [<span data-ttu-id="eedd3-116">Avvio, arresto o sospensione del servizio SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="eedd3-116">Start, Stop, or Pause the SQL Server Agent Service</span></span>](agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  
  
