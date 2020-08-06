---
title: Abilitare un server di pubblicazione remoto in un database di distribuzione (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- remote Distributors [SQL Server replication]
- Publishers [SQL Server replication]
ms.assetid: 6f8e2831-5c45-4e39-8e51-d37e2813cf3d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 06c85924731b79e8b3c79cfbcc354b5bedf69b62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624612"
---
# <a name="enable-a-remote-publisher-at-a-distributor-sql-server-management-studio"></a><span data-ttu-id="29cef-102">Abilitazione di un server di pubblicazione remoto in un database di distribuzione (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="29cef-102">Enable a Remote Publisher at a Distributor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="29cef-103">Attivare un server di pubblicazione per l'utilizzo di un server di distribuzione remoto nella pagina **Server di pubblicazione** .</span><span class="sxs-lookup"><span data-stu-id="29cef-103">Enable a Publisher to use a remote Distributor on the **Publishers** page.</span></span> <span data-ttu-id="29cef-104">Tale pagina è disponibile nella Configurazione guidata distribuzione e nella finestra di dialogo **Proprietà database di distribuzione - \<Distributor>** .</span><span class="sxs-lookup"><span data-stu-id="29cef-104">This page is available in the Configure Distribution Wizard and the **Distributor Properties - \<Distributor>** dialog box.</span></span> <span data-ttu-id="29cef-105">Per altre informazioni sull'uso della creazione guidata e l'accesso alla finestra di dialogo, vedere [Configurare la pubblicazione e la distribuzione](configure-publishing-and-distribution.md) e [Visualizzare e modificare le proprietà del server di pubblicazione e del database di distribuzione](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="29cef-105">For more information about using the wizard and accessing the dialog box, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md) and [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
### <a name="to-enable-a-publisher-in-the-configure-distribution-wizard"></a><span data-ttu-id="29cef-106">Per attivare un server di pubblicazione nella Configurazione guidata distribuzione</span><span class="sxs-lookup"><span data-stu-id="29cef-106">To enable a Publisher in the Configure Distribution Wizard</span></span>  
  
1.  <span data-ttu-id="29cef-107">Nella pagina **Server di pubblicazione** della Configurazione guidata distribuzione fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="29cef-107">On the **Publishers** page of the Configure Distribution Wizard, click **Add**.</span></span>  
  
2.  <span data-ttu-id="29cef-108">Fare clic su **Aggiungi server di pubblicazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="29cef-108">Click **Add SQL Server Publisher**.</span></span> <span data-ttu-id="29cef-109">Per informazioni sull'attivazione di un server di pubblicazione Oracle per l'utilizzo di un server di distribuzione, vedere [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="29cef-109">For information about enabling an Oracle Publisher to use a Distributor, see [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span></span>  
  
3.  <span data-ttu-id="29cef-110">Nella finestra di dialogo **Connetti al server** specificare le informazioni sulla connessione del server di pubblicazione che utilizzerà il server di distribuzione remoto e fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="29cef-110">In the **Connect to Server** dialog box, specify connection information for the Publisher that will use the remote Distributor, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="29cef-111">Nelle caselle di testo **Password** e **Conferma password** della pagina **Password server di distribuzione** specificare una password complessa per l'account **distributor_admin** , che verrà utilizzata durante la replica per la connessione dal server di pubblicazione al server di distribuzione allo scopo di eseguire le attività amministrative.</span><span class="sxs-lookup"><span data-stu-id="29cef-111">On the **Distributor Password** page, in the **Password** and **Confirm password** text boxes, specify a strong password for the **distributor_admin** account, which replication uses to connect from the Publisher to the Distributor to perform administrative tasks.</span></span>  
  
5.  <span data-ttu-id="29cef-112">Per visualizzare e modificare le impostazioni relative a un server di pubblicazione, fare clic sul pulsante delle proprietà ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="29cef-112">To view and modify settings for a Publisher, click the properties button (**...**).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-enable-a-publisher-in-the-distributor-properties-dialog-box"></a><span data-ttu-id="29cef-113">Per abilitare un server di pubblicazione nella finestra di dialogo Proprietà database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="29cef-113">To enable a Publisher in the Distributor Properties dialog box</span></span>  
  
1.  <span data-ttu-id="29cef-114">Nella pagina **Server di pubblicazione** della finestra di dialogo **Proprietà database di distribuzione - \<Distributor>** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="29cef-114">On the **Publishers** page of the **Distributor Properties - \<Distributor>** dialog box, click **Add**.</span></span>  
  
2.  <span data-ttu-id="29cef-115">Fare clic su **Aggiungi server di pubblicazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="29cef-115">Click **Add SQL Server Publisher**.</span></span> <span data-ttu-id="29cef-116">Per informazioni sull'attivazione di un server di pubblicazione Oracle per l'utilizzo di un server di distribuzione, vedere [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="29cef-116">For information about enabling an Oracle Publisher to use a Distributor, see [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span></span>  
  
3.  <span data-ttu-id="29cef-117">Nella finestra di dialogo **Connetti al server** specificare le informazioni sulla connessione del server di pubblicazione che utilizzerà il server di distribuzione remoto e fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="29cef-117">In the **Connect to Server** dialog box, specify connection information for the Publisher that will use the remote Distributor, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="29cef-118">Nelle caselle di testo **Password** e **Conferma password** della pagina **Server di pubblicazione** specificare una password complessa per l'account **distributor_admin** , che verrà utilizzata durante la replica per la connessione dal server di pubblicazione al server di distribuzione allo scopo di eseguire le attività amministrative.</span><span class="sxs-lookup"><span data-stu-id="29cef-118">On the **Publishers** page, in the **Password** and **Confirm password** text boxes, specify a strong password for the **distributor_admin** account, which replication uses to connect from the Publisher to the Distributor to perform administrative tasks.</span></span>  
  
5.  <span data-ttu-id="29cef-119">Per visualizzare e modificare le impostazioni relative a un server di pubblicazione, fare clic sul pulsante delle proprietà ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="29cef-119">To view and modify settings for a Publisher, click the properties button (**...**).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="29cef-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29cef-120">See Also</span></span>  
 <span data-ttu-id="29cef-121">[Configurare la pubblicazione e la distribuzione](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="29cef-121">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="29cef-122">[Configura distribuzione](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="29cef-122">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="29cef-123">Proteggere il database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="29cef-123">Secure the Distributor</span></span>](security/secure-the-distributor.md)  
  
  
