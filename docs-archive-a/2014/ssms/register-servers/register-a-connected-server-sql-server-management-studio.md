---
title: Registrare un server connesso
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.f1
helpviewer_keywords:
- Registered Servers [SQL Server], register connected servers
- connected server registrations [SQL Server]
ms.assetid: 77deb5f5-0f80-484f-8b8b-29afa67ec18f
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 1d337d2da7d305165307745fb02526e37b53bbd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627020"
---
# <a name="register-a-connected-server-sql-server-management-studio"></a><span data-ttu-id="6905d-102">Registrazione di un server connesso (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="6905d-102">Register a Connected Server (SQL Server Management Studio)</span></span>
  <span data-ttu-id="6905d-103">In questo argomento viene descritto come registrare i server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6905d-103">This topic describes how to register servers in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="6905d-104">Tramite la registrazione del server è possibile salvare le informazioni di connessione per i server ai quali si accede di frequente.</span><span class="sxs-lookup"><span data-stu-id="6905d-104">By registering the server, you can save the connection information for servers that you access frequently.</span></span> <span data-ttu-id="6905d-105">È possibile registrare un server prima della connessione o durate la connessione da Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="6905d-105">A server can be registered before connecting, or at the time of connection from Object Explorer.</span></span>  
  
 <span data-ttu-id="6905d-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="6905d-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6905d-107">**Per registrare un server utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="6905d-107">**To register a server, using:**</span></span>  
  
     [<span data-ttu-id="6905d-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6905d-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6905d-109">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6905d-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-register-a-connected-server"></a><span data-ttu-id="6905d-110">Per registrare un server connesso</span><span class="sxs-lookup"><span data-stu-id="6905d-110">To register a connected server</span></span>  
  
1.  <span data-ttu-id="6905d-111">In Esplora oggetti fare clic con il pulsante destro del mouse su un server al quale si è già connessi e quindi scegliere **Registra**.</span><span class="sxs-lookup"><span data-stu-id="6905d-111">In Object Explorer, right-click a server to which you already are connected, and then click **Register**.</span></span>  
  
     <span data-ttu-id="6905d-112">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="6905d-112">**Server name**</span></span>  
     <span data-ttu-id="6905d-113">Consente di immettere il nome che si desidera utilizzare per il server registrato.</span><span class="sxs-lookup"><span data-stu-id="6905d-113">Enter the name you want to use for the registered server.</span></span> <span data-ttu-id="6905d-114">La registrazione di un server locale o remoto con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] consente di archiviare le informazioni di connessione al server per connessioni future.</span><span class="sxs-lookup"><span data-stu-id="6905d-114">Registering a local or remote server using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] lets you store the server connection information for future connections.</span></span> <span data-ttu-id="6905d-115">In questo campo viene immesso automaticamente il nome del server specificato durante la connessione al server.</span><span class="sxs-lookup"><span data-stu-id="6905d-115">This field defaults to the server name entered when you were connecting to the server.</span></span> <span data-ttu-id="6905d-116">È possibile scegliere di utilizzare questo nome oppure immettere un nome diverso per il server.</span><span class="sxs-lookup"><span data-stu-id="6905d-116">You can retain this server name or enter another easy-to-use name for the server.</span></span>  
  
     <span data-ttu-id="6905d-117">**Descrizione server**</span><span class="sxs-lookup"><span data-stu-id="6905d-117">**Server description**</span></span>  
     <span data-ttu-id="6905d-118">Consente di immettere una descrizione facoltativa del server.</span><span class="sxs-lookup"><span data-stu-id="6905d-118">Enter an optional description of the server.</span></span> <span data-ttu-id="6905d-119">Il numero massimo di caratteri consentito è di 250.</span><span class="sxs-lookup"><span data-stu-id="6905d-119">The maximum number of characters allowed is 250.</span></span>  
  
     <span data-ttu-id="6905d-120">**Selezionare un gruppo di server**</span><span class="sxs-lookup"><span data-stu-id="6905d-120">**Select a server group**</span></span>  
     <span data-ttu-id="6905d-121">Consente di selezionare il gruppo di server in cui si desidera salvare la registrazione del server.</span><span class="sxs-lookup"><span data-stu-id="6905d-121">Select the server group where you want to save the server registration.</span></span>  
  
     <span data-ttu-id="6905d-122">**Nuovo gruppo**</span><span class="sxs-lookup"><span data-stu-id="6905d-122">**New Group**</span></span>  
     <span data-ttu-id="6905d-123">Fare clic su questo pulsante per aprire la finestra di dialogo **Nuovo gruppo** tramite la quale è possibile creare un nuovo gruppo di server per il server registrato.</span><span class="sxs-lookup"><span data-stu-id="6905d-123">Click to launch the **New Group** dialog box, where you can create a new server group for the registered server.</span></span>  
  
     <span data-ttu-id="6905d-124">**Salva**</span><span class="sxs-lookup"><span data-stu-id="6905d-124">**Save**</span></span>  
     <span data-ttu-id="6905d-125">Fare clic su questo pulsante per salvare le informazioni immesse e creare un server registrato.</span><span class="sxs-lookup"><span data-stu-id="6905d-125">Click to save the information you have entered and create a registered server.</span></span>  
  
  
