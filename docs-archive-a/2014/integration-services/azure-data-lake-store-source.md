---
title: Origine di Azure Data Lake Store | Microsoft Docs
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSSRC.F1
- SQL11.DTS.DESIGNER.AFPADLSSRC.F1
ms.assetid: 7d9e8457-62aa-4aea-98ee-7d1121dfae4f
author: yualan
ms.author: chugu
ms.openlocfilehash: e5bce25e303b055d734da6a00c73851f4eb0d7ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629998"
---
# <a name="azure-data-lake-store-source"></a><span data-ttu-id="7a163-102">Origine di Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="7a163-102">Azure Data Lake Store Source</span></span>
  <span data-ttu-id="7a163-103">Il componente **Origine di Azure Data Lake Store** consente a un pacchetto SSIS di leggere dati da Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="7a163-103">The **Azure Data Lake Store Source** component enables an SSIS package to read data from an Azure Data Lake Store.</span></span> <span data-ttu-id="7a163-104">I formati di file supportati sono: testo e AVRO.</span><span class="sxs-lookup"><span data-stu-id="7a163-104">The supported file formats are: Text and Avro.</span></span>
  
## <a name="configure-the-azure-data-lake-store-source"></a><span data-ttu-id="7a163-105">Configurare Origine di Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="7a163-105">Configure the Azure Data Lake Store Source</span></span> 
  
1.  <span data-ttu-id="7a163-106">Per visualizzare l'editor per Origine di Azure Data Lake Store, trascinare la selezione **Origine di Azure Data Lake Store** nell'area di progettazione del flusso di dati e fare doppio clic per aprire l'editor.</span><span class="sxs-lookup"><span data-stu-id="7a163-106">To see the editor for the Azure Data Lake Store Source, drag and drop **Azure Data Lake Store Source** on the data flow designer and double-click it to open the editor).</span></span>  
  
2.  <span data-ttu-id="7a163-107">Nel campo **Gestione connessioni di Azure Data Lake Store** specificare un'istanza esistente di Gestione connessioni di Azure Data Lake Store o creare una nuova istanza che faccia riferimento a un servizio di Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="7a163-107">For the **Azure Data Lake Store connection manager** field, specify an existing Azure Data Lake Store Connection Manager or create a new one that refers to an Azure Data Lake Store service.</span></span>  
  
    1.  <span data-ttu-id="7a163-108">Per il campo **Percorso File** , specificare il percorso del file di origine in Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="7a163-108">For the **File Path** field, specify the file path of the source file in Azure Data Lake Store.</span></span>   
  
    2.  <span data-ttu-id="7a163-109">Per il campo **Formato file** specificare il formato file che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="7a163-109">For the **File format** field, specify the file format of the source file.</span></span>  
  
        <span data-ttu-id="7a163-110">Se il formato del file corrisponde a testo, è necessario impostare il valore **Carattere delimitatore di colonna** .</span><span class="sxs-lookup"><span data-stu-id="7a163-110">If the file format is Text, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="7a163-111">Selezionare anche **Nomi di colonne nella prima riga di dati** se la prima riga nel file contiene i nomi di colonna.</span><span class="sxs-lookup"><span data-stu-id="7a163-111">Also select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
3.  <span data-ttu-id="7a163-112">Dopo aver specificato le informazioni di connessione, passare alla pagina **Colonne** per eseguire il mapping delle colonne di origine alle colonne di destinazione per il flusso di dati SSIS.</span><span class="sxs-lookup"><span data-stu-id="7a163-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
