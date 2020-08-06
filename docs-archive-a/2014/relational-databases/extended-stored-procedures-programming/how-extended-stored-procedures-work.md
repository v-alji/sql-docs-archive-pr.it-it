---
title: Funzionamento delle stored procedure estese | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], about extended stored procedures
ms.assetid: 6e946d8c-3268-4b59-8a1c-1637909cd701
author: rothja
ms.author: jroth
ms.openlocfilehash: 75082fed6b70c214b4f55b85034ffa371824d24f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635604"
---
# <a name="how-extended-stored-procedures-work"></a><span data-ttu-id="3282f-102">Funzionamento delle stored procedure estese</span><span class="sxs-lookup"><span data-stu-id="3282f-102">How Extended Stored Procedures Work</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="3282f-103">Utilizzare invece la funzionalità di integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="3282f-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="3282f-104">Il funzionamento di una stored procedure estesa è il seguente:</span><span class="sxs-lookup"><span data-stu-id="3282f-104">The process by which an extended stored procedure works is:</span></span>  
  
1.  <span data-ttu-id="3282f-105">Quando un client esegue una stored procedure estesa, la richiesta viene trasmessa nel formato TDS (Tabular Data Stream) o Simple Object Access Protocol (SOAP) dall'applicazione client a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3282f-105">When a client executes an extended stored procedure, the request is transmitted in tabular data stream (TDS) or Simple Object Access Protocol (SOAP) format from the client application to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3282f-106">esegue la ricerca della DLL associata alla stored procedure estesa e, se non è già caricata, la carica.</span><span class="sxs-lookup"><span data-stu-id="3282f-106">searches for the DLL associated with the extended stored procedure, and loads the DLL if it is not already loaded.</span></span>  
  
3.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3282f-107">chiama la stored procedure estesa richiesta (implementata come funzione all'interno della DLL).</span><span class="sxs-lookup"><span data-stu-id="3282f-107">calls the requested extended stored procedure (implemented as a function inside the DLL).</span></span>  
  
4.  <span data-ttu-id="3282f-108">La stored procedure estesa passa set di risultati e restituisce parametri al server mediante l'API Stored procedure estesa.</span><span class="sxs-lookup"><span data-stu-id="3282f-108">The extended stored procedure passes result sets and return parameters back to the server by through the Extended Stored Procedure API.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3282f-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3282f-109">See Also</span></span>  
 [<span data-ttu-id="3282f-110">Programmazione di stored procedure estese del Motore di database</span><span class="sxs-lookup"><span data-stu-id="3282f-110">Database Engine Extended Stored Procedure Programming</span></span>](../database-engine-extended-stored-procedure-programming.md)  
  
  
