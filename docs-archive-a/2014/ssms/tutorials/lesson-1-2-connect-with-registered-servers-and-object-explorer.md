---
title: Connettersi con Server registrati ed Esplora oggetti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: d6b3911f-68b4-4483-831b-df89d6400add
author: stevestein
ms.author: sstein
ms.openlocfilehash: b4bc75ad7f3682765dc102064a5621cd541ccd12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711503"
---
# <a name="connect-with-registered-servers-and-object-explorer"></a><span data-ttu-id="ca4d5-102">Connettersi con Server registrati ed Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="ca4d5-102">Connect with Registered Servers and Object Explorer</span></span>
  <span data-ttu-id="ca4d5-103">In questa esercitazione viene illustrato l'utilizzo di Server registrati ed Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="ca4d5-103">This tutorial demonstrates the use of Registered Servers and Object Explorer.</span></span>  
  
 <span data-ttu-id="ca4d5-104">In questa esercitazione viene utilizzato il database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ca4d5-104">This tutorial uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="ca4d5-105">Per una maggiore sicurezza, i database di esempio non vengono installati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ca4d5-105">To help enhance security, by default, the sample databases are not installed.</span></span> <span data-ttu-id="ca4d5-106">Per ulteriori informazioni, vedere la pagina relativa all' [installazione dei database di esempio e degli esempi di SQL Server](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="ca4d5-106">For more information, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
## <a name="connecting-to-servers"></a><span data-ttu-id="ca4d5-107">Connessione ai server</span><span class="sxs-lookup"><span data-stu-id="ca4d5-107">Connecting to Servers</span></span>  
 <span data-ttu-id="ca4d5-108">Nella barra degli strumenti del componente Server registrati sono inclusi pulsanti per il [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]e [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca4d5-108">The toolbar of the Registered Servers component has buttons for the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="ca4d5-109">È possibile registrare uno o più di questi tipi di server a seconda delle esigenze di gestione.</span><span class="sxs-lookup"><span data-stu-id="ca4d5-109">You can register one or more of these server types for convenient management.</span></span> <span data-ttu-id="ca4d5-110">Eseguire le procedure descritte di seguito per registrare il database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ca4d5-110">Try the following exercise to register the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
#### <a name="to-register-the-database"></a><span data-ttu-id="ca4d5-111">Per registrare il database</span><span class="sxs-lookup"><span data-stu-id="ca4d5-111">To register the database</span></span>  
  
1.  <span data-ttu-id="ca4d5-112">Fare clic su **Motore di database** nella barra degli strumenti Server registrati, se necessario</span><span class="sxs-lookup"><span data-stu-id="ca4d5-112">On the Registered Servers toolbar, click **Database Engine** if you have to.</span></span> <span data-ttu-id="ca4d5-113">(è possibile che sia già selezionato).</span><span class="sxs-lookup"><span data-stu-id="ca4d5-113">(It may already be selected.)</span></span>  
  
2.  <span data-ttu-id="ca4d5-114">Espandere **Motore di database**.</span><span class="sxs-lookup"><span data-stu-id="ca4d5-114">Expand **Database Engine**.</span></span>  
  
3.  <span data-ttu-id="ca4d5-115">Fare clic con il pulsante destro del mouse su **Gruppi di server locali**e scegliere **Nuova registrazione server**.</span><span class="sxs-lookup"><span data-stu-id="ca4d5-115">Right-click **Local Server Groups**, and then click **New Server Registration**.</span></span>  
  
4.  <span data-ttu-id="ca4d5-116">Nella casella di testo **Nome server** della finestra di dialogo **Nuova registrazione server** digitare il nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca4d5-116">In the **New Server Registration** dialog box, in the **Server name** text box, type the name of your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="ca4d5-117">Nella casella **Nome server registrato** digitare [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca4d5-117">In the **Registered server name** box, type [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
6.  <span data-ttu-id="ca4d5-118">Nell'elenco **Connetti al database** della scheda **Proprietà connessione** selezionare **\<Browse server...>** .</span><span class="sxs-lookup"><span data-stu-id="ca4d5-118">On the **Connection Properties** tab, in the **Connect to database** list, select **\<Browse server...>**.</span></span>  
  
7.  <span data-ttu-id="ca4d5-119">Nella finestra di dialogo **Cerca database** fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="ca4d5-119">In the **Browse for Databases** dialog box, click **Yes**.</span></span>  
  
8.  <span data-ttu-id="ca4d5-120">Nella finestra di dialogo **Cerca database nel server** selezionare [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ca4d5-120">In the **Browse Server for Database** dialog box, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **OK**.</span></span>  
  
9. <span data-ttu-id="ca4d5-121">Per verificare che il server sia stato registrato correttamente, fare clic su **Test**.</span><span class="sxs-lookup"><span data-stu-id="ca4d5-121">To verify that the server has been registered correctly, click **Test**.</span></span>  
  
10. <span data-ttu-id="ca4d5-122">Nella finestra di dialogo **Nuova registrazione server** fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ca4d5-122">In the **New Server Registration** dialog box, click **Save**.</span></span>  
  
## <a name="connecting-with-object-explorer"></a><span data-ttu-id="ca4d5-123">Connessione con Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="ca4d5-123">Connecting with Object Explorer</span></span>  
 <span data-ttu-id="ca4d5-124">Analogamente a Server registrati, tramite Esplora oggetti è possibile connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)], ad [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], a [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]e a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca4d5-124">Like Registered Servers, Object Explorer can connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
#### <a name="to-connect-with-object-explorer"></a><span data-ttu-id="ca4d5-125">Per connettersi con Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="ca4d5-125">To connect with Object Explorer</span></span>  
  
1.  <span data-ttu-id="ca4d5-126">Fare clic su **Connetti** nella barra degli strumenti di Esplora oggetti per visualizzare l'elenco dei tipi di connessione disponibili e quindi selezionare **Motore di database**.</span><span class="sxs-lookup"><span data-stu-id="ca4d5-126">On the toolbar of Object Explorer, click **Connect** for a list of possible connection types, and then select **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="ca4d5-127">Nella casella di testo **Nome server** della finestra di dialogo **Connetti al server** digitare il nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca4d5-127">In the **Connect to Server** dialog box, in the **Server name** text box, type the name of your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="ca4d5-128">Fare clic su **Opzioni** ed esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="ca4d5-128">Click **Options** and explore the choices.</span></span>  
  
4.  <span data-ttu-id="ca4d5-129">Fare clic su **Connetti**per connettersi al server.</span><span class="sxs-lookup"><span data-stu-id="ca4d5-129">To connect to the server, click **Connect**.</span></span> <span data-ttu-id="ca4d5-130">Se la connessione è già stata eseguita, si tornerà a Esplora oggetti e il server riceverà lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="ca4d5-130">If you are already connected, this action just returns you to Object Explorer and sets the focus on that server.</span></span>  
  
     <span data-ttu-id="ca4d5-131">Con Esplora oggetti è possibile amministrare la sicurezza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, Replica e Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="ca4d5-131">With Object Explorer you can administer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Security, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, Replication, and Database Mail.</span></span> <span data-ttu-id="ca4d5-132">In Esplora oggetti è possibile gestire solo alcune caratteristiche di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]e [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca4d5-132">Object Explorer can only manage some of the features of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span></span> <span data-ttu-id="ca4d5-133">Ognuno di questi componenti contiene strumenti specializzati aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="ca4d5-133">Each of those components has additional specialized tools.</span></span>  
  
5.  <span data-ttu-id="ca4d5-134">In Esplora oggetti espandere la cartella **Database** e selezionare [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca4d5-134">In Object Explorer, expand the **Databases** folder and select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
     <span data-ttu-id="ca4d5-135">Si noti che [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] include i database di sistema in una cartella distinta.</span><span class="sxs-lookup"><span data-stu-id="ca4d5-135">Notice that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] presents the system databases in a separate folder.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ca4d5-136">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="ca4d5-136">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ca4d5-137">Modificare il layout ambiente</span><span class="sxs-lookup"><span data-stu-id="ca4d5-137">Change the Environment Layout</span></span>](lesson-1-3-change-the-environment-layout.md)  
  
  
