---
title: Installazione di Microsoft Connector per 1,1 SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3bfb9023-9597-4f59-9085-4b9057e7702e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ef96f38054f04e71de72bda0bbb12f8f003ef20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627890"
---
# <a name="installing-the-microsoft-connector-for-11-sap-bw"></a><span data-ttu-id="13024-102">Installazione di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="13024-102">Installing the Microsoft Connector for 1.1 SAP BW</span></span>
  <span data-ttu-id="13024-103">Per installare il [!INCLUDE[msCoName](../includes/msconame-md.md)] connettore 1,1 per SAP BW e la relativa documentazione, scaricare ed eseguire il pacchetto di Windows Installer dalla pagina Web SQL Server Feature Pack.</span><span class="sxs-lookup"><span data-stu-id="13024-103">To install the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW and its documentation, download and run the Windows installer package from the SQL Server Feature Pack Web page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="13024-104">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="13024-104">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="13024-105">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="13024-105">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="13024-106">L'estrazione di dati da SAP Netweaver BW richiede licenze SAP aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="13024-106">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="13024-107">Contattare SAP per verificare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="13024-107">Check with SAP to verify these requirements.</span></span>  
  
## <a name="required-sap-files"></a><span data-ttu-id="13024-108">File SAP richiesti</span><span class="sxs-lookup"><span data-stu-id="13024-108">Required SAP Files</span></span>  
 <span data-ttu-id="13024-109">Per usare il [!INCLUDE[msCoName](../includes/msconame-md.md)] connettore 1,1 per SAP BW, non è necessario installare il software front-end SAP (SAP GUI) nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="13024-109">To use the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW, you do not have to install the SAP Front End software (SAP GUI) on the local computer.</span></span>  
  
 <span data-ttu-id="13024-110">È tuttavia necessario copiare il file del connettore SAP .NET, librfc32.dll, nella sottocartella di sistema nella cartella Windows.</span><span class="sxs-lookup"><span data-stu-id="13024-110">However you must copy the SAP .NET connector file, librfc32.dll, into the system subfolder in the Windows folder.</span></span> <span data-ttu-id="13024-111">In genere, il percorso di questa cartella è **C:\Windows\system32**.</span><span class="sxs-lookup"><span data-stu-id="13024-111">(Typically, this folder location is **C:\Windows\system32**.)</span></span>  
  
## <a name="considerations-for-64-bit-computers"></a><span data-ttu-id="13024-112">Considerazioni relative ai computer a 64 bit</span><span class="sxs-lookup"><span data-stu-id="13024-112">Considerations for 64-bit Computers</span></span>  
 <span data-ttu-id="13024-113">Il [!INCLUDE[msCoName](../includes/msconame-md.md)] connettore 1,1 per SAP BW supporta completamente la versione a 64 bit di [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="13024-113">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW fully supports the 64-bit version of [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="13024-114">In un computer a 64 bit, il [!INCLUDE[msCoName](../includes/msconame-md.md)] connettore 1,1 per SAP BW presenta i requisiti aggiuntivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="13024-114">On a 64-bit computer, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW has the following additional requirements:</span></span>  
  
-   <span data-ttu-id="13024-115">Per eseguire pacchetti in modalità a 64 bit in qualsiasi sistema operativo Windows a 64 bit, copiare la versione a 64 bit del file SAP GUI, librfc32.dll, nella cartella **system32** della cartella Windows.</span><span class="sxs-lookup"><span data-stu-id="13024-115">To run packages in 64-bit mode on any 64-bit Windows operating system, copy the 64-bit version of the SAP GUI file, librfc32.dll, into the **system32** folder of the Windows folder.</span></span> <span data-ttu-id="13024-116">In genere, il percorso di questo file è **C:\Windows\system32**.</span><span class="sxs-lookup"><span data-stu-id="13024-116">(Typically, this file location is **C:\Windows\system32**.)</span></span>  
  
-   <span data-ttu-id="13024-117">Per eseguire pacchetti in modalità a 32 bit in qualsiasi sistema operativo Windows a 64 bit, copiare la versione del file SAP GUI, librfc32.dll, nella cartella **SysWow64** della cartella Windows.</span><span class="sxs-lookup"><span data-stu-id="13024-117">To run packages in 32-bit mode on any 64-bit Windows operating system, copy the SAP GUI file, librfc32.dll, into the **SysWow64** folder of the Windows folder.</span></span> <span data-ttu-id="13024-118">In genere, il percorso di questa cartella è **C:\Windows\SysWow64**.</span><span class="sxs-lookup"><span data-stu-id="13024-118">(Typically, this folder location is **C:\Windows\SysWow64**.)</span></span>  
  
  
