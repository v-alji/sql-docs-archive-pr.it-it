---
title: Mapping dei parametri di query a variabili in un componente del flusso di dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- queries [Integration Services], parameter mapping
- parameters [Integration Services]
- mapping query parameters to variables [Integration Services]
- variables [Integration Services], mapping parameters to
ms.assetid: 5e26977c-758c-46d6-acf1-4fd9238f0950
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b38940313397c7be7a8bcdbd2bf7f5233583096e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724828"
---
# <a name="map-query-parameters-to-variables-in-a-data-flow-component"></a><span data-ttu-id="acd40-102">Mapping dei parametri di query a variabili in un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="acd40-102">Map Query Parameters to Variables in a Data Flow Component</span></span>
  <span data-ttu-id="acd40-103">Quando viene configurata l'origine OLE DB per utilizzare query con parametri, è possibile eseguire il mapping dei parametri alle variabili.</span><span class="sxs-lookup"><span data-stu-id="acd40-103">When you configure the OLE DB source to use parameterized queries, you can map the parameters to variables.</span></span>  
  
 <span data-ttu-id="acd40-104">L'origine OLE DB utilizza query con parametri per filtrare i dati quando l'origine si collega a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="acd40-104">The OLE DB source uses parameterized queries to filter data when the source connects to a data source.</span></span>  
  
### <a name="to-map-a-query-parameter-to-a-variable"></a><span data-ttu-id="acd40-105">Per eseguire il mapping di un parametro di query a una variabile</span><span class="sxs-lookup"><span data-stu-id="acd40-105">To map a query parameter to a variable</span></span>  
  
1.  <span data-ttu-id="acd40-106">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="acd40-106">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="acd40-107">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="acd40-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="acd40-108">Fare clic sulla scheda **Flusso di dati** e quindi dalla **Casella degli strumenti**trascinare l'origine OLE DB sull'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="acd40-108">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB source to the design surface.</span></span>  
  
4.  <span data-ttu-id="acd40-109">Fare clic con il pulsante destro del mouse sull'origine OLE DB e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="acd40-109">Right-click the OLE DB source, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="acd40-110">In **Editor origine OLE DB**, selezionare la gestione connessione OLE DB da usare per la connessione all'origine dei dati oppure fare clic su **Nuova** per creare una nuova gestione connessione OLE DB.</span><span class="sxs-lookup"><span data-stu-id="acd40-110">In the **OLE DB Source Editor**, select an OLE DB connection manager to use to connect to the data source, or click **New** to create a new OLE DB connection manager.</span></span>  
  
6.  <span data-ttu-id="acd40-111">Selezionare l'opzione **Comando SQL** per la modalità di accesso ai dati e quindi immettere una query con parametri nella casella **Testo comando SQL** .</span><span class="sxs-lookup"><span data-stu-id="acd40-111">Select the **SQL command** option for data access mode, and then type a parameterized query in the **SQL command text** pane.</span></span>  
  
7.  <span data-ttu-id="acd40-112">Fare clic su **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="acd40-112">Click **Parameters**.</span></span>  
  
8.  <span data-ttu-id="acd40-113">Nella finestra di dialogo **Imposta parametri query** eseguire il mapping di ogni parametro nell'elenco **Parametri** a una variabile nell'elenco **Variabili** oppure fare clic su **\<New variable>** per creare una nuova variabile.</span><span class="sxs-lookup"><span data-stu-id="acd40-113">In the **Set Query Parameters** dialog box, map each parameter in the **Parameters** list to a variable in the **Variables** list, or create a new variable by clicking **\<New variable>**.</span></span> <span data-ttu-id="acd40-114">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="acd40-114">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="acd40-115">Sono disponibili per il mapping solo le variabili di sistema e le variabili definite dall'utente nell'ambito del pacchetto, di un contenitore padre quale Ciclo Foreach o dell'attività Flusso di dati che contiene il componente del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="acd40-115">Only system variables and user-defined variables that are in the scope of the package, a parent container such as a Foreach Loop, or the Data Flow task that contains the data flow component are available for mapping.</span></span> <span data-ttu-id="acd40-116">La variabile deve avere un tipo di dati compatibile con la colonna nella clausola WHERE a cui è assegnato il parametro.</span><span class="sxs-lookup"><span data-stu-id="acd40-116">The variable must have a data type that is compatible with the column in the WHERE clause to which the parameter is assigned.</span></span>  
  
9. <span data-ttu-id="acd40-117">Facendo clic su **Anteprima** è possibile visualizzare fino a 200 righe di dati restituiti dalla query.</span><span class="sxs-lookup"><span data-stu-id="acd40-117">You can click **Preview** to view up to 200 rows of the data that the query returns.</span></span>  
  
10. <span data-ttu-id="acd40-118">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="acd40-118">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acd40-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acd40-119">See Also</span></span>  
 <span data-ttu-id="acd40-120">[Origine OLE DB](ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="acd40-120">[OLE DB Source](ole-db-source.md) </span></span>  
 [<span data-ttu-id="acd40-121">Trasformazione Ricerca</span><span class="sxs-lookup"><span data-stu-id="acd40-121">Lookup Transformation</span></span>](transformations/lookup-transformation.md)  
  
  
