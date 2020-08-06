---
title: 'Esercitazione: Introduzione al motore di database | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tutorials [connecting]
- tutorials [Database Engine]
- unable to connect [SQL Server]
- failure to connect [SQL Server]
- connecting tutorial [SQL Server]
ms.assetid: 655e709b-346b-469c-bddc-a5a0238d07e0
author: rothja
ms.author: jroth
ms.openlocfilehash: aaa1fb21c026d064c2b14db73aadc2b82e9c15d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637121"
---
# <a name="tutorial-getting-started-with-the-database-engine"></a><span data-ttu-id="f9115-102">Esercitazione: Introduzione al motore di database</span><span class="sxs-lookup"><span data-stu-id="f9115-102">Tutorial: Getting Started with the Database Engine</span></span>
  <span data-ttu-id="f9115-103">Benvenuto a questa esercitazione introduttiva su [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f9115-103">Welcome to the Getting Started with the [!INCLUDE[ssDE](../includes/ssde-md.md)] tutorial.</span></span> <span data-ttu-id="f9115-104">Questa esercitazione è destinata agli utenti che non hanno familiarità con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e hanno installato [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o [!INCLUDE[ssExpress](../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9115-104">This tutorial is intended for users who are new to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and who have installed [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssExpress](../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="f9115-105">In questa breve esercitazione verranno fornite informazioni per iniziare a utilizzare [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9115-105">This brief tutorial helps you get started using the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="f9115-106">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="f9115-106">What You Will Learn</span></span>  
 <span data-ttu-id="f9115-107">In questa esercitazione vengono descritte le procedure per connettersi al [!INCLUDE[ssDE](../includes/ssde-md.md)] tramite [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] nel computer locale e in un altro computer.</span><span class="sxs-lookup"><span data-stu-id="f9115-107">This tutorial shows you how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] on both the local computer and from another computer.</span></span>  
  
 <span data-ttu-id="f9115-108">L'esercitazione è suddivisa in due lezioni:</span><span class="sxs-lookup"><span data-stu-id="f9115-108">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="f9115-109">Lezione 1: Connessione al motore di database</span><span class="sxs-lookup"><span data-stu-id="f9115-109">Lesson 1: Connecting to the Database Engine</span></span>](lesson-1-connecting-to-the-database-engine.md)  
 <span data-ttu-id="f9115-110">In questa lezione verranno descritte le procedure per connettersi a [!INCLUDE[ssDE](../includes/ssde-md.md)] e consentire ad altre persone di connettersi.</span><span class="sxs-lookup"><span data-stu-id="f9115-110">In this lesson, you will learn how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] and enable additional people to connect.</span></span>  
  
 [<span data-ttu-id="f9115-111">Lezione 2: Connessione da un altro computer</span><span class="sxs-lookup"><span data-stu-id="f9115-111">Lesson 2: Connecting from Another Computer</span></span>](lesson-2-connecting-from-another-computer.md)  
 <span data-ttu-id="f9115-112">In questa lezione verranno descritte le procedure per connettersi a [!INCLUDE[ssDE](../includes/ssde-md.md)] da un secondo computer, incluse le impostazioni per l'abilitazione di protocolli, la configurazione di porte e la configurazione del firewall.</span><span class="sxs-lookup"><span data-stu-id="f9115-112">In this lesson, you will learn how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] from a second computer, including enabling protocols, configuring ports, and configuring firewall settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9115-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f9115-113">Requirements</span></span>  
 <span data-ttu-id="f9115-114">Per questa esercitazione non sono richieste nozioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="f9115-114">This tutorial has no knowledge prerequisites.</span></span>  
  
 <span data-ttu-id="f9115-115">Per utilizzare l'esercitazione è necessario che nel sistema siano installati i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9115-115">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]<span data-ttu-id="f9115-116">.</span><span class="sxs-lookup"><span data-stu-id="f9115-116">.</span></span> [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] <span data-ttu-id="f9115-117">può essere installato eseguendo il programma di installazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o scaricandolo e installandolo dall' [Area download Microsoft](https://go.microsoft.com/fwlink/?LinkId=144346).</span><span class="sxs-lookup"><span data-stu-id="f9115-117">can be installed by running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] setup or by downloading and installing from [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=144346).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9115-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9115-118">See Also</span></span>  
 [<span data-ttu-id="f9115-119">Esercitazione su SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f9115-119">Tutorial: SQL Server Management Studio</span></span>](../ssms/tutorials/tutorial-sql-server-management-studio.md)  
  
  
