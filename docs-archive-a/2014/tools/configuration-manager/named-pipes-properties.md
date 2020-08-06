---
title: Proprietà Named Pipes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- pipes [SQL Server]
- listening [SQL Server], pipes
- pipes [SQL Server], listening on pipes
- Named Pipes [SQL Server], listening on pipes
ms.assetid: a5fd5b8e-f889-485b-89e3-d4010ec4c6ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80790c1cb8830a0fd132721f375a70d2574421b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628042"
---
# <a name="named-pipes-properties"></a><span data-ttu-id="1de50-102">Proprietà Named Pipes</span><span class="sxs-lookup"><span data-stu-id="1de50-102">Named Pipes Properties</span></span>
  <span data-ttu-id="1de50-103">La pagina **Protocollo** della finestra di dialogo **Proprietà - Named Pipes** consente di visualizzare o modificare la named pipe sulla quale [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resta in attesa quando è in uso il protocollo Named Pipes.</span><span class="sxs-lookup"><span data-stu-id="1de50-103">Use the **Protocol**page on the **Named Pipes Properties** dialog box to view or change the named pipe that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens to, when using the Named Pipes protocol.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1de50-104">deve essere riavviato per abilitare o disabilitare il protocollo oppure modificare la named pipe.</span><span class="sxs-lookup"><span data-stu-id="1de50-104">must be restarted to enable or disable the protocol, or change the named pipe.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1de50-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1de50-105">Options</span></span>  
 <span data-ttu-id="1de50-106">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="1de50-106">**Enabled**</span></span>  
 <span data-ttu-id="1de50-107">I valori possibili sono **Sì** e **No**.</span><span class="sxs-lookup"><span data-stu-id="1de50-107">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="1de50-108">**Nome pipe**</span><span class="sxs-lookup"><span data-stu-id="1de50-108">**Pipe Name**</span></span>  
 <span data-ttu-id="1de50-109">Specifica la named pipe sulla quale [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resta in attesa.</span><span class="sxs-lookup"><span data-stu-id="1de50-109">Specifies the named pipe on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens.</span></span> <span data-ttu-id="1de50-110">Per impostazione predefinita, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resta in attesa su `\\.\pipe\sql\query` per l'istanza predefinita e su `\\.\pipe\MSSQL$<instancename>\sql\query` per un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="1de50-110">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on: `\\.\pipe\sql\query` for the default instance and `\\.\pipe\MSSQL$<instancename>\sql\query` for a named instance.</span></span> <span data-ttu-id="1de50-111">La lunghezza massima del campo è 2047 caratteri.</span><span class="sxs-lookup"><span data-stu-id="1de50-111">This field is limited to 2047 characters.</span></span>  
  
## <a name="creating-an-alternate-named-pipe"></a><span data-ttu-id="1de50-112">Creazione di una named pipe alternativa</span><span class="sxs-lookup"><span data-stu-id="1de50-112">Creating an Alternate Named Pipe</span></span>  
 <span data-ttu-id="1de50-113">Per modificare la named pipe, digitare il nome della nuova pipe nella casella **Nome pipe** e quindi arrestare e riavviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1de50-113">To change the named pipe, type the new pipe name in the **Pipe Name** box and then stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1de50-114">Poiché è noto che **sql\query** è la named pipe usata da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], modificare la pipe può risultare utile per ridurre il rischio di attacco da parte di programmi dannosi.</span><span class="sxs-lookup"><span data-stu-id="1de50-114">Since **sql\query** is well known as the named pipe used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], changing the pipe can help reduce the risk of attack by malicious programs.</span></span>  
  
### <a name="example"></a><span data-ttu-id="1de50-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="1de50-115">Example</span></span>  
 <span data-ttu-id="1de50-116">Digitare **\\\\.\pipe\unit\app** per impostare l'attesa sulla pipe **unit\app** .</span><span class="sxs-lookup"><span data-stu-id="1de50-116">Type **\\\\.\pipe\unit\app** to listen on the **unit\app** pipe.</span></span>  
  
 <span data-ttu-id="1de50-117">Digitare **\\\\.\pipe\acct** per impostare l'attesa sulla pipe **acct** .</span><span class="sxs-lookup"><span data-stu-id="1de50-117">Type **\\\\.\pipe\acct** to listen on the **acct** pipe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de50-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1de50-118">See Also</span></span>  
 <span data-ttu-id="1de50-119">[Abilitare o disabilitare un protocollo di rete del server](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="1de50-119">[Enable or Disable a Server Network Protocol](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span></span>  
 <span data-ttu-id="1de50-120">[Scelta di un protocollo di rete](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="1de50-120">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="1de50-121">Creazione di una stringa di connessione valida tramite named pipe</span><span class="sxs-lookup"><span data-stu-id="1de50-121">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
