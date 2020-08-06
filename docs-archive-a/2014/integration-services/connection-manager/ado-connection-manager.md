---
title: Gestione connessione ADO | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], ADO
- connection managers [Integration Services], ADO
- ADO connection manager [Integration Services]
ms.assetid: 490418bc-5ef1-41b8-a9c8-de38aa96e0f6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb4b667733f81eebbaf2b6a2ab9b205c09fe2c66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636357"
---
# <a name="ado-connection-manager"></a><span data-ttu-id="0ea2c-102">Gestione connessione ADO</span><span class="sxs-lookup"><span data-stu-id="0ea2c-102">ADO Connection Manager</span></span>
  <span data-ttu-id="0ea2c-103">Una gestione connessione ADO consente la connessione di un pacchetto a oggetti ADO (ActiveX Data Objects), ad esempio un recordset.</span><span class="sxs-lookup"><span data-stu-id="0ea2c-103">An ADO connection manager enables a package to connect to ActiveX Data Objects (ADO) objects, such as a recordset.</span></span> <span data-ttu-id="0ea2c-104">Questa gestione connessione viene in genere usata nelle attività personalizzate create con versioni precedenti di un linguaggio, ad esempio Microsoft Visual Basic 6.0, o in attività personalizzate che fanno parte di un'applicazione esistente che usa ADO per connettersi a un'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="0ea2c-104">This connection manager is typically used in custom tasks written in an earlier version of a language, such as Microsoft Visual Basic 6.0, or in custom tasks that are part of an existing application that uses ADO to connect to a data source.</span></span>  
  
 <span data-ttu-id="0ea2c-105">Quando si aggiunge una gestione connessione ADO a un pacchetto, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Crea una gestione connessione che in fase di esecuzione verrà risolta in una connessione ADO, imposta le proprietà della gestione connessione e la aggiunge alla `Connections` raccolta del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0ea2c-105">When you add an ADO connection manager to a package, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an ADO connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="0ea2c-106">La proprietà `ConnectionManagerType` della gestione connessione viene impostata su `ADO`.</span><span class="sxs-lookup"><span data-stu-id="0ea2c-106">The `ConnectionManagerType` property of the connection manager is set to `ADO`.</span></span>  
  
## <a name="troubleshooting-the-ado-connection-manager"></a><span data-ttu-id="0ea2c-107">Risoluzione dei problemi relativi alla gestione connessione ADO</span><span class="sxs-lookup"><span data-stu-id="0ea2c-107">Troubleshooting the ADO Connection Manager</span></span>  
 <span data-ttu-id="0ea2c-108">Durante la lettura da parte di una gestione connessione ADO, alcuni tipi di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] relativi alle date genereranno i risultati mostrati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0ea2c-108">When being read by an ADO connection manager, certain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date data types will generate the results shown in the following table.</span></span>  
  
|<span data-ttu-id="0ea2c-109">Tipo di dati di SQL Server</span><span class="sxs-lookup"><span data-stu-id="0ea2c-109">SQL Server Data type</span></span>|<span data-ttu-id="0ea2c-110">Risultato</span><span class="sxs-lookup"><span data-stu-id="0ea2c-110">Result</span></span>|  
|--------------------------|------------|  
|<span data-ttu-id="0ea2c-111">`time`, `datetimeoffset`</span><span class="sxs-lookup"><span data-stu-id="0ea2c-111">`time`, `datetimeoffset`</span></span>|<span data-ttu-id="0ea2c-112">L'esecuzione del pacchetto non viene completata correttamente, a meno che non vengano utilizzati comandi SQL con parametri.</span><span class="sxs-lookup"><span data-stu-id="0ea2c-112">The package fails unless the package uses parameterized SQL commands.</span></span> <span data-ttu-id="0ea2c-113">È necessario servirsi dell'attività Esegui SQL nel pacchetto per utilizzare i comandi SQL con parametri.</span><span class="sxs-lookup"><span data-stu-id="0ea2c-113">To use parameterized SQL commands, use the Execute SQL Task in your package.</span></span> <span data-ttu-id="0ea2c-114">Per altre informazioni, vedere [Attività Esegui SQL](../control-flow/execute-sql-task.md) e [Parametri e codici restituiti nell'attività Esegui SQL](../parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="0ea2c-114">For more information, see [Execute SQL Task](../control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>|  
|`datetime2`|<span data-ttu-id="0ea2c-115">La gestione connessione ADO tronca il valore relativo ai millisecondi.</span><span class="sxs-lookup"><span data-stu-id="0ea2c-115">The ADO connection manager truncates the millisecond value.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="0ea2c-116">Per altre informazioni sui tipi di dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e sul relativo mapping nei tipi di dati [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], vedere [Tipi di dati &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) e [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="0ea2c-116">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types and how they map to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) and [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="configuring-the-ado-connection-manager"></a><span data-ttu-id="0ea2c-117">Configurazione della gestione connessione ADO</span><span class="sxs-lookup"><span data-stu-id="0ea2c-117">Configuring the ADO Connection Manager</span></span>  
 <span data-ttu-id="0ea2c-118">Per configurare una gestione connessione ADO, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="0ea2c-118">You can configure an ADO connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="0ea2c-119">Specificare una stringa di connessione configurata in modo da soddisfare i requisiti del provider selezionato.</span><span class="sxs-lookup"><span data-stu-id="0ea2c-119">Provide a specific connection string configured to meet the requirements of the selected provider.</span></span>  
  
-   <span data-ttu-id="0ea2c-120">Se richiesto dal provider, includere il nome dell'origine dei dati a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="0ea2c-120">Depending on the provider, include the name of the data source to connect to.</span></span>  
  
-   <span data-ttu-id="0ea2c-121">Specificare le credenziali di sicurezza come previsto dal provider selezionato.</span><span class="sxs-lookup"><span data-stu-id="0ea2c-121">Provide security credentials as appropriate for the selected provider.</span></span>  
  
-   <span data-ttu-id="0ea2c-122">Indicare se la connessione creata dalla gestione connessione deve essere mantenuta in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0ea2c-122">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
 <span data-ttu-id="0ea2c-123">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="0ea2c-123">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="0ea2c-124">Per ulteriori informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="0ea2c-124">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="0ea2c-125">Configura gestione connessione OLE DB</span><span class="sxs-lookup"><span data-stu-id="0ea2c-125">Configure OLE DB Connection Manager</span></span>](ole-db-connection-manager.md)  
  
 <span data-ttu-id="0ea2c-126">Per informazioni sulla configurazione di una gestione connessione a livello di programmazione, vedere l'articolo relativo a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Aggiunta di connessioni a livello di programmazione](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="0ea2c-126">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ea2c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ea2c-127">See Also</span></span>  
 [<span data-ttu-id="0ea2c-128">Connessioni in Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="0ea2c-128">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
