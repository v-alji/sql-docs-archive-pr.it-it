---
title: Avvio dell'utilità sqlcmd
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 00d57437-7a29-4da1-b639-ee990db055fb
author: rothja
ms.author: jroth
ms.openlocfilehash: d71e6f140238599b3f22850ee9b63a0ee25d900b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625283"
---
# <a name="start-the-sqlcmd-utility"></a><span data-ttu-id="33995-102">Avvio dell'utilità sqlcmd</span><span class="sxs-lookup"><span data-stu-id="33995-102">Start the sqlcmd Utility</span></span>
  <span data-ttu-id="33995-103">Per iniziare a utilizzare `sqlcmd`, è innanzitutto necessario avviare l'utilità e connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33995-103">To begin using `sqlcmd`, you must first launch the utility and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="33995-104">È possibile connettersi a un'istanza predefinita oppure a un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="33995-104">You can connect to either a default or named instance.</span></span> <span data-ttu-id="33995-105">Il primo passaggio consiste nell'avvio dell'utilità `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="33995-105">The first step is to start the `sqlcmd` utility.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33995-106">La modalità di autenticazione predefinita per l'utilità `sqlcmd` è l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="33995-106">Windows Authentication is the default authentication mode for `sqlcmd`.</span></span> <span data-ttu-id="33995-107">Per usare l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è necessario specificare un nome utente e una password con le opzioni **-U** e **-P** .</span><span class="sxs-lookup"><span data-stu-id="33995-107">To use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must specify a user name and password by using the **-U** and **-P** options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33995-108">Per impostazione predefinita, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] viene installato come istanza denominata **sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="33995-108">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs as the named instance **sqlexpress**.</span></span>  
  
 <span data-ttu-id="33995-109">Se non ci si è mai connessi a questa istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], potrebbe essere necessario configurare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per accettare connessioni.</span><span class="sxs-lookup"><span data-stu-id="33995-109">If you have not connected to this instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] before, you may have to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
### <a name="to-start-the-sqlcmd-utility-and-connect-to-a-default-instance-of-sql-server"></a><span data-ttu-id="33995-110">Per avviare l'utilità sqlcmd e connettersi a un'istanza predefinita di SQL Server</span><span class="sxs-lookup"><span data-stu-id="33995-110">To start the sqlcmd utility and connect to a default instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="33995-111">Dal menu **Start** fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="33995-111">On the **Start** menu click **Run**.</span></span> <span data-ttu-id="33995-112">Nella casella **Apri** digitare **cmd**e quindi fare clic su **OK** per aprire una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="33995-112">In the **Open** box type **cmd**, and then click **OK** to open a Command Prompt window.</span></span>  
  
2.  <span data-ttu-id="33995-113">Al prompt dei comandi digitare `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="33995-113">At the command prompt, type `sqlcmd`.</span></span>  
  
3.  <span data-ttu-id="33995-114">Premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="33995-114">Press ENTER.</span></span>  
  
     <span data-ttu-id="33995-115">Verrà quindi stabilita una connessione trusted all'istanza predefinita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in esecuzione nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="33995-115">You now have a trusted connection to the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on your computer.</span></span>  
  
     <span data-ttu-id="33995-116">**1>** è il `sqlcmd` prompt che specifica il numero di riga.</span><span class="sxs-lookup"><span data-stu-id="33995-116">**1>** is the `sqlcmd` prompt that specifies the line number.</span></span> <span data-ttu-id="33995-117">Il numero viene aumentato di un'unità ogni volta che si preme INVIO.</span><span class="sxs-lookup"><span data-stu-id="33995-117">Each time you press ENTER, the number increases by one.</span></span>  
  
4.  <span data-ttu-id="33995-118">Per terminare la `sqlcmd` sessione, digitare `EXIT` al `sqlcmd` prompt.</span><span class="sxs-lookup"><span data-stu-id="33995-118">To end the `sqlcmd` session, type `EXIT` at the `sqlcmd` prompt.</span></span>  
  
### <a name="to-start-the-sqlcmd-utility-and-connect-to-a-named-instance-of-sql-server"></a><span data-ttu-id="33995-119">Per avviare l'utilità sqlcmd e connettersi a un'istanza denominata di SQL Server</span><span class="sxs-lookup"><span data-stu-id="33995-119">To start the sqlcmd utility and connect to a named instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="33995-120">Aprire una finestra del prompt dei comandi e digitare `sqlcmd -S` *myServer\instanceName*.</span><span class="sxs-lookup"><span data-stu-id="33995-120">Open a Command Prompt window, and type `sqlcmd -S`*myServer\instanceName*.</span></span> <span data-ttu-id="33995-121">Sostituire *server\nomeIstanza* con il nome del computer e dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a cui ci si vuole connettere.</span><span class="sxs-lookup"><span data-stu-id="33995-121">Replace *myServer\instanceName* with the name of the computer and the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to connect to.</span></span>  
  
2.  <span data-ttu-id="33995-122">Premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="33995-122">Press ENTER.</span></span>  
  
     <span data-ttu-id="33995-123">Il `sqlcmd` prompt (1>) indica che si è connessi all'istanza specificata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33995-123">The `sqlcmd` prompt (1>) indicates that you are connected to the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="33995-124">Le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] immesse vengono archiviate in un buffer.</span><span class="sxs-lookup"><span data-stu-id="33995-124">Entered [!INCLUDE[tsql](../../includes/tsql-md.md)] statements are stored in a buffer.</span></span> <span data-ttu-id="33995-125">Vengono eseguite in batch quando viene rilevato il comando GO.</span><span class="sxs-lookup"><span data-stu-id="33995-125">They are executed as a batch when the GO command is encountered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33995-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33995-126">See Also</span></span>  
 [<span data-ttu-id="33995-127">Esecuzione di file script Transact-SQL mediante sqlcmd</span><span class="sxs-lookup"><span data-stu-id="33995-127">Run Transact-SQL Script Files Using sqlcmd</span></span>](sqlcmd-run-transact-sql-script-files.md)  
  
  
