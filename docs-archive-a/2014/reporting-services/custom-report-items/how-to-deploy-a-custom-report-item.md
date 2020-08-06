---
title: 'Procedura: Distribuire un elemento del report personalizzato | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, deploying
ms.assetid: 80e97b0d-e355-4240-aebd-08cbc84089ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 66519610526478caadeb41b48c9823414e88d5d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725312"
---
# <a name="how-to-deploy-a-custom-report-item"></a><span data-ttu-id="51daf-102">Procedura: Distribuire un elemento del report personalizzato</span><span class="sxs-lookup"><span data-stu-id="51daf-102">How to: Deploy a Custom Report Item</span></span>
  <span data-ttu-id="51daf-103">Per distribuire un elemento del report personalizzato in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], è necessario modificare i file di configurazione del server di report e copiare gli assembly del componente runtime e della fase di progettazione nelle cartelle appropriate dell'applicazione sia per Progettazione report sia per il server di report.</span><span class="sxs-lookup"><span data-stu-id="51daf-103">To deploy a custom report item in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must modify the report server configuration files and copy the design-time and run-time component assemblies into the appropriate application folders for both Report Designer and the report server.</span></span>  
  
### <a name="to-deploy-a-custom-report-item"></a><span data-ttu-id="51daf-104">Per distribuire un elemento del report personalizzato</span><span class="sxs-lookup"><span data-stu-id="51daf-104">To deploy a custom report item</span></span>  
  
1.  <span data-ttu-id="51daf-105">Modificare il file Rsreportdesigner.config per configurare i componenti runtime e della modalità progettazione del report personalizzato da utilizzare nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="51daf-105">Edit the Rsreportdesigner.config file to configure the custom report item run-time and design-time components for use in the designer.</span></span> <span data-ttu-id="51daf-106">Si noti che la voce `ReportItemName` deve corrispondere all'attributo `CustomReportItemAttribute` utilizzato nella classe `CustomReportItemDesigner`.</span><span class="sxs-lookup"><span data-stu-id="51daf-106">Note that the `ReportItemName` entry must match the `CustomReportItemAttribute` attribute used in your `CustomReportItemDesigner` class.</span></span> <span data-ttu-id="51daf-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="51daf-107">For example:</span></span>  
  
    ```  
    <ReportItems>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsCRI,PolygonsCRI"/>  
    </ReportItems>  
    <ReportItemDesigner>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsDesigner, PolygonsDesigner" />  
    </ReportItemDesigner>  
    <ReportItemConverter>  
       <Converter Source="Chart" Target="Polygons" Type="PolygonsCRI.PolygonsConverter, PolygonsDesigner" />  
    </ReportItemConverter>  
    ```  
  
2.  <span data-ttu-id="51daf-108">Modificare il file Rsreportserver.config per registrare il componente runtime dell'elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="51daf-108">Edit the Rsreportserver.config file to register the custom report item run-time component.</span></span> <span data-ttu-id="51daf-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="51daf-109">For example:</span></span>  
  
    ```  
    <ReportItems>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsCRI,PolygonsCRI"/>  
    </ReportItems>  
    ```  
  
3.  <span data-ttu-id="51daf-110">Modificare il file Rsssrvpolicy.config per aggiungere una parola chiave `CodeGroup` che conceda le autorizzazioni appropriate all'elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="51daf-110">Edit the Rsssrvpolicy.config file to add a `CodeGroup` that grants the proper permissions to the custom report item.</span></span> <span data-ttu-id="51daf-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="51daf-111">For example:</span></span>  
  
    ```  
    <CodeGroup   
       class="UnionCodeGroup"   
       version="1"   
       PermissionSetName="FullTrust"  
       Description="This code group grants MyCustomReportItem.dll FullTrust permission. ">  
       <IMembershipCondition   
          class="UrlMembershipCondition"  
          version="1"  
       Url="C:\Program Files\Microsoft SQL Server\ MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin\MyCustomReportItem.dll" />  
    </CodeGroup>  
    ```  
  
4.  <span data-ttu-id="51daf-112">Copiare la DLL del componente runtime dell'elemento del report personalizzato nelle directory %Programmi%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies e \Programmi\Microsoft SQL Server\MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="51daf-112">Copy the custom report item run-time component DLL to the %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies and \Program Files\Microsoft SQL Server\MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin directories.</span></span>  
  
5.  <span data-ttu-id="51daf-113">Copiare la DLL del componente della modalità progettazione dell'elemento del report personalizzato nella directory %Programmi %\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="51daf-113">Copy the custom report item design-time component DLL to the %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51daf-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51daf-114">See Also</span></span>  
 <span data-ttu-id="51daf-115">[File di configurazione di Reporting Services](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="51daf-115">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="51daf-116">Librerie di classi dell'elemento del report personalizzato</span><span class="sxs-lookup"><span data-stu-id="51daf-116">Custom Report Item Class Libraries</span></span>](custom-report-item-class-libraries.md)  
  
  
