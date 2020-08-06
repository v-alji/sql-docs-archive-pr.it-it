---
title: Individuare la versione dello schema di definizione del report (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- XML schemas [Reporting Services]
- Report Definition Language, XML schema
- schemas [Reporting Services]
ms.assetid: 67954419-1b61-4481-a3b9-23b4ba7a5624
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 413a270a3722ddda1f418c748fa5b7fba50dfeea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716076"
---
# <a name="find-the-report-definition-schema-version-ssrs"></a><span data-ttu-id="6de51-102">Individuare la versione dello schema di definizione del report (SSRS)</span><span class="sxs-lookup"><span data-stu-id="6de51-102">Find the Report Definition Schema Version (SSRS)</span></span>
  <span data-ttu-id="6de51-103">Un file di definizione del report specifica lo spazio dei nomi RDL per la versione dello schema di definizione del report utilizzata per convalidare il file rdl.</span><span class="sxs-lookup"><span data-stu-id="6de51-103">A report definition file specifies the RDL namespace for the version of the report definition schema that is used to validate the rdl file.</span></span> <span data-ttu-id="6de51-104">Quando si apre un file con estensione rdl in un ambiente di creazione di report, ad esempio Progettazione report in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] o Generatore report, se il report è creato per uno spazio dei nomi precedente, viene automaticamente creato un file di backup e il report viene aggiornato allo spazio dei nomi corrente.</span><span class="sxs-lookup"><span data-stu-id="6de51-104">When you open an .rdl file in a report authoring environment such as Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or Report Builder, if the report was created for a previous namespace, a backup file is automatically created, and the report is upgraded to the current namespace.</span></span> <span data-ttu-id="6de51-105">Salvando la definizione del report aggiornata, si salva il file con estensione rdl convertito.</span><span class="sxs-lookup"><span data-stu-id="6de51-105">If you save the upgraded report definition, you have saved the converted .rdl file.</span></span> <span data-ttu-id="6de51-106">Questo è l'unico modo per aggiornare una definizione del report.</span><span class="sxs-lookup"><span data-stu-id="6de51-106">This is the only way to upgrade a report definition.</span></span> <span data-ttu-id="6de51-107">La definizione del report non viene aggiornata su un server di report.</span><span class="sxs-lookup"><span data-stu-id="6de51-107">The report definition itself is not upgraded on a report server.</span></span> <span data-ttu-id="6de51-108">Il report compilato viene aggiornato su un server di report.</span><span class="sxs-lookup"><span data-stu-id="6de51-108">The compiled report is upgraded on a report server.</span></span> <span data-ttu-id="6de51-109">Per altre informazioni, vedere [Upgrade Reports](../install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="6de51-109">For more information, see [Upgrade Reports](../install-windows/upgrade-reports.md).</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-of-a-report"></a><span data-ttu-id="6de51-110">Procedura: Identificazione della versione di schema RDL di un report</span><span class="sxs-lookup"><span data-stu-id="6de51-110">How to: Identify the RDL Schema Version of a Report</span></span>  
  
1.  <span data-ttu-id="6de51-111">Aprire il file del report con estensione rdl in un'applicazione, ad esempio Blocco note o XML Blocco note 2007, nella quale è possibile visualizzare file in formato xml.</span><span class="sxs-lookup"><span data-stu-id="6de51-111">Open the report .rdl file in an application such as Notepad or XML Notepad 2007 in which you can view the xml.</span></span>  
  
     <span data-ttu-id="6de51-112">L'elemento Report XML specifica lo spazio dei nomi dello schema.</span><span class="sxs-lookup"><span data-stu-id="6de51-112">The XML Report element specifies the schema namespace.</span></span> <span data-ttu-id="6de51-113">L'elemento Report seguente, ad esempio, specifica lo spazio dei nomi per Progettazione report e lo spazio dei nomi per la definizione del report.</span><span class="sxs-lookup"><span data-stu-id="6de51-113">For example, the following Report element specifies the namespace for Report Designer and the namespace for the report definition.</span></span>  
  
    ```  
    <Report xmlns:rd=https://schemas.microsoft.com/SQLServer/reporting/reportdesigner   
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition">  
    ```  
  
     <span data-ttu-id="6de51-114">Lo spazio dei nomi della definizione del report viene specificato dall'URL seguente: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`.</span><span class="sxs-lookup"><span data-stu-id="6de51-114">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`.</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-of-report-designer"></a><span data-ttu-id="6de51-115">Procedura: Identificazione della versione di schema RDL di Progettazione report</span><span class="sxs-lookup"><span data-stu-id="6de51-115">How to: Identify the RDL Schema Version of Report Designer</span></span>  
  
1.  <span data-ttu-id="6de51-116">Apre un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="6de51-116">Open a new project.</span></span> <span data-ttu-id="6de51-117">La versione del progetto che si sceglie determina la versione dello schema RDL.</span><span class="sxs-lookup"><span data-stu-id="6de51-117">The version of the project that you choose determines the version of the RDL schema.</span></span> <span data-ttu-id="6de51-118">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]sono supportate più versioni dello schema.</span><span class="sxs-lookup"><span data-stu-id="6de51-118">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], more than one schema version is supported.</span></span> <span data-ttu-id="6de51-119">Per altre informazioni, vedere [Distribuzione e supporto della versione in SQL Server Data Tools &#40;SSRS&#41;](../tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6de51-119">For more information, see [Deployment and Version Support in SQL Server Data Tools &#40;SSRS&#41;](../tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="6de51-120">Dal menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="6de51-120">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="6de51-121">Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento** .</span><span class="sxs-lookup"><span data-stu-id="6de51-121">The **Add New Item** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="6de51-122">Nel riquadro **Modelli** fare clic su **Report**.</span><span class="sxs-lookup"><span data-stu-id="6de51-122">In the **Templates** pane, click **Report**.</span></span>  
  
4.  <span data-ttu-id="6de51-123">In **Nome**digitare un nome di report o accettare il nome predefinito.</span><span class="sxs-lookup"><span data-stu-id="6de51-123">In **Name**, type a report name or accept the default.</span></span>  
  
5.  <span data-ttu-id="6de51-124">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6de51-124">Click **Add**.</span></span> <span data-ttu-id="6de51-125">Progettazione report apre un nuovo report vuoto nella visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="6de51-125">Report Designer opens a new blank report in Design view.</span></span>  
  
6.  <span data-ttu-id="6de51-126">Scegliere **Codice** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="6de51-126">On the **View** menu, click **Code**.</span></span> <span data-ttu-id="6de51-127">La definizione del report viene visualizzata come file XML.</span><span class="sxs-lookup"><span data-stu-id="6de51-127">The report definition is displayed as an XML file.</span></span>  
  
     <span data-ttu-id="6de51-128">L'elemento Report XML specifica lo spazio dei nomi dello schema.</span><span class="sxs-lookup"><span data-stu-id="6de51-128">The XML Report element specifies the schema namespace.</span></span> <span data-ttu-id="6de51-129">L'elemento Report seguente, ad esempio, specifica lo spazio dei nomi per Progettazione report e lo spazio dei nomi per la definizione del report.</span><span class="sxs-lookup"><span data-stu-id="6de51-129">For example, the following Report element specifies the namespace for Report Designer and the namespace for the report definition.</span></span>  
  
    ```  
    <Report xmlns:rd=https://schemas.microsoft.com/SQLServer/reporting/reportdesigner  
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition">  
    ```  
  
     <span data-ttu-id="6de51-130">Lo spazio dei nomi della definizione del report viene specificato dall'URL seguente: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span><span class="sxs-lookup"><span data-stu-id="6de51-130">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-on-the-report-server"></a><span data-ttu-id="6de51-131">Procedura: Identificazione della versione di schema RDL nel server di report</span><span class="sxs-lookup"><span data-stu-id="6de51-131">How to: Identify the RDL Schema Version on the Report Server</span></span>  
  
-   <span data-ttu-id="6de51-132">In Gestione report digitare l'URL per il server di report.</span><span class="sxs-lookup"><span data-stu-id="6de51-132">In Report Manager, type the URL for the report server.</span></span> <span data-ttu-id="6de51-133">Ad esempio, nel seguente URL viene specificato un server di report sul computer locale:</span><span class="sxs-lookup"><span data-stu-id="6de51-133">For example, the following URL specifies a report server on the local computer:</span></span>  
  
     `http://localhost/reportserver/reportdefinition.xsd`  
  
     <span data-ttu-id="6de51-134">Il file con estensione xsd viene aperto nel browser.</span><span class="sxs-lookup"><span data-stu-id="6de51-134">The .xsd file opens in the browser.</span></span>  
  
     <span data-ttu-id="6de51-135">L'elemento XML Schema specifica lo spazio dei nomi dello schema.</span><span class="sxs-lookup"><span data-stu-id="6de51-135">The XML schema element specifies the schema namespace.</span></span> <span data-ttu-id="6de51-136">Nell'elemento schema seguente, ad esempio, sono specificati tre spazi dei nomi: il riferimento di targetNamespace usato internamente da [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], il riferimento xsd per lo schema stesso (xsd) e il riferimento della definizione del report.</span><span class="sxs-lookup"><span data-stu-id="6de51-136">For example, the following schema element specifies three namespaces: the targetNamespace reference that is used internally by [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], the xsd reference for the schema itself (xsd), and the report definition reference.</span></span>  
  
    ```  
    <xsd:schema   
    targetNamespace="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition"   
    xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition"   
    elementFormDefault="qualified">  
    ```  
  
     <span data-ttu-id="6de51-137">Lo spazio dei nomi della definizione del report viene specificato dall'URL seguente: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span><span class="sxs-lookup"><span data-stu-id="6de51-137">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de51-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6de51-138">See Also</span></span>  
 <span data-ttu-id="6de51-139">[Aggiornare i report](../install-windows/upgrade-reports.md) </span><span class="sxs-lookup"><span data-stu-id="6de51-139">[Upgrade Reports](../install-windows/upgrade-reports.md) </span></span>  
 [<span data-ttu-id="6de51-140">Report Definition Language &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6de51-140">Report Definition Language &#40;SSRS&#41;</span></span>](report-definition-language-ssrs.md)  
  
  
