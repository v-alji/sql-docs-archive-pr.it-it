---
title: Connettersi a un file di Microsoft Excel (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connexcelfile.f1
ms.assetid: 126f7d6b-d270-40e7-b23e-8d114f87065b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 79bb3d57470be8acbbb990dde71cf21b62b3cb2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625726"
---
# <a name="connect-to-a-microsoft-excel-file-ssas"></a><span data-ttu-id="a3a72-102">Connessione a un file di Microsoft Excel (SSAS)</span><span class="sxs-lookup"><span data-stu-id="a3a72-102">Connect to a Microsoft Excel File (SSAS)</span></span>
  <span data-ttu-id="a3a72-103">Questa pagina dell' **Importazione guidata tabella** consente di connettersi a un file di Microsoft Excel archiviato nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="a3a72-103">This page of the **Table Import Wizard** enables you to connect to a Microsoft Excel file stored on the local machine.</span></span> <span data-ttu-id="a3a72-104">Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="a3a72-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="a3a72-105">Per connettersi a un file di Microsoft Excel, è necessario che nel computer sia installato il provider ACE appropriato.</span><span class="sxs-lookup"><span data-stu-id="a3a72-105">To connect to a Microsoft Excel file, you must have the appropriate ACE provider installed on your computer.</span></span> <span data-ttu-id="a3a72-106">Per altre informazioni, vedere [Origini dati supportate &#40;SSAS tabulare&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="a3a72-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3a72-107">Le credenziali dell'utente corrente vengono utilizzate in caso di selezione di un file in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="a3a72-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="a3a72-108">Tuttavia, l'importazione non verrà completata se l'utente specificato nella pagina Impostazioni di rappresentazione non dispone di privilegi sufficienti per leggere dal file selezionato.</span><span class="sxs-lookup"><span data-stu-id="a3a72-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="a3a72-109">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="a3a72-109">UI element list</span></span>  
 <span data-ttu-id="a3a72-110">**Nome descrittivo connessione**</span><span class="sxs-lookup"><span data-stu-id="a3a72-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="a3a72-111">Digitare un nome univoco per questa connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="a3a72-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="a3a72-112">Questo campo è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a3a72-112">This is a required field.</span></span>  
  
 <span data-ttu-id="a3a72-113">**Percorso file di Excel**</span><span class="sxs-lookup"><span data-stu-id="a3a72-113">**Excel File Path**</span></span>  
 <span data-ttu-id="a3a72-114">Specificare il percorso completo del file di Excel.</span><span class="sxs-lookup"><span data-stu-id="a3a72-114">Specify a full path for the Excel file.</span></span>  
  
 <span data-ttu-id="a3a72-115">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="a3a72-115">**Browse**</span></span>  
 <span data-ttu-id="a3a72-116">Passare al percorso in cui è disponibile un file di Excel.</span><span class="sxs-lookup"><span data-stu-id="a3a72-116">Navigate to a location where an Excel file is available.</span></span>  
  
 <span data-ttu-id="a3a72-117">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="a3a72-117">**Advanced**</span></span>  
 <span data-ttu-id="a3a72-118">Impostare altre proprietà relative alla connessione tramite la finestra di dialogo **Impostazione delle proprietà avanzate** .</span><span class="sxs-lookup"><span data-stu-id="a3a72-118">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="a3a72-119">**Utilizza la prima riga per le intestazioni di colonna**</span><span class="sxs-lookup"><span data-stu-id="a3a72-119">**Use first row as column headers**</span></span>  
 <span data-ttu-id="a3a72-120">Specificare se utilizzare la prima riga di dati per le intestazioni di colonna della tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a3a72-120">Specify whether to use the first data row as the column headers of the destination table.</span></span>  
  
 <span data-ttu-id="a3a72-121">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="a3a72-121">**Test Connection**</span></span>  
 <span data-ttu-id="a3a72-122">Provare a stabilire una connessione all'origine dati utilizzando le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="a3a72-122">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="a3a72-123">Viene visualizzato un messaggio che indica se la connessione è stata stabilita.</span><span class="sxs-lookup"><span data-stu-id="a3a72-123">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
