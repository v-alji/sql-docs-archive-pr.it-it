---
title: Selezione tabella dimensione e chiavi (Configurazione guidata dimensioni a modifica lenta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.selecttableandkeys.f1
ms.assetid: 01e0495f-de35-4607-ba19-0539e801e8fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 671c66a8a5d5f1f4f5201fd8c9ecc144540d8b68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727080"
---
# <a name="select-a-dimension-table-and-keys-slowly-changing-dimension-wizard"></a><span data-ttu-id="16f05-102">Selezione tabella dimensione e chiavi (Configurazione guidata dimensioni a modifica lenta)</span><span class="sxs-lookup"><span data-stu-id="16f05-102">Select a Dimension Table and Keys (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="16f05-103">Utilizzare la pagina **Selezione tabella dimensione e chiavi** per selezionare una tabella della dimensione da caricare</span><span class="sxs-lookup"><span data-stu-id="16f05-103">Use the **Select a Dimension Table and Keys** page to select a dimension table to load.</span></span> <span data-ttu-id="16f05-104">ed eseguire il mapping tra le colonne del flusso di dati e le colonne che verranno caricate.</span><span class="sxs-lookup"><span data-stu-id="16f05-104">Map columns from the data flow to the columns that will be loaded.</span></span>  
  
 <span data-ttu-id="16f05-105">Per ulteriori informazioni su questa procedura guidata, vedere [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="16f05-105">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="16f05-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="16f05-106">Options</span></span>  
 <span data-ttu-id="16f05-107">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="16f05-107">**Connection manager**</span></span>  
 <span data-ttu-id="16f05-108">Selezionare una gestione connessione OLE DB esistente nell'elenco oppure fare clic su **Nuova** per creare una nuova gestione connessione OLE DB.</span><span class="sxs-lookup"><span data-stu-id="16f05-108">Select an existing OLE DB connection manager from the list, or click **New** to create an OLE DB connection manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16f05-109">La Configurazione guidata dimensioni a modifica lenta supporta solo le gestioni connessioni OLE DB e le connessioni a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16f05-109">The Slowly Changing Dimension Wizard only supports OLE DB connection managers, and only supports connections to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="16f05-110">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="16f05-110">**New**</span></span>  
 <span data-ttu-id="16f05-111">Nella finestra di dialogo **Configura gestione connessione OLE DB** selezionare una gestione connessione esistente oppure scegliere **Nuova** per creare una nuova connessione OLE DB.</span><span class="sxs-lookup"><span data-stu-id="16f05-111">Use the **Configure OLE DB Connection Manager** dialog box to select an existing connection manager, or click **New** to create a new OLE DB connection.</span></span>  
  
 <span data-ttu-id="16f05-112">**Tabella o vista**</span><span class="sxs-lookup"><span data-stu-id="16f05-112">**Table or View**</span></span>  
 <span data-ttu-id="16f05-113">Consente di selezionare una tabella o una vista dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="16f05-113">Select a table or view from the list.</span></span>  
  
 <span data-ttu-id="16f05-114">**Colonne di input**</span><span class="sxs-lookup"><span data-stu-id="16f05-114">**Input Columns**</span></span>  
 <span data-ttu-id="16f05-115">Consente di seleziona dall'apposito elenco le colonne di input per le quali è possibile definire il mapping.</span><span class="sxs-lookup"><span data-stu-id="16f05-115">Select from the list of input columns for which you may specify mapping.</span></span>  
  
 <span data-ttu-id="16f05-116">**Colonne dimensione**</span><span class="sxs-lookup"><span data-stu-id="16f05-116">**Dimension Columns**</span></span>  
 <span data-ttu-id="16f05-117">Consente di visualizzare tutte le colonne della dimensione disponibili.</span><span class="sxs-lookup"><span data-stu-id="16f05-117">View all available dimension columns.</span></span>  
  
 <span data-ttu-id="16f05-118">**Tipo chiave**</span><span class="sxs-lookup"><span data-stu-id="16f05-118">**Key Type**</span></span>  
 <span data-ttu-id="16f05-119">Consente di selezionare una delle colonne della dimensione da utilizzare come chiave business.</span><span class="sxs-lookup"><span data-stu-id="16f05-119">Select one of the dimension columns to be the business key.</span></span> <span data-ttu-id="16f05-120">È necessario disporre di una chiave business.</span><span class="sxs-lookup"><span data-stu-id="16f05-120">You must have one business key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16f05-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16f05-121">See Also</span></span>  
 [<span data-ttu-id="16f05-122">Configurare gli output tramite Configurazione guidata dimensioni a modifica lenta</span><span class="sxs-lookup"><span data-stu-id="16f05-122">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
