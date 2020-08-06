---
title: Pubblicare l'esecuzione di una stored procedure in una pubblicazione transazionale (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- publishing [SQL Server replication], stored procedure execution
- stored procedures [SQL Server replication], publishing
ms.assetid: 1d3a3525-0bc5-466f-b097-5359dc74432d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44310d45a7049701a6aecfa73301b15b0021ac6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625307"
---
# <a name="publish-the-execution-of-a-stored-procedure-in-a-transactional-publication-sql-server-management-studio"></a><span data-ttu-id="4ec56-102">Pubblicazione dell'esecuzione di una stored procedure in una pubblicazione transazionale (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="4ec56-102">Publish the Execution of a Stored Procedure in a Transactional Publication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="4ec56-103">Specificare che nella finestra di dialogo **Proprietà articolo - \<Article>** deve essere pubblicata l'esecuzione di una stored procedure, anziché la sola definizione.</span><span class="sxs-lookup"><span data-stu-id="4ec56-103">Specify that the execution of a stored procedure (rather than just its definition) should be published in the **Article Properties - \<Article>** dialog box.</span></span> <span data-ttu-id="4ec56-104">Questa finestra di dialogo è disponibile nella Creazione guidata nuova pubblicazione e nella finestra di dialogo **Proprietà pubblicazione - \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="4ec56-104">This dialog box is available in the New Publication Wizard and the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="4ec56-105">Per altre informazioni sull'uso della creazione guidata e l'accesso alla finestra di dialogo, vedere [Creare una pubblicazione](create-a-publication.md) e [Visualizzare e modificare le proprietà della pubblicazione](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4ec56-105">For more information about using the wizard and accessing the dialog box, see [Create a Publication](create-a-publication.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
 <span data-ttu-id="4ec56-106">La definizione della procedura, ovvero l'istruzione CREATE PROCEDURE, viene replicata nel Sottoscrittore durante l'inizializzazione della sottoscrizione. Quando la procedura viene eseguita nel server di pubblicazione, la replica esegue la procedura corrispondente nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="4ec56-106">The definition of the procedure (the CREATE PROCEDURE statement) is replicated to the Subscriber when the subscription is initialized; when the procedure is executed at the Publisher, replication executes the corresponding procedure at the Subscriber.</span></span>  
  
### <a name="to-publish-the-execution-of-a-stored-procedure"></a><span data-ttu-id="4ec56-107">Per pubblicare l'esecuzione di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="4ec56-107">To publish the execution of a stored procedure</span></span>  
  
1.  <span data-ttu-id="4ec56-108">Nella pagina **Articoli** della Creazione guidata nuova pubblicazione o nella finestra di dialogo **Proprietà pubblicazione - \<Publication>** selezionare una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="4ec56-108">On the **Articles** page of the New Publication Wizard or the **Publication Properties - \<Publication>** dialog box, select a stored procedure.</span></span>  
  
2.  <span data-ttu-id="4ec56-109">Fare clic su **Proprietà articolo**e quindi su **Imposta proprietà dell'articolo di stored procedure evidenziato**.</span><span class="sxs-lookup"><span data-stu-id="4ec56-109">Click **Article Properties**, and then click **Set Properties of Highlighted Stored Procedure**.</span></span>  
  
3.  <span data-ttu-id="4ec56-110">Nella finestra di dialogo **Proprietà articolo - \<Article>** specificare uno dei valori seguenti per l'opzione **Replica**:</span><span class="sxs-lookup"><span data-stu-id="4ec56-110">In the **Article Properties - \<Article>** dialog box, specify one of the following values for the **Replicate** option:</span></span>  
  
    -   <span data-ttu-id="4ec56-111">**Esecuzione della stored procedure**</span><span class="sxs-lookup"><span data-stu-id="4ec56-111">**Execution of the stored procedure**</span></span>  
  
    -   <span data-ttu-id="4ec56-112">**Esecuzione in una transazione serializzata della stored procedure**</span><span class="sxs-lookup"><span data-stu-id="4ec56-112">**Execution in a serialized transaction of the SP**</span></span>  
  
         <span data-ttu-id="4ec56-113">Questa è l'opzione consigliata in quanto replica l'esecuzione della procedura solo se essa viene eseguita all'interno del contesto di una transazione serializzabile.</span><span class="sxs-lookup"><span data-stu-id="4ec56-113">This is the recommended option, because it replicates the procedure execution only if the procedure is executed within the context of a serializable transaction.</span></span> <span data-ttu-id="4ec56-114">Se viene eseguita in un contesto diverso, le modifiche ai dati delle tabelle pubblicate vengono replicate come una serie di istruzioni DML (Data Manipulation Language).</span><span class="sxs-lookup"><span data-stu-id="4ec56-114">If the stored procedure is executed outside of a serializable transaction, changes to data in published tables are replicated as a series of data manipulation language (DML) statements.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="4ec56-115">Se è visualizzata la finestra di dialogo **Proprietà pubblicazione - \<Publication>** fare clic su **OK** per salvare e chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="4ec56-115">If you are in the **Publication Properties - \<Publication>** dialog box, click **OK** to save and close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ec56-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ec56-116">See Also</span></span>  
 [<span data-ttu-id="4ec56-117">Pubblicazione dell'esecuzione delle stored procedure nella replica transazionale</span><span class="sxs-lookup"><span data-stu-id="4ec56-117">Publishing Stored Procedure Execution in Transactional Replication</span></span>](../transactional/publishing-stored-procedure-execution-in-transactional-replication.md)  
  
  
