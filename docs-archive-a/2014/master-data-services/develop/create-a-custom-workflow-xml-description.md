---
title: Descrizione XML del flusso di lavoro personalizzato (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: e267e5f4-38bb-466d-82e8-871eabeec07e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 77906426ddb901ec422367bf30aabef2e532ad06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638435"
---
# <a name="custom-workflow-xml-description-master-data-services"></a><span data-ttu-id="7e62b-102">Descrizione XML del flusso di lavoro personalizzato (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="7e62b-102">Custom Workflow XML Description (Master Data Services)</span></span>
  <span data-ttu-id="7e62b-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] il metodo [Microsoft. MasterDataServices. WorkflowTypeExtender. IWorkflowTypeExtender. StartWorkflow \*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) viene chiamato dal servizio di integrazione del flusso di lavoro di SQL Server MDS all'avvio di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7e62b-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)], the [Microsoft.MasterDataServices.WorkflowTypeExtender.IWorkflowTypeExtender.StartWorkflow\*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) method is called by SQL Server MDS Workflow Integration Service when a workflow starts.</span></span> <span data-ttu-id="7e62b-104">Questo metodo riceve i metadati e i dati sull'elemento che ha attivato la regola business del flusso di lavoro come blocco di XML.</span><span class="sxs-lookup"><span data-stu-id="7e62b-104">This method receives metadata and data about the item that triggered the workflow business rule as a block of XML.</span></span> <span data-ttu-id="7e62b-105">Per un esempio di codice che implementa un gestore del flusso di lavoro, vedere [Creare un flusso di lavoro personalizzato - Esempio &#40;Master Data Services&#41;](create-a-custom-workflow-example.md).</span><span class="sxs-lookup"><span data-stu-id="7e62b-105">For example code that implements a workflow handler, see [Custom Workflow Example &#40;Master Data Services&#41;](create-a-custom-workflow-example.md).</span></span>  
  
 <span data-ttu-id="7e62b-106">Nell'esempio seguente viene illustrato il possibile aspetto del codice XML inviato al gestore del flusso di lavoro:</span><span class="sxs-lookup"><span data-stu-id="7e62b-106">The following example shows what the XML that is sent to the workflow handler might look like:</span></span>  
  
```scr  
<ExternalAction>  
  <Type>TEST</Type>  
  <SendData>1</SendData>  
  <Server_URL>This is my test!</Server_URL>  
  <Action_ID>Test Workflow</Action_ID>  
  <Model_ID>5</Model_ID>  
  <Model_Name>Customer</Model_Name>  
  <Entity_ID>34</Entity_ID>  
  <Entity_Name>Customer</Entity_Name>  
  <Version_ID>8</Version_ID>  
  <MemberType_ID>1</MemberType_ID>  
  <Member_ID>12</Member_ID>  
  <MemberData>  
    <ID>12</ID>  
    <Version_ID>8</Version_ID>  
    <ValidationStatus_ID>3</ValidationStatus_ID>  
    <ChangeTrackingMask>0</ChangeTrackingMask>  
    <EnterDTM>2011-02-25T20:16:36.650</EnterDTM>  
    <EnterUserID>2</EnterUserID>  
    <EnterUserName>MyUserName</EnterUserName>  
    <EnterUserMuid>EEF91D48-B673-4D83-B95F-5A363C11DE91</EnterUserMuid>  
    <EnterVersionId>8</EnterVersionId>  
    <EnterVersionName>VERSION_1</EnterVersionName>  
    <EnterVersionMuid>52B788C2-2750-4651-9DB0-2CB05A88AA5A</EnterVersionMuid>  
    <LastChgDTM>2011-02-25T20:16:36.650</LastChgDTM>  
    <LastChgUserID>2</LastChgUserID>  
    <LastChgUserName>MyUserName</LastChgUserName>  
    <LastChgUserMuid>EEF91D48-B673-4D83-B95F-5A363C11DE91</LastChgUserMuid>  
    <LastChgVersionId>8</LastChgVersionId>  
    <LastChgVersionName>VERSION_1</LastChgVersionName>  
    <LastChgVersionMuid>52B788C2-2750-4651-9DB0-2CB05A88AA5A</LastChgVersionMuid>  
    <Name>Test Customer</Name>  
    <Code>TC</Code>  
  </MemberData>  
</ExternalAction>  
```  
  
 <span data-ttu-id="7e62b-107">Nella tabella seguente vengono descritti alcuni dei tag contenuti nel codice XML:</span><span class="sxs-lookup"><span data-stu-id="7e62b-107">The following table describes some of the tags contained in this XML:</span></span>  
  
|<span data-ttu-id="7e62b-108">Tag</span><span class="sxs-lookup"><span data-stu-id="7e62b-108">Tag</span></span>|<span data-ttu-id="7e62b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e62b-109">Description</span></span>|  
|---------|-----------------|  
|\<Type>|<span data-ttu-id="7e62b-110">Testo immesso nella casella di testo **Tipo di flusso di lavoro** in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] per identificare l'assembly del flusso di lavoro personalizzato da caricare.</span><span class="sxs-lookup"><span data-stu-id="7e62b-110">The text you entered in the **Workflow type** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] to identify which custom workflow assembly to load.</span></span>|  
|\<SendData>|<span data-ttu-id="7e62b-111">Valore booleano gestito dalla casella di controllo **Includi dati membro nel messaggio** in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e62b-111">A Boolean value controlled by the **Include member data in the message** checkbox in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span> <span data-ttu-id="7e62b-112">Il valore 1 indica che la \<MemberData> sezione viene inviata; in caso contrario, la \<MemberData> sezione non viene inviata.</span><span class="sxs-lookup"><span data-stu-id="7e62b-112">A value of 1 means that the \<MemberData> section is sent; otherwise the \<MemberData> section is not sent.</span></span>|  
|<span data-ttu-id="7e62b-113"><Server_URL></span><span class="sxs-lookup"><span data-stu-id="7e62b-113"><Server_URL></span></span>|<span data-ttu-id="7e62b-114">Testo immesso nella casella di testo **Sito flusso di lavoro** in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e62b-114">The text you entered in the **Workflow site** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>|  
|<span data-ttu-id="7e62b-115"><Action_ID></span><span class="sxs-lookup"><span data-stu-id="7e62b-115"><Action_ID></span></span>|<span data-ttu-id="7e62b-116">Testo immesso nella casella di testo **Nome flusso di lavoro** in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e62b-116">The text you entered in the **Workflow name** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>|  
|\<MemberData>|<span data-ttu-id="7e62b-117">Contiene i dati del membro che ha attivato l'azione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7e62b-117">Contains the data of the member that triggered the workflow action.</span></span> <span data-ttu-id="7e62b-118">Questa operazione viene inclusa solo se il valore di \<SendData> è 1.</span><span class="sxs-lookup"><span data-stu-id="7e62b-118">This is included only if the value of \<SendData> is 1.</span></span>|  
|\<Enter*xxx*>|<span data-ttu-id="7e62b-119">Questo set di tag contiene i metadati sulla creazione del membro, ad esempio il momento e l'autore della creazione.</span><span class="sxs-lookup"><span data-stu-id="7e62b-119">This set of tags contains metadata about the creation of the member, such as when it was created and who created it.</span></span>|  
|\<LastChg*xxx*>|<span data-ttu-id="7e62b-120">Questo set di tag contiene i metadati sull'ultima modifica apportata al membro, ad esempio il momento e l'autore dell'esecuzione della modifica.</span><span class="sxs-lookup"><span data-stu-id="7e62b-120">This set of tags contains metadata about the last change made to the member, such as when the change was made and who made it.</span></span>|  
|\<Name>|<span data-ttu-id="7e62b-121">Primo attributo del membro modificato.</span><span class="sxs-lookup"><span data-stu-id="7e62b-121">The first attribute of the member that was changed.</span></span> <span data-ttu-id="7e62b-122">Questo membro di esempio contiene solo gli attributi Name e Code.</span><span class="sxs-lookup"><span data-stu-id="7e62b-122">This example member contains only Name and Code attributes.</span></span>|  
|\<Code>|<span data-ttu-id="7e62b-123">Attributo successivo del membro modificato.</span><span class="sxs-lookup"><span data-stu-id="7e62b-123">The next attribute of the member that was changed.</span></span> <span data-ttu-id="7e62b-124">Se il membro di esempio contiene più attributi, essi vengono specificati dopo questo.</span><span class="sxs-lookup"><span data-stu-id="7e62b-124">If this example member contained more attributes, they would follow this one.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e62b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e62b-125">See Also</span></span>  
 <span data-ttu-id="7e62b-126">[Creare un &#40;del flusso di lavoro personalizzato Master Data Services&#41;](create-a-custom-workflow-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="7e62b-126">[Create a Custom Workflow &#40;Master Data Services&#41;](create-a-custom-workflow-master-data-services.md) </span></span>  
 [<span data-ttu-id="7e62b-127">Esempio di flusso di lavoro personalizzato &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7e62b-127">Custom Workflow Example &#40;Master Data Services&#41;</span></span>](create-a-custom-workflow-example.md)  
  
  
