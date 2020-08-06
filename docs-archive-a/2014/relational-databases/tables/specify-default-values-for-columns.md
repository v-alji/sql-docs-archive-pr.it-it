---
title: Specificare valori predefiniti per le colonne | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], defaults
- default values
ms.assetid: 64514aed-b846-407b-992e-cf813f9a1a91
author: stevestein
ms.author: sstein
ms.openlocfilehash: 650347c29e1175c5a1fe646fc079478520dc8c6d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635967"
---
# <a name="specify-default-values-for-columns"></a><span data-ttu-id="ae4bf-102">Specificare valori predefiniti per le colonne</span><span class="sxs-lookup"><span data-stu-id="ae4bf-102">Specify Default Values for Columns</span></span>
  <span data-ttu-id="ae4bf-103">È possibile specificare un valore predefinito che sarà immesso nella colonna in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae4bf-103">You can specify a default value that will be entered in the column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ae4bf-104">Se non si assegna un valore predefinito e l'utente lascia la colonna vuota, si verificherà quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ae4bf-104">If you do not assign a default value and the user leaves the column blank, then:</span></span>  
  
-   <span data-ttu-id="ae4bf-105">Se è stata impostata l'opzione che consente l'immissione di valori Null, nella colonna verrà inserito il valore NULL.</span><span class="sxs-lookup"><span data-stu-id="ae4bf-105">If you set the option to allow null values, NULL will be inserted into the column.</span></span>  
  
-   <span data-ttu-id="ae4bf-106">Se non è stata impostata l'opzione che consente l'immissione di valori Null, la colonna resterà vuota, ma non sarà possibile salvare la riga senza avere fornito un valore per la colonna.</span><span class="sxs-lookup"><span data-stu-id="ae4bf-106">If you do not set the option to allow null values, the column will remain blank, but the user will not be able to save the row until they supply a value for the column.</span></span>  
  
 <span data-ttu-id="ae4bf-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="ae4bf-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ae4bf-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="ae4bf-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ae4bf-109">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="ae4bf-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ae4bf-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ae4bf-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ae4bf-111">**Per specificare un valore predefinito personalizzato:**</span><span class="sxs-lookup"><span data-stu-id="ae4bf-111">**To specify a default value, using:**</span></span>  
  
     [<span data-ttu-id="ae4bf-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ae4bf-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ae4bf-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ae4bf-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ae4bf-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ae4bf-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ae4bf-115">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="ae4bf-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ae4bf-116">Se la voce nel campo **Valore predefinito** sostituisce un valore predefinito associato (visualizzato senza parentesi), verrà chiesto se separare il valore predefinito e sostituirlo con il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="ae4bf-116">If your entry in the **Default Value** field replaces a bound default (which is shown without parentheses), you will be prompted to unbind the default and replace it with your new default.</span></span>  
  
-   <span data-ttu-id="ae4bf-117">Per immettere una stringa di testo, è necessario racchiudere il valore tra virgolette singole ('). Non è consentito l'utilizzo delle virgolette doppie (") poiché sono riservate per gli identificatori delimitati.</span><span class="sxs-lookup"><span data-stu-id="ae4bf-117">To enter a text string, enclose the value in single quotation marks ('); do not use double quotation marks (") because they are reserved for quoted identifiers.</span></span>  
  
-   <span data-ttu-id="ae4bf-118">Per immettere un valore predefinito numerico immettere il numero senza virgolette.</span><span class="sxs-lookup"><span data-stu-id="ae4bf-118">To enter a numeric default, enter the number without quotation marks around it.</span></span>  
  
-   <span data-ttu-id="ae4bf-119">Per specificare un oggetto o una funzione, immetterne il nome senza racchiuderlo tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="ae4bf-119">To enter an object/function, enter the name of the object/function without quotation marks around it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ae4bf-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ae4bf-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ae4bf-121">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ae4bf-121">Permissions</span></span>  
 <span data-ttu-id="ae4bf-122">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="ae4bf-122">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ae4bf-123">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ae4bf-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-default-value-for-a-column"></a><span data-ttu-id="ae4bf-124">Per specificare un valore predefinito per una colonna</span><span class="sxs-lookup"><span data-stu-id="ae4bf-124">To specify a default value for a column</span></span>  
  
1.  <span data-ttu-id="ae4bf-125">In **Esplora oggetti**fare clic con il pulsante destro del mouse sulle colonne della tabella di cui modificare la scala e scegliere **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="ae4bf-125">In **Object Explorer**, right-click the table with columns for which you want to change the scale and click **Design**.</span></span>  
  
2.  <span data-ttu-id="ae4bf-126">Selezionare la colonna per la quale si desidera specificare un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="ae4bf-126">Select the column for which you want to specify a default value.</span></span>  
  
3.  <span data-ttu-id="ae4bf-127">Nella scheda **Proprietà colonne** , immettere il nuovo valore predefinito nella proprietà **Valore predefinito dell'associazione** .</span><span class="sxs-lookup"><span data-stu-id="ae4bf-127">In the **Column Properties** tab, enter the new default value in the **Default Value or Binding** property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ae4bf-128">Per specificare un valore predefinito numerico, immettere il numero desiderato.</span><span class="sxs-lookup"><span data-stu-id="ae4bf-128">To enter a numeric default value, enter the number.</span></span> <span data-ttu-id="ae4bf-129">Per specificare un oggetto o una funzione, immetterne il nome.</span><span class="sxs-lookup"><span data-stu-id="ae4bf-129">For an object or function enter its name.</span></span> <span data-ttu-id="ae4bf-130">Per specificare un valore predefinito alfanumerico, immettere il valore racchiudendolo tra virgolette singole.</span><span class="sxs-lookup"><span data-stu-id="ae4bf-130">For an alphanumeric default enter the value inside single quotes.</span></span>  
  
4.  <span data-ttu-id="ae4bf-131">Nel menu **File** fare clic su **Salva**_nome tabella_.</span><span class="sxs-lookup"><span data-stu-id="ae4bf-131">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ae4bf-132">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ae4bf-132">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-default-value-for-a-column"></a><span data-ttu-id="ae4bf-133">Per specificare un valore predefinito per una colonna</span><span class="sxs-lookup"><span data-stu-id="ae4bf-133">To specify a default value for a column</span></span>  
  
1.  <span data-ttu-id="ae4bf-134">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae4bf-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ae4bf-135">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="ae4bf-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ae4bf-136">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="ae4bf-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    CREATE TABLE dbo.doc_exz ( column_a INT, column_b INT) ;  
    GO  
    INSERT INTO dbo.doc_exz (column_a)VALUES ( 7 ) ;  
    GO  
    ALTER TABLE dbo.doc_exz  
    ADD CONSTRAINT col_b_def  
    DEFAULT 50 FOR column_b ;  
    GO  
  
    ```  
  
 <span data-ttu-id="ae4bf-137">Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ae4bf-137">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
