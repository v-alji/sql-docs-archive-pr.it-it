---
title: Nuovo alias (scheda alias) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 785eb6fb-f67e-449d-b1c8-c38dfbb95ef6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 90742e5de3da0cac83c8b18eebba242ddb9a865d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628041"
---
# <a name="new-alias-alias-tab"></a><span data-ttu-id="b4465-102">Nuovo alias (scheda Alias)</span><span class="sxs-lookup"><span data-stu-id="b4465-102">New Alias (Alias Tab)</span></span>
  <span data-ttu-id="b4465-103">Un alias rappresenta un nome alternativo che può essere utilizzato per stabilire una connessione.</span><span class="sxs-lookup"><span data-stu-id="b4465-103">An alias is an alternate name that can be used to make a connection.</span></span> <span data-ttu-id="b4465-104">L'alias incapsula gli elementi necessari di una stringa di connessione e li espone con un nome scelto dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b4465-104">The alias encapsulates the required elements of a connection string, and exposes them with a name chosen by the user.</span></span> <span data-ttu-id="b4465-105">La pagina **Alias** della finestra di dialogo **Nuovo alias** consente di specificare gli elementi della stringa di connessione per un alias.</span><span class="sxs-lookup"><span data-stu-id="b4465-105">Use the **Alias** page on the **Alias - New** dialog box to specify the elements of the connection string for an alias.</span></span> <span data-ttu-id="b4465-106">Per modificare la stringa di connessione di un alias esistente, vedere [Proprietà &#60;Alias&#62; &#40;scheda Alias&#41;](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md).</span><span class="sxs-lookup"><span data-stu-id="b4465-106">To change the connection string of an existing alias, see [&#60;Alias&#62; Properties &#40;Alias Tab&#41;](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md).</span></span>  
  
 <span data-ttu-id="b4465-107">Non è necessario completare tutti i valori nella griglia **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="b4465-107">All values in the **Properties** grid do not have to be completed.</span></span> <span data-ttu-id="b4465-108">Le combinazioni valide variano a seconda del protocollo selezionato.</span><span class="sxs-lookup"><span data-stu-id="b4465-108">Valid combinations vary depending on the protocol selected.</span></span> <span data-ttu-id="b4465-109">Per esempi di combinazioni valide, vedere gli argomenti elencati di seguito.</span><span class="sxs-lookup"><span data-stu-id="b4465-109">See the topics listed below for examples of valid combinations.</span></span>  
  
 <span data-ttu-id="b4465-110">**Nome alias**</span><span class="sxs-lookup"><span data-stu-id="b4465-110">**Alias Name**</span></span>  
 <span data-ttu-id="b4465-111">Nome o alias che si desidera utilizzare per fare riferimento alla connessione.</span><span class="sxs-lookup"><span data-stu-id="b4465-111">The name (alias) that you want to use to refer to this connection.</span></span>  
  
 <span data-ttu-id="b4465-112">**Nome pipe** / **Numero porta**</span><span class="sxs-lookup"><span data-stu-id="b4465-112">**Pipe Name** / **Port No**</span></span>  
 <span data-ttu-id="b4465-113">Elementi aggiuntivi della stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="b4465-113">Additional elements of the connection string.</span></span> <span data-ttu-id="b4465-114">Il nome di questa casella varia a seconda del protocollo selezionato.</span><span class="sxs-lookup"><span data-stu-id="b4465-114">The name of this box varies with the selected protocol.</span></span>  
  
 <span data-ttu-id="b4465-115">**Protocollo**</span><span class="sxs-lookup"><span data-stu-id="b4465-115">**Protocol**</span></span>  
 <span data-ttu-id="b4465-116">Protocollo utilizzato per la connessione.</span><span class="sxs-lookup"><span data-stu-id="b4465-116">The protocol used for the connection.</span></span>  
  
 <span data-ttu-id="b4465-117">**Server**</span><span class="sxs-lookup"><span data-stu-id="b4465-117">**Server**</span></span>  
 <span data-ttu-id="b4465-118">Nome dell'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a cui si esegue la connessione.</span><span class="sxs-lookup"><span data-stu-id="b4465-118">The name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance being connected to.</span></span>  
  
## <a name="when-to-use-an-alias"></a><span data-ttu-id="b4465-119">Situazioni in cui utilizzare un alias</span><span class="sxs-lookup"><span data-stu-id="b4465-119">When to Use an Alias</span></span>  
 <span data-ttu-id="b4465-120">Per impostazione predefinita, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si connette a un'istanza locale di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante il protocollo **Shared Memory** e a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un altro computer mediante **TCP/IP** o **Named Pipes**.</span><span class="sxs-lookup"><span data-stu-id="b4465-120">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connects to a local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the **Shared Memory** protocol, and to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on another computer using either **TCP/IP** or **Named Pipes**.</span></span> <span data-ttu-id="b4465-121">Creare un alias quando si utilizza TCP/IP o Named Pipes e si desidera fornire una stringa di connessione personalizzata o quando si desidera utilizzare un nome diverso da quello del server per la connessione.</span><span class="sxs-lookup"><span data-stu-id="b4465-121">Create an alias when you are using TCP/IP or named pipes, and you want to provide a customized connection string, or when you want to use a name other than the server name for the connection.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="b4465-122">Esempi</span><span class="sxs-lookup"><span data-stu-id="b4465-122">Examples</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b4465-123">non è in attesa sulla porta TCP/IP 1433 predefinita, pertanto si desidera creare una stringa di connessione con un numero di porta diverso.</span><span class="sxs-lookup"><span data-stu-id="b4465-123">is not listening on the default TCP/IP port of 1433 so you want to provide a connection string with a different port number.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b4465-124">non è in attesa sulla porta named pipe predefinita, pertanto si desidera creare una stringa di connessione con un nome di pipe diverso.</span><span class="sxs-lookup"><span data-stu-id="b4465-124">is not listening on the default named pipe so you want to provide a connection string with a different pipe name.</span></span>  
  
-   <span data-ttu-id="b4465-125">Un'applicazione prevede di connettersi a un database nel server denominato `ACCT`, ma tale database è stato consolidato come istanza denominata `ACCT` nel server `CENTRAL`.</span><span class="sxs-lookup"><span data-stu-id="b4465-125">An application expects to connect to a database on the server named `ACCT`, but that database has been consolidated as an instance named `ACCT` on a server named `CENTRAL`.</span></span> <span data-ttu-id="b4465-126">Non è semplice modificare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b4465-126">The application cannot easily be changed.</span></span> <span data-ttu-id="b4465-127">Creare un alias denominato `ACCT`, con una stringa di connessione che punta a `CENTRAL\ACCT`.</span><span class="sxs-lookup"><span data-stu-id="b4465-127">Create an alias named `ACCT`, with a connection string pointing to `CENTRAL\ACCT`.</span></span>  
  
## <a name="creating-a-valid-connection-string"></a><span data-ttu-id="b4465-128">Creazione di una stringa di connessione valida</span><span class="sxs-lookup"><span data-stu-id="b4465-128">Creating a Valid Connection String</span></span>  
 <span data-ttu-id="b4465-129">Per una descrizione ed esempi di combinazioni valide di proprietà di alias, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4465-129">See the following topics for a description and examples of valid combinations of alias properties:</span></span>  
  
-   [<span data-ttu-id="b4465-130">Creazione di una stringa di connessione valida mediante il protocollo di memoria condivisa</span><span class="sxs-lookup"><span data-stu-id="b4465-130">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
-   [<span data-ttu-id="b4465-131">Creazione di una stringa di connessione valida con TCP/IP</span><span class="sxs-lookup"><span data-stu-id="b4465-131">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
-   [<span data-ttu-id="b4465-132">Creazione di una stringa di connessione valida tramite named pipe</span><span class="sxs-lookup"><span data-stu-id="b4465-132">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
