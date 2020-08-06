---
title: Procedura di preparazione di SQL Server per CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a327fa18-58f4-4e69-bb87-44faf47e20ef
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fbd285faaa55a28ad82beb673fa783570809bd04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710987"
---
# <a name="how-to-prepare-sql-server-for-cdc"></a><span data-ttu-id="ad676-102">Procedura di preparazione di SQL Server per CDC</span><span class="sxs-lookup"><span data-stu-id="ad676-102">How to Prepare SQL Server for CDC</span></span>
  <span data-ttu-id="ad676-103">Il servizio Oracle CDC richiede che tutte le istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di destinazione contengano il database MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="ad676-103">The Oracle CDC service requires all target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances to contain the MSXDBCDC database.</span></span> <span data-ttu-id="ad676-104">Questo database viene creato utilizzando l'azione Prepare SQL Server in CDC Service Configuration Console. Questa attività viene effettuata una sola volta per ogni istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ad676-104">You create this database using the Prepare SQL Server action in the CDC Service Configuration Console.This task is done one time only for each target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="ad676-105">Di seguito viene illustrato come preparare un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per Change Data Capture Oracle utilizzando CDC Service Configuration Console.</span><span class="sxs-lookup"><span data-stu-id="ad676-105">The following describes how to prepare a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for Oracle Change Data Capture using the CDC Service Configuration Console.</span></span> <span data-ttu-id="ad676-106">Tramite questo processo viene creato il database MSXDBCDC e vengono definite le tabelle, le stored procedure e altri artefatti obbligatori.</span><span class="sxs-lookup"><span data-stu-id="ad676-106">This process creates the MSXDBCDC database and defines the required tables, stored procedures, and other required artifacts.</span></span>  
  
 <span data-ttu-id="ad676-107">La preparazione di SQL Server per Oracle CDC viene effettuata dall'amministratore del servizio Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="ad676-107">Preparing the SQL Server for Oracle CDC is done by the Oracle CDC Service Administrator.</span></span> <span data-ttu-id="ad676-108">Per ulteriori informazioni sul ruolo di amministratore del servizio CDC, vedere [ruoli utente per la Change Data Capture Service per Oracle di Attunity](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ad676-108">For more information about the CDC Service Administrator role, see [User Roles for Change Data Capture Service for Oracle by Attunity](user-roles.md).</span></span>  
  
### <a name="to-enable-sql-server-for-cdc"></a><span data-ttu-id="ad676-109">Per abilitare SQL Server per CDC</span><span class="sxs-lookup"><span data-stu-id="ad676-109">To enable SQL Server for CDC</span></span>  
  
1.  <span data-ttu-id="ad676-110">Dal menu **Start** , selezionare **CDC Service Configuration for Oracle**.</span><span class="sxs-lookup"><span data-stu-id="ad676-110">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="ad676-111">Dal riquadro sinistro selezionare **Local CDC Services** , quindi dal riquadro **Actions** fare clic su **Prepare SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ad676-111">From the left pane, select **Local CDC Services** then from the **Actions** pane, click **Prepare SQL Server**.</span></span>  
  
     <span data-ttu-id="ad676-112">È anche possibile fare clic con il pulsante destro del mouse su **Local CDC Services** e scegliere **Prepare SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ad676-112">You can also right-click **Local CDC Services** and select **Prepare SQL Server**.</span></span>  
  
3.  <span data-ttu-id="ad676-113">Immettere le informazioni obbligatorie nella finestra di dialogo Preparing SQL Server Instance for Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="ad676-113">Enter the required information in the Preparing SQL Server Instance for Oracle CDC dialog box.</span></span> <span data-ttu-id="ad676-114">Per informazioni sull'immissione delle informazioni obbligatorie in questa finestra di dialogo, vedere [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="ad676-114">For information on how to enter the required information into this dialog box, see [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span></span>  
  
     <span data-ttu-id="ad676-115">Per preparare l'istanza di SQL Server per Oracle CDC, l'account di accesso deve disporre di autorizzazioni di scrittura per il database MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="ad676-115">To Prepare the SQL Server instance for Oracle CDC, the login must have write permission to the MSXDBCDC database.</span></span> <span data-ttu-id="ad676-116">Immettere le credenziali per un account di accesso che dispone di autorizzazioni per il database MSXDBCDC, ad esempio un membro del ruolo `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="ad676-116">Enter the credentials for a login that has write permission to the MSXDBCDC database, such as a member of the `sysasmin` role.</span></span>  
  
 <span data-ttu-id="ad676-117">**Nota**: è possibile fare clic su **View Script** per visualizzare una versione di sola lettura dello script di impostazione.</span><span class="sxs-lookup"><span data-stu-id="ad676-117">**Note**: You can click **View Script** to view a read-only version of the setup script.</span></span> <span data-ttu-id="ad676-118">Se necessario, un amministratore di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] può copiare questo script nella console di gestione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per modificarlo ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="ad676-118">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator can copy this script into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Console to edit and execute it, if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad676-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad676-119">See Also</span></span>  
 [<span data-ttu-id="ad676-120">Preparare SQL Server per CDC</span><span class="sxs-lookup"><span data-stu-id="ad676-120">Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
