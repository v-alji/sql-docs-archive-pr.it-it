---
title: Individuazione dei tipi di parametri con valori di tabella
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- table-valued parameters, type discovery
ms.assetid: f55818c2-ebb5-4cf6-8c0c-0da41f592560
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ab8d837e4ddf74256e4bae70f772557ec8ff67f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716695"
---
# <a name="table-valued-parameter-type-discovery"></a><span data-ttu-id="f95b5-102">Individuazione del tipo di parametro con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="f95b5-102">Table-Valued Parameter Type Discovery</span></span>
  <span data-ttu-id="f95b5-103">Il consumer, ovvero l'applicazione client che utilizza il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client, può individuare il tipo di ogni parametro del comando se il testo del comando è stato assegnato al provider di OLE DB.</span><span class="sxs-lookup"><span data-stu-id="f95b5-103">The consumer-that is, the client application using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider-can discover the type of each command parameter if the command text has been given to the OLE DB Provider.</span></span> <span data-ttu-id="f95b5-104">Una volta noto il tipo di un parametro con valori di tabella, il consumer può individuare le informazioni sui metadati per ogni singola colonna del parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="f95b5-104">After the type of a table-valued parameter is known, the consumer can discover the metadata information for each individual column of the table-valued parameter.</span></span>  
  
 <span data-ttu-id="f95b5-105">Per la maggior parte dei tipi di parametri le informazioni sul tipo dei parametri di procedura sono supportate da ICommandWithParameters::GetParameterInfo.</span><span class="sxs-lookup"><span data-stu-id="f95b5-105">The type information of procedure parameters is supported by ICommandWithParameters::GetParameterInfo for most parameter types.</span></span> <span data-ttu-id="f95b5-106">A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , con l'introduzione di tipi definiti dall'utente e del `xml` tipo di dati, il metodo GetParameterInfo non è sufficiente a questo scopo perché non è stato possibile fornire informazioni sui tipi definiti dall'utente (nome, schema e catalogo) tramite ICommandWithParameters.</span><span class="sxs-lookup"><span data-stu-id="f95b5-106">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], with the introduction of user-defined types and the `xml` data type, the GetParameterInfo method was not sufficient for this purpose because it was not possible to provide user-defined type information (name, schema, and catalog) through ICommandWithParameters.</span></span> <span data-ttu-id="f95b5-107">Per fornire informazioni estese sul tipo è stata definita la nuova interfaccia ISSCommandWithParameters.</span><span class="sxs-lookup"><span data-stu-id="f95b5-107">A new interface, ISSCommandWithParameters, was defined to provide extended type information.</span></span>  
  
 <span data-ttu-id="f95b5-108">Per i parametri con valori di tabella, l'interfaccia ISSCommandWithParameters viene usata anche per individuare informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="f95b5-108">For table-valued parameters, you also use the ISSCommandWithParameters interface to discover detailed information.</span></span> <span data-ttu-id="f95b5-109">Il client chiama ISSCommandWithParameters::GetParameterInfo dopo aver preparato l'oggetto commando.</span><span class="sxs-lookup"><span data-stu-id="f95b5-109">The client calls ISSCommandWithParameters::GetParameterInfo after preparing the command object.</span></span> <span data-ttu-id="f95b5-110">Per i parametri con valori di tabella il membro *wType* della struttura DBPARAMINFO viene impostato su DBTYPE_TABLE dal provider.</span><span class="sxs-lookup"><span data-stu-id="f95b5-110">For table-valued parameters, the *wType* member of the DBPARAMINFO structure is set to DBTYPE_TABLE by the provider.</span></span> <span data-ttu-id="f95b5-111">Il valore del campo *ulParamSize* della struttura DBPARAMINFO è ~0.</span><span class="sxs-lookup"><span data-stu-id="f95b5-111">The *ulParamSize* field of DBPARAMINFO structure has a value of ~0.</span></span>  
  
 <span data-ttu-id="f95b5-112">Il consumer può quindi richiedere proprietà aggiuntive (nome del catalogo del tipo di parametro con valori di tabella, nome dello schema del tipo di parametro con valori di tabella, nome del tipo di parametro con valori di tabella, ordinamento colonne e colonne predefinite) mediante ISSCommandWithParameters::GetParameterProperties.</span><span class="sxs-lookup"><span data-stu-id="f95b5-112">The consumer would then request additional properties (table-valued parameter type catalog name, table-valued parameter type schema name, table-valued parameter type name, column ordering, and default columns) by using ISSCommandWithParameters::GetParameterProperties.</span></span>  
  
 <span data-ttu-id="f95b5-113">Una volta noto il nome del tipo, per recuperare informazioni sulle singole colonne il consumer deve chiamare IOpenRowset::OpenRowset oppure ottenere il set di righe DBSCHEMA_TABLE_TYPE_COLUMNS specificando il nome del tipo di parametro con valori di tabella come nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="f95b5-113">After the type name is known, to retrieve the individual column information the consumer must either call IOpenRowset::OpenRowsetor obtain the DBSCHEMA_TABLE_TYPE_COLUMNS rowset by specifying the table-valued parameter type name as the table name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f95b5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f95b5-114">See Also</span></span>  
 <span data-ttu-id="f95b5-115">[Parametri con valori di tabella &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="f95b5-115">[Table-Valued Parameters &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="f95b5-116">Usare parametri con valori di tabella &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f95b5-116">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
