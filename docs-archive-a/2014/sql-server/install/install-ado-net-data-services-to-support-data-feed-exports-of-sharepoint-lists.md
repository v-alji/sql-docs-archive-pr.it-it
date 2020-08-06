---
title: Installare ADO.NET Data Services per supportare esportazioni di feed di dati di elenchi SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: f32527ae-f623-4e08-adfb-6d3262f5c2ac
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: fb47804daee38427f48baefdf3997edda5fb90b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626477"
---
# <a name="install-adonet-data-services-to-support-data-feed-exports-of-sharepoint-lists"></a><span data-ttu-id="81fac-102">Installare ADO.NET Data Services per supportare esportazioni di feed di dati di elenchi SharePoint</span><span class="sxs-lookup"><span data-stu-id="81fac-102">Install ADO.NET Data Services to support data feed exports of SharePoint lists</span></span>
  <span data-ttu-id="81fac-103">ADO.NET Data Services è necessario per un'esportazione dei feed di dati di elenchi SharePoint.</span><span class="sxs-lookup"><span data-stu-id="81fac-103">ADO.NET Data Services is required for a data feed export of SharePoint lists.</span></span> <span data-ttu-id="81fac-104">SharePoint 2010 non include questo componente nel programma di installazione essenziale di SharePoint, pertanto è necessario installarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="81fac-104">SharePoint 2010 does not include this component in the SharePoint Prerequisite Installer program, so you must install it manually.</span></span>  
  
 <span data-ttu-id="81fac-105">Senza questo prerequisito, si otterrà l'errore seguente quando si tenta di utilizzare un elenco SharePoint esportato come feed di dati: "Per motivi di sicurezza, la dichiarazione DTD non è consentita in questo documento XML.</span><span class="sxs-lookup"><span data-stu-id="81fac-105">Without this prerequisite, you will get the following error when you attempt to use a SharePoint list that was exported as a data feed: "For security reasons DTD is prohibited in this XML document.</span></span> <span data-ttu-id="81fac-106">Per abilitare l'elaborazione DTD impostare la proprietà ProhibitDtd in XmlReaderSettings su false e passare le impostazioni al metodo XmlReader.Create".</span><span class="sxs-lookup"><span data-stu-id="81fac-106">To enable DTD processing set the ProhibitDtd property on XmlReaderSettings to false and pass the settings into XmlReader.Create method."</span></span>  
  
 <span data-ttu-id="81fac-107">Utilizzare le istruzioni seguenti per installare ADO.NET Data Services in ogni server SharePoint per il quale si desidera l'esportazione degli elenchi come feed di dati.</span><span class="sxs-lookup"><span data-stu-id="81fac-107">Use the following instructions to install ADO.NET Data Services on every SharePoint server for which you want to allow lists to be exported as data feeds.</span></span>  
  
### <a name="download-and-install-adonet-data-services"></a><span data-ttu-id="81fac-108">Scaricare e installare ADO.NET Data Services</span><span class="sxs-lookup"><span data-stu-id="81fac-108">Download and install ADO.NET Data Services</span></span>  
  
1.  <span data-ttu-id="81fac-109">Vedere la documentazione sui requisiti hardware e software per SharePoint 2010, [requisiti hardware e software (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734)</span><span class="sxs-lookup"><span data-stu-id="81fac-109">Go to the hardware and software requirements documentation for SharePoint 2010, [Hardware and Software Requirements (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734)</span></span>  
  
2.  <span data-ttu-id="81fac-110">Per **accedere al software applicabile**, trovare il collegamento per ADO.NET Data Services 3,5 che corrisponde al sistema operativo in uso (windows Server 2008 SP2 o windows Server 2008 R2).</span><span class="sxs-lookup"><span data-stu-id="81fac-110">In **Access to applicable software**, find the link for ADO.NET Data Services 3.5 that corresponds to the operating system you are using (either Windows Server 2008 SP2 or Windows Server 2008 R2).</span></span>  
  
3.  <span data-ttu-id="81fac-111">Fare clic sul collegamento ed eseguire il programma di installazione che consente di installare il servizio.</span><span class="sxs-lookup"><span data-stu-id="81fac-111">Click the link and run the setup program that installs the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81fac-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81fac-112">See Also</span></span>  
 [<span data-ttu-id="81fac-113">Installazione di PowerPivot per SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="81fac-113">PowerPivot for SharePoint 2010 Installation</span></span>](../../../2014/sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
