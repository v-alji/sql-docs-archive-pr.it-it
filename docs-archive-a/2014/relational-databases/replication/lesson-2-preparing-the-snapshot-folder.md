---
title: 'Lezione 2: Preparazione della cartella snapshot | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: f286cde9-c0d0-43ef-b7ba-53c3cbb8906c
author: rothja
ms.author: jroth
ms.openlocfilehash: 5d98c7433d0bd50504f20f7f576fcf0b20154c81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723703"
---
# <a name="lesson-2-preparing-the-snapshot-folder"></a><span data-ttu-id="a59f4-102">Lezione 2: Preparazione della cartella snapshot</span><span class="sxs-lookup"><span data-stu-id="a59f4-102">Lesson 2: Preparing the Snapshot Folder</span></span>
  <span data-ttu-id="a59f4-103">In questa lezione verrà configurata la cartella snapshot utilizzata per la creazione e l'archiviazione dello snapshot di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="a59f4-103">In this lesson, you will learn to configure the snapshot folder that is used to create and store the publication snapshot.</span></span>  
  
### <a name="to-create-a-share-for-the-snapshot-folder-and-assign-permissions"></a><span data-ttu-id="a59f4-104">Per creare una condivisione per la cartella snapshot e assegnare le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a59f4-104">To create a share for the snapshot folder and assign permissions</span></span>  
  
1.  <span data-ttu-id="a59f4-105">In Esplora risorse passare alla cartella di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a59f4-105">In Windows Explorer, navigate to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data folder.</span></span> <span data-ttu-id="a59f4-106">Il percorso predefinito è C:\Programmi\Microsoft SQL Server\MSSQL.X\MSSQL\Data.</span><span class="sxs-lookup"><span data-stu-id="a59f4-106">The default location is C:\Program Files\Microsoft SQL Server\MSSQL.X\MSSQL\Data.</span></span>  
  
2.  <span data-ttu-id="a59f4-107">Creare una nuova cartella denominata **repldata**.</span><span class="sxs-lookup"><span data-stu-id="a59f4-107">Create a new folder named **repldata**.</span></span>  
  
3.  <span data-ttu-id="a59f4-108">Fare clic con il pulsante destro del mouse sulla cartella e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a59f4-108">Right-click this folder and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="a59f4-109">Nella scheda **Condivisione** della finestra di dialogo **Proprietà di repldata** fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="a59f4-109">On the **Sharing** tab in the **repldata Properties** dialog box, click **Share**.</span></span>  
  
5.  <span data-ttu-id="a59f4-110">Nella finestra di dialogo **Condivisione file** fare clic su **Condividi**e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a59f4-110">In the **File Sharing** dialog box, click **Share**, and then click **Done**.</span></span>  
  
6.  <span data-ttu-id="a59f4-111">Nella scheda **Sicurezza** fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a59f4-111">On the **Security** tab, click **Edit**.</span></span>  
  
7.  <span data-ttu-id="a59f4-112">Nella finestra di dialogo **Autorizzazioni** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a59f4-112">In the **Permissions** dialog box, click **Add.**</span></span> <span data-ttu-id="a59f4-113">Nella casella di testo **Seleziona utente, computer, account servizio o gruppi** Digitare il nome dell'account agente di snapshot creato nella lezione 1, come \<_Machine_Name> _**\ repl_snapshot**, dove \<*Machine_Name> \* è il nome del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="a59f4-113">In the **Select User, Computers, Service Account, or Groups** text box, type the name of the Snapshot Agent account created in Lesson 1, as \<_Machine_Name>_**\repl_snapshot**, where \<*Machine_Name>\* is the name of the Publisher.</span></span> <span data-ttu-id="a59f4-114">Fare clic su **Controlla nomi** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a59f4-114">Click **Check Names**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="a59f4-115">Ripetere il passaggio precedente per aggiungere le autorizzazioni per il agente di distribuzione, come \<_Machine_Name> _ **\ repl_distribution**e per il agente di merge come \<_Machine_Name> _ **\ repl_merge**.</span><span class="sxs-lookup"><span data-stu-id="a59f4-115">Repeat the previous step to add permissions for the Distribution Agent, as \<_Machine_Name>_**\repl_distribution**, and for the Merge Agent as \<_Machine_Name>_**\repl_merge**.</span></span>  
  
9. <span data-ttu-id="a59f4-116">Verificare che siano state concesse le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a59f4-116">Verify the following permissions are allowed:</span></span>  
  
    -   <span data-ttu-id="a59f4-117">repl_snapshot - Controllo completo</span><span class="sxs-lookup"><span data-stu-id="a59f4-117">repl_snapshot - Full Control</span></span>  
  
    -   <span data-ttu-id="a59f4-118">repl_distribution - Lettura</span><span class="sxs-lookup"><span data-stu-id="a59f4-118">repl_distribution - Read</span></span>  
  
    -   <span data-ttu-id="a59f4-119">repl_merge - Lettura</span><span class="sxs-lookup"><span data-stu-id="a59f4-119">repl_merge - Read</span></span>  
  
10. <span data-ttu-id="a59f4-120">Fare clic su **OK** per chiudere la finestra di dialogo **Proprietà di repldata** e creare la condivisione repldata.</span><span class="sxs-lookup"><span data-stu-id="a59f4-120">Click **OK** to close the **repldata Properties** dialog box and create the repldata share.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a59f4-121">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a59f4-121">Next Steps</span></span>  
 <span data-ttu-id="a59f4-122">In questo modo è stata configurata la condivisione per la cartella snapshot.</span><span class="sxs-lookup"><span data-stu-id="a59f4-122">You have successfully configured the share for the snapshot folder.</span></span> <span data-ttu-id="a59f4-123">Il passaggio successivo consiste nella configurazione della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a59f4-123">Next, you will configure distribution.</span></span> <span data-ttu-id="a59f4-124">Vedere [Lezione 3: Configurazione della distribuzione](lesson-3-configuring-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="a59f4-124">See [Lesson 3: Configuring Distribution](lesson-3-configuring-distribution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a59f4-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a59f4-125">See Also</span></span>  
 [<span data-ttu-id="a59f4-126">Proteggere la cartella snapshot</span><span class="sxs-lookup"><span data-stu-id="a59f4-126">Secure the Snapshot Folder</span></span>](security/secure-the-snapshot-folder.md)  
  
  
