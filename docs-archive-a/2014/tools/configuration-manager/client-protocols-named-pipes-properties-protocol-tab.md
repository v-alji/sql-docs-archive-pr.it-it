---
title: Protocolli client - Proprietà Named pipe (scheda Protocollo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- pipes [SQL Server], connecting to
- Named Pipes [SQL Server], default pipe
- client protocols [SQL Server]
ms.assetid: 30fbae62-2f2e-4d36-9c6e-3444fff68781
author: stevestein
ms.author: sstein
ms.openlocfilehash: 169b6d98212c724b8d6c43615ae2fa7eba9cfc7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712679"
---
# <a name="client-protocols---named-pipes-properties-protocol-tab"></a><span data-ttu-id="1cedc-102">Protocolli client - Proprietà - Named pipe (scheda Protocollo)</span><span class="sxs-lookup"><span data-stu-id="1cedc-102">Client Protocols - Named Pipes Properties (Protocol Tab)</span></span>
  <span data-ttu-id="1cedc-103">In Gestione configurazione [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usare la scheda **Protocollo** della finestra di dialogo **Proprietà - Named Pipes** per visualizzare o modificare la descrizione della pipe predefinita.</span><span class="sxs-lookup"><span data-stu-id="1cedc-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager use the **Protocol** tab on the **Named Pipes Properties** dialog box to view or modify the description of default pipe.</span></span> <span data-ttu-id="1cedc-104">Per connettersi a una pipe diversa, digitarne il nome nella casella **Pipe predefinita** .</span><span class="sxs-lookup"><span data-stu-id="1cedc-104">To connect to a different pipe, type the pipe in the **Default Pipe** box.</span></span> <span data-ttu-id="1cedc-105">Per ulteriori informazioni sulle stringhe di connessione, vedere [Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md).</span><span class="sxs-lookup"><span data-stu-id="1cedc-105">For more information about connection strings, see [Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1cedc-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1cedc-106">Options</span></span>  
 <span data-ttu-id="1cedc-107">**Pipe predefinita**</span><span class="sxs-lookup"><span data-stu-id="1cedc-107">**Default Pipe**</span></span>  
 <span data-ttu-id="1cedc-108">Specifica la pipe predefinita usata dalla libreria di rete Named Pipes per tentare la connessione all'istanza di destinazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cedc-108">Specifies the default pipe the Named Pipes Net-library will use to attempt to connect to the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1cedc-109">Per impostazione predefinita, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in ascolto su: `\\.\pipe\sql\query`</span><span class="sxs-lookup"><span data-stu-id="1cedc-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on: `\\.\pipe\sql\query`</span></span>  
  
 <span data-ttu-id="1cedc-110">Per connettersi alla pipe predefinita, immettere `sql\query`</span><span class="sxs-lookup"><span data-stu-id="1cedc-110">To connect to the default pipe, enter `sql\query`</span></span>  
  
 <span data-ttu-id="1cedc-111">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="1cedc-111">**Enabled**</span></span>  
 <span data-ttu-id="1cedc-112">I valori possibili sono **Sì** e **No**.</span><span class="sxs-lookup"><span data-stu-id="1cedc-112">Possible values are **Yes** and **No**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cedc-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cedc-113">See Also</span></span>  
 [<span data-ttu-id="1cedc-114">Scelta di un protocollo di rete</span><span class="sxs-lookup"><span data-stu-id="1cedc-114">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
