---
title: Utilizzo di DiffGram per modificare i dati in SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- data deletions [SQLXML]
- updating data [SQLXML]
- DiffGrams [SQLXML]
- modifying data [SQLXML]
- .NET Framework [SQLXML], DiffGrams
- XML [SQLXML]
- database modifications [SQLXML]
- data updates [SQLXML]
- data modifications [SQLXML]
- record insertion [SQLXML]
- SQLXML, DiffGrams
- deleting data
- record updates [SQLXML]
- record deletions [SQLXML]
ms.assetid: 48b8a8f9-f3af-404f-8c84-f4c3703364d9
author: rothja
ms.author: jroth
ms.openlocfilehash: cc2e24304679a7648f18148eb45f33b9bf719a9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629293"
---
# <a name="using-diffgrams-to-modify-data-in-sqlxml-40"></a><span data-ttu-id="0773f-102">Utilizzo di DiffGram per la modifica dei dati in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="0773f-102">Using DiffGrams to Modify Data in SQLXML 4.0</span></span>
  <span data-ttu-id="0773f-103">Il formato DiffGram è stato introdotto nel componente **DataSet** del [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0773f-103">The DiffGram format is introduced in the **DataSet** component of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="0773f-104">In .NET Framework è possibile creare DiffGram e utilizzarli per modificare i dati delle tabelle di un database di Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0773f-104">Within the .NET Framework, you can create DiffGrams and use them to modify data in tables in a Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0773f-105">In questa sezione vengono forniti una breve introduzione ai Diffgram e alcuni esempi relativi al loro utilizzo.</span><span class="sxs-lookup"><span data-stu-id="0773f-105">This section provides a brief introduction to DiffGrams and examples of how to use them.</span></span> <span data-ttu-id="0773f-106">Si presuppone che l'utente abbia familiarità con i DiffGram in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0773f-106">It is assumed that you are familiar with DiffGrams in the .NET Framework.</span></span> <span data-ttu-id="0773f-107">La presente documentazione tratta principalmente dei problemi relativi ai Diffgram specifici di SQLXML.</span><span class="sxs-lookup"><span data-stu-id="0773f-107">In this documentation, the primary focus is on DiffGram issues that are specific to SQLXML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0773f-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0773f-108">In This Section</span></span>  
 [<span data-ttu-id="0773f-109">Introduzione ai DiffGram in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="0773f-109">Introduction to DiffGrams in SQLXML 4.0</span></span>](introduction-to-diffgrams-in-sqlxml-4-0.md)  
 <span data-ttu-id="0773f-110">Vengono fornite informazioni di base sui Diffgram.</span><span class="sxs-lookup"><span data-stu-id="0773f-110">Provides basic information about Diffgrams.</span></span>  
  
 [<span data-ttu-id="0773f-111">Esempi di DiffGram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="0773f-111">DiffGram Examples &#40;SQLXML 4.0&#41;</span></span>](diffgram-examples-sqlxml-4-0.md)  
 <span data-ttu-id="0773f-112">Vengono forniti esempi sull'utilizzo dei Diffgram.</span><span class="sxs-lookup"><span data-stu-id="0773f-112">Provides examples of using Diffgrams.</span></span>  
  
 [<span data-ttu-id="0773f-113">Esecuzione di un DiffGram utilizzando ADO &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="0773f-113">Executing a DiffGram by Using ADO &#40;SQLXML 4.0&#41;</span></span>](executing-a-diffgram-by-using-ado-sqlxml-4-0.md)  
 <span data-ttu-id="0773f-114">Viene fornito un esempio relativo all'esecuzione di un Diffgram con oggetti ADO (ActiveX Data Objects).</span><span class="sxs-lookup"><span data-stu-id="0773f-114">Provides an example of executing a Diffgram with ActiveX Data Objects (ADO).</span></span>  
  
 [<span data-ttu-id="0773f-115">Esecuzione di un DiffGram mediante classi gestite SQLXML</span><span class="sxs-lookup"><span data-stu-id="0773f-115">Executing a DiffGram by Using SQLXML Managed Classes</span></span>](../net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md)  
 <span data-ttu-id="0773f-116">Viene fornito un esempio relativo all'esecuzione di un Diffgram con classi gestite SQLXML.</span><span class="sxs-lookup"><span data-stu-id="0773f-116">Provides an example of executing a Diffgram with SQLXML Managed Classes.</span></span>  
  
  
