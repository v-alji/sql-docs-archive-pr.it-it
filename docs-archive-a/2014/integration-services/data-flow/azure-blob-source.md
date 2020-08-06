---
title: Origine BLOB di Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobsrc.f1
- sql11.dts.designer.afpblobsrc.f1
ms.assetid: 80645c5c-88c8-4fb0-8607-de1bb7bffcbb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a14c7022437c8a23f898a0f29c211bd9ae82aa0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636836"
---
# <a name="azure-blob-source"></a><span data-ttu-id="2d0a5-102">Origine BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="2d0a5-102">Azure Blob Source</span></span>
 <span data-ttu-id="2d0a5-103">Il componente **Origine Blob di Azure** consente a un pacchetto SSIS di leggere dati da un BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="2d0a5-103">The **Azure Blob Source** component enables an SSIS package to read data from an Azure blob.</span></span> <span data-ttu-id="2d0a5-104">I formati di file supportati sono CSV e AVRO.</span><span class="sxs-lookup"><span data-stu-id="2d0a5-104">The supported file formats are: CSV and AVRO.</span></span> <span data-ttu-id="2d0a5-105">Per visualizzare l'editor per l'origine BLOB di Azure, trascinare la selezione **Origine BLOB di Azure** nell'area di progettazione del flusso di dati e fare doppio clic per aprire l'editor.</span><span class="sxs-lookup"><span data-stu-id="2d0a5-105">To see the editor for the Azure Blob Source, drag and drop **Azure Blob Source** on the data flow designer and double-click it to open the editor).</span></span>  
  
1.  <span data-ttu-id="2d0a5-106">Nel campo **Gestione connessione di archiviazione di Azure** specificare un'istanza esistente di Gestione connessioni dell'archiviazione di Azure o creare una nuova istanza che fa riferimento a un account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="2d0a5-106">For the **Azure storage connection manager** field, specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account.</span></span>  
  
2.  <span data-ttu-id="2d0a5-107">Nel campo **Nome contenitore BLOB** specificare il nome del contenitore BLOB che contiene i file di origine.</span><span class="sxs-lookup"><span data-stu-id="2d0a5-107">For the **Blob container name** field, specify the name of the blob container that contains source files.</span></span>  
  
3.  <span data-ttu-id="2d0a5-108">Nel campo **Nome BLOB** specificare il percorso per il BLOB.</span><span class="sxs-lookup"><span data-stu-id="2d0a5-108">For the **Blob name** field, specify the path for the blob.</span></span>  
  
4.  <span data-ttu-id="2d0a5-109">Nel campo **Formato del file BLOB** specificare il formato BLOB che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="2d0a5-109">For the **Blob file format** field, specify the blob format you want to use.</span></span>  
  
5.  <span data-ttu-id="2d0a5-110">Se il formato del file è CSV, è necessario impostare il valore **Carattere delimitatore di colonna** .</span><span class="sxs-lookup"><span data-stu-id="2d0a5-110">If the file format is CSV, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="2d0a5-111">Selezionare anche **Nomi di colonne nella prima riga di dati** se la prima riga nel file contiene i nomi di colonna.</span><span class="sxs-lookup"><span data-stu-id="2d0a5-111">Also select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
6.  <span data-ttu-id="2d0a5-112">Dopo aver specificato le informazioni di connessione, passare alla pagina **Colonne** per eseguire il mapping delle colonne di origine alle colonne di destinazione per il flusso di dati SSIS.</span><span class="sxs-lookup"><span data-stu-id="2d0a5-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
  
  
