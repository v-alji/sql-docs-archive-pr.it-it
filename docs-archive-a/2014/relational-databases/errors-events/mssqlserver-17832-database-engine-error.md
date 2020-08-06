---
title: MSSQLSERVER_17832 | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17828 (Database Engine error)
- maxtokensize
- 17832 (Database Engine error)
- login packet (bad)
ms.assetid: bd56ffe4-0855-4ada-8aca-251fbc6ff2ce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dba214e2cce04ff2583e12ae7cee9b54373390a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713223"
---
# <a name="mssqlserver_17832"></a><span data-ttu-id="5b535-102">MSSQLSERVER_17832</span><span class="sxs-lookup"><span data-stu-id="5b535-102">MSSQLSERVER_17832</span></span>
    
## <a name="details"></a><span data-ttu-id="5b535-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5b535-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b535-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="5b535-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="5b535-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="5b535-105">Event ID</span></span>|<span data-ttu-id="5b535-106">17832</span><span class="sxs-lookup"><span data-stu-id="5b535-106">17832</span></span>|  
|<span data-ttu-id="5b535-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="5b535-107">Event Source</span></span>|<span data-ttu-id="5b535-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5b535-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5b535-109">Componente</span><span class="sxs-lookup"><span data-stu-id="5b535-109">Component</span></span>|<span data-ttu-id="5b535-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5b535-110">SQLEngine</span></span>|  
|<span data-ttu-id="5b535-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="5b535-111">Symbolic Name</span></span>|<span data-ttu-id="5b535-112">SRV_BAD_LOGIN_PKT</span><span class="sxs-lookup"><span data-stu-id="5b535-112">SRV_BAD_LOGIN_PKT</span></span>|  
|<span data-ttu-id="5b535-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="5b535-113">Message Text</span></span>|<span data-ttu-id="5b535-114">La struttura del pacchetto di accesso utilizzato per aprire la connessione non è valido. La connessione è stata chiusa.</span><span class="sxs-lookup"><span data-stu-id="5b535-114">The login packet used to open the connection is structurally invalid; the connection has been closed.</span></span> <span data-ttu-id="5b535-115">Contattare il fornitore della libreria client.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="5b535-115">Please contact the vendor of the client library.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5b535-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="5b535-116">Explanation</span></span>  
 <span data-ttu-id="5b535-117">Il computer di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è in grado di elaborare il pacchetto di accesso client in quanto</span><span class="sxs-lookup"><span data-stu-id="5b535-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer was unable to process the client login packet.</span></span> <span data-ttu-id="5b535-118">quest'ultimo potrebbe essere stato creato in modo errato o danneggiato durante la trasmissione.</span><span class="sxs-lookup"><span data-stu-id="5b535-118">This may be because the packet was created improperly or because the packet was damaged during transmission.</span></span> <span data-ttu-id="5b535-119">La mancata elaborazione può essere causata anche dalla configurazione del computer di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b535-119">It can also be caused by the configuration of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="5b535-120">L'indirizzo IP elencato è l'indirizzo del computer client.</span><span class="sxs-lookup"><span data-stu-id="5b535-120">The IP address listed is the address of the client computer.</span></span>  
  
### <a name="more-information"></a><span data-ttu-id="5b535-121">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="5b535-121">More Information</span></span>  
 <span data-ttu-id="5b535-122">In caso di utilizzo dell'autenticazione di Windows in un ambiente Kerberos, un client riceve un ticket Kerberos che contiene un certificato attributi privilegi.</span><span class="sxs-lookup"><span data-stu-id="5b535-122">When using Windows Authentication in a Kerberos environment, a client receives a Kerberos ticket that contains a Privilege Attribute Certificate (PAC).</span></span> <span data-ttu-id="5b535-123">Tale certificato contiene vari tipi di dati sull'autorizzazione, inclusi i gruppi di cui l'utente è membro, i diritti di cui dispone e i criteri validi.</span><span class="sxs-lookup"><span data-stu-id="5b535-123">The PAC contains various types of authorization data including groups that the user is a member of, rights the user has, and what policies apply to the user.</span></span> <span data-ttu-id="5b535-124">Quando il client riceve il ticket Kerberos, le informazioni contenute nel certificato attributi privilegi vengono utilizzate per generare il token di accesso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5b535-124">When the client receives the Kerberos ticket, the information contained in the PAC is used to generate the user's access token.</span></span> <span data-ttu-id="5b535-125">Il client presenta il token al computer di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] come parte del pacchetto di accesso.</span><span class="sxs-lookup"><span data-stu-id="5b535-125">The client presents the token to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer as part of the login packet.</span></span>  
  
 <span data-ttu-id="5b535-126">Se il token è stato creato in modo errato o è stato danneggiato durante la trasmissione, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non sono disponibili informazioni aggiuntive sul problema.</span><span class="sxs-lookup"><span data-stu-id="5b535-126">If the token was improperly created or damaged during transmission, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot offer additional information about the problem.</span></span>  
  
 <span data-ttu-id="5b535-127">Quando l'utente è un membro di molti gruppi o dispone di molti criteri, è possibile che il token diventi più grande del normale per elencarli tutti.</span><span class="sxs-lookup"><span data-stu-id="5b535-127">When the user is a member of many groups or has many policies, the token may grow larger than normal to list them all.</span></span> <span data-ttu-id="5b535-128">Se il token diventa più grande del valore di **MaxTokenSize** del computer server, il client non riesce a connettersi con un errore di rete generale ed è possibile che venga generato l'errore 17832.</span><span class="sxs-lookup"><span data-stu-id="5b535-128">If the token grows larger than the **MaxTokenSize** value of the server computer, the client fails to connect with a General Network Error (GNE) and error 17832 can occur.</span></span> <span data-ttu-id="5b535-129">Questo problema può interessare solo alcune categorie di utenti, ovvero coloro che dispongono di molti gruppi o criteri.</span><span class="sxs-lookup"><span data-stu-id="5b535-129">This problem may affect only some users: users with many groups or policies.</span></span> <span data-ttu-id="5b535-130">Se il problema è il valore di **MaxTokenSize** del computer server, l'errore 17832 nel log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sarà accompagnato da un errore con lo stato 9.</span><span class="sxs-lookup"><span data-stu-id="5b535-130">When the problem is the **MaxTokenSize** value of the server computer, error 17832 in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log will be accompanied by an error with state 9.</span></span> <span data-ttu-id="5b535-131">Per altri dettagli su Kerberos e **MaxTokenSize**, vedere [KB327825](https://support.microsoft.com/kb/327825).</span><span class="sxs-lookup"><span data-stu-id="5b535-131">For additional details about the Kerberos and **MaxTokenSize**, see [KB327825](https://support.microsoft.com/kb/327825).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5b535-132">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="5b535-132">User Action</span></span>  
 <span data-ttu-id="5b535-133">Per risolvere questo problema, aumentare il valore di **MaxTokenSize** del computer server in modo da impostarlo su una dimensione sufficientemente ampia da contenere il token più grande di qualsiasi utente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b535-133">To resolve this problem, increase the **MaxTokenSize** value of the server computer, to a size large enough to contain the largest token of any user in your organization.</span></span> <span data-ttu-id="5b535-134">Per identificare la dimensione del token appropriata per la propria organizzazione, usare l'applicazione **Tokensz**.</span><span class="sxs-lookup"><span data-stu-id="5b535-134">To research the correct token size for your organization, consider using the **Tokensz** application.</span></span>   
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="5b535-135">**Per modificare il MaxTokenSize nel computer server**</span><span class="sxs-lookup"><span data-stu-id="5b535-135">**To change the MaxTokenSize  on the server computer**</span></span>  
  
1.  <span data-ttu-id="5b535-136">Fare clic sul menu **Start** e scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5b535-136">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="5b535-137">Digitare `regedit` e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b535-137">Type `regedit`, and then click **OK**.</span></span> <span data-ttu-id="5b535-138">Se viene visualizzata la finestra di dialogo **Controllo account utente**, fare clic su **Continua**.</span><span class="sxs-lookup"><span data-stu-id="5b535-138">(If the **User Account Control** dialog box appears, click **Continue**.)</span></span>  
  
3.  <span data-ttu-id="5b535-139">Passare a **HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Lsa\Kerberos\Parameters**.</span><span class="sxs-lookup"><span data-stu-id="5b535-139">Navigate to **HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Lsa\Kerberos\Parameters**.</span></span>  
  
4.  <span data-ttu-id="5b535-140">Se il parametro **MaxTokenSize** non è presente, fare clic con il pulsante destro del mouse su **Parametri**, scegliere **Nuovo** e quindi fare clic su **Valore DWORD (32 bit)** .</span><span class="sxs-lookup"><span data-stu-id="5b535-140">If the **MaxTokenSize** parameter is not present, right-click **Parameters**, point to **New**, and then click **DWORD (32-bit)** Value.</span></span> <span data-ttu-id="5b535-141">Assegnare alla voce del Registro di sistema il nome **MaxTokenSize**.</span><span class="sxs-lookup"><span data-stu-id="5b535-141">Name the registry entry **MaxTokenSize**.</span></span>  
  
5.  <span data-ttu-id="5b535-142">Fare clic con il pulsante destro del mouse su **MaxTokenSize** e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5b535-142">Right-click **MaxTokenSize**, and then click **Modify**.</span></span>  
  
6.  <span data-ttu-id="5b535-143">Nella casella **Dati valore** digitare il valore di **MaxTokenSize** desiderato.</span><span class="sxs-lookup"><span data-stu-id="5b535-143">In the **Value data** box type the desired **MaxTokenSize** value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b535-144">Il valore esadecimale ffff (valore decimale 65535) rappresenta la dimensione massima del token consigliata.</span><span class="sxs-lookup"><span data-stu-id="5b535-144">Hexadecimal value ffff (decimal value 65535) is the maximum recommended token size.</span></span> <span data-ttu-id="5b535-145">L'indicazione di questo valore potrebbe risolvere il problema, ma avere al tempo stesso effetti negativi sul computer relativamente alle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="5b535-145">Providing this value would probably solve the problem, but could have negative computer-wide effects with regard to performance.</span></span> <span data-ttu-id="5b535-146">È consigliabile impostare il valore minimo di **MaxTokenSize** che consente di ottenere il token più grande di qualsiasi utente nell'organizzazione e immettere quindi tale valore.</span><span class="sxs-lookup"><span data-stu-id="5b535-146">We recommend that you establish the minimum **MaxTokenSize** value that allows for the largest token of any user in your organization and enter that value.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="5b535-147">Chiudere l'**Editor del Registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="5b535-147">Close **Registry Editor**.</span></span>  
  
9. <span data-ttu-id="5b535-148">Riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="5b535-148">Restart the computer.</span></span>  
  
  
