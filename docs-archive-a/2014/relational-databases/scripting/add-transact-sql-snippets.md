---
title: Aggiunta di frammenti Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 901c7995-8eb5-4d12-8bb0-de0a922b48f8
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b5886f8f36ae3753fcb7c89dd3aeff9c69eeba5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627173"
---
# <a name="add-transact-sql-snippets"></a><span data-ttu-id="d2c4d-102">Aggiunta di frammenti Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d2c4d-102">Add Transact-SQL Snippets</span></span>
  <span data-ttu-id="d2c4d-103">È possibile aggiungere frammenti di codice Transact-SQL personalizzati al set di frammenti predefiniti incluso in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2c4d-103">You can add your own Transact-SQL code snippets to the set of pre-defined snippets included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="creating-a-transact-sql-snippet-file"></a><span data-ttu-id="d2c4d-104">Creazione di un file di frammento Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d2c4d-104">Creating a Transact-SQL Snippet File</span></span>  
 <span data-ttu-id="d2c4d-105">La prima parte della creazione di un frammento di codice [!INCLUDE[tsql](../../includes/tsql-md.md)] consiste nel creare un file XML con il testo del frammento di codice.</span><span class="sxs-lookup"><span data-stu-id="d2c4d-105">The first part of creating a [!INCLUDE[tsql](../../includes/tsql-md.md)] code snippet is to create an XML file with the text of your code snippet.</span></span> <span data-ttu-id="d2c4d-106">Il file deve avere un'estensione di file snippet e soddisfare i requisiti dello [schema dei frammenti di codice](https://go.microsoft.com/fwlink/?LinkId=207504).</span><span class="sxs-lookup"><span data-stu-id="d2c4d-106">The file must have a .snippet file extension, and meet the requirements of the [Code Snippets Schema](https://go.microsoft.com/fwlink/?LinkId=207504).</span></span> <span data-ttu-id="d2c4d-107">Impostare la lingua del frammento su SQL.</span><span class="sxs-lookup"><span data-stu-id="d2c4d-107">Set the snippet language to SQL.</span></span>  
  
 <span data-ttu-id="d2c4d-108">È possibile utilizzare i frammenti predefiniti forniti con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] come esempi.</span><span class="sxs-lookup"><span data-stu-id="d2c4d-108">You can use the pre-defined snippets that ship with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as examples.</span></span> <span data-ttu-id="d2c4d-109">Per trovare i frammenti predefiniti, aprire [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], selezionare il menu **Strumenti** e quindi fare clic su **Gestione frammenti di codice**.</span><span class="sxs-lookup"><span data-stu-id="d2c4d-109">To find the pre-defined snippets, open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the **Tools** menu, and click **Code Snippet Manager**.</span></span> <span data-ttu-id="d2c4d-110">Selezionare **SQL** nella casella di riepilogo **Lingua** . Il percorso dei frammenti [!INCLUDE[tsql](../../includes/tsql-md.md)] verrà visualizzato nella casella **Percorso** .</span><span class="sxs-lookup"><span data-stu-id="d2c4d-110">Select **SQL** in the **Language** list box, the path to the [!INCLUDE[tsql](../../includes/tsql-md.md)] snippets is displayed in the **Location** box.</span></span>  
  
## <a name="registering-the-code-snippet"></a><span data-ttu-id="d2c4d-111">Registrazione del frammento di codice</span><span class="sxs-lookup"><span data-stu-id="d2c4d-111">Registering the Code Snippet</span></span>  
 <span data-ttu-id="d2c4d-112">Dopo avere creato il file di frammento, utilizzare Gestione frammenti di codice per registrare il frammento con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2c4d-112">After creating the snippet file, use the Code Snippets Manager to register the snippet with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d2c4d-113">È possibile aggiungere una cartella contenente più frammenti oppure importare singoli frammenti nella cartella **Frammenti di codice** .</span><span class="sxs-lookup"><span data-stu-id="d2c4d-113">You can either add a folder containing multiple snippets, or import individual snippets to the **My Code Snippets** folder.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="d2c4d-114">Procedure</span><span class="sxs-lookup"><span data-stu-id="d2c4d-114">Procedures</span></span>  
  
#### <a name="adding-a-snippet-folder"></a><span data-ttu-id="d2c4d-115">Aggiunta di una cartella per i frammenti</span><span class="sxs-lookup"><span data-stu-id="d2c4d-115">Adding a Snippet Folder</span></span>  
  
1.  <span data-ttu-id="d2c4d-116">Aprire [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2c4d-116">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="d2c4d-117">Scegliere **Gestione frammenti di codice** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="d2c4d-117">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
3.  <span data-ttu-id="d2c4d-118">Fare clic su **Add** .</span><span class="sxs-lookup"><span data-stu-id="d2c4d-118">Click the **Add** button.</span></span>  
  
4.  <span data-ttu-id="d2c4d-119">Passare alla cartella contenente i frammenti di codice e fare clic sul pulsante **Seleziona cartella** .</span><span class="sxs-lookup"><span data-stu-id="d2c4d-119">Navigate to the folder containing your code snippets, and click the **Select Folder** button.</span></span>  
  
#### <a name="importing-a-snippet"></a><span data-ttu-id="d2c4d-120">Importazione di un frammento</span><span class="sxs-lookup"><span data-stu-id="d2c4d-120">Importing a Snippet</span></span>  
  
1.  <span data-ttu-id="d2c4d-121">Aprire [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2c4d-121">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="d2c4d-122">Scegliere **Gestione frammenti di codice** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="d2c4d-122">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
3.  <span data-ttu-id="d2c4d-123">Fare clic sul pulsante **Import** (Importa).</span><span class="sxs-lookup"><span data-stu-id="d2c4d-123">Click the **Import** button.</span></span>  
  
4.  <span data-ttu-id="d2c4d-124">Passare alla cartella contenente il frammento, fare clic sul file con estensione snippet e quindi sul pulsante **Apri** .</span><span class="sxs-lookup"><span data-stu-id="d2c4d-124">Navigate to the folder containing your snippet, click on the .snippet file, and click the **Open** button.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d2c4d-125">Esempi</span><span class="sxs-lookup"><span data-stu-id="d2c4d-125">Examples</span></span>  
 <span data-ttu-id="d2c4d-126">Nell'esempio seguente viene creato un frammento di inclusione `TRY-CATCH` che viene importato in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2c4d-126">The following example creates a `TRY-CATCH` surround-with snippet and imports it to [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="d2c4d-127">Incollare il codice seguente in Blocco note, quindi salvare il file con il nome TryCatch.snippet.</span><span class="sxs-lookup"><span data-stu-id="d2c4d-127">Paste the following code into notepad, then save as a file named TryCatch.snippet.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <CodeSnippets  xmlns="https://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">  
    <_locDefinition xmlns="urn:locstudio">  
        <_locDefault _loc="locNone" />  
        <_locTag _loc="locData">Title</_locTag>  
        <_locTag _loc="locData">Description</_locTag>  
        <_locTag _loc="locData">Author</_locTag>  
        <_locTag _loc="locData">ToolTip</_locTag>  
       <_locTag _loc="locData">Default</_locTag>  
    </_locDefinition>  
    <CodeSnippet Format="1.0.0">  
    <Header>  
    <Title>TryCatch</Title>  
                            <Shortcut></Shortcut>  
    <Description>Example Snippet for Try-Catch.</Description>  
    <Author>SQL Server Books Online Example</Author>  
    <SnippetTypes>  
                                    <SnippetType>SurroundsWith</SnippetType>  
    </SnippetTypes>  
    </Header>  
    <Snippet>  
    <Declarations>  
                                    <Literal>  
                                    <ID>CatchCode</ID>  
                                    <ToolTip>Code to handle the caught error</ToolTip>  
                                    <Default>CatchCode</Default>  
                                    </Literal>  
    </Declarations>  
    <Code Language="SQL"><![CDATA[  
    BEGIN TRY  
  
    $selected$ $end$  
  
    END TRY  
    BEGIN CATCH  
  
    $CatchCode$  
  
    END CATCH;  
    ]]>  
    </Code>  
    </Snippet>  
    </CodeSnippet>  
    </CodeSnippets>  
    ```  
  
2.  <span data-ttu-id="d2c4d-128">Aprire [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2c4d-128">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
3.  <span data-ttu-id="d2c4d-129">Scegliere **Gestione frammenti di codice** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="d2c4d-129">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
4.  <span data-ttu-id="d2c4d-130">Fare clic sul pulsante **Import** (Importa).</span><span class="sxs-lookup"><span data-stu-id="d2c4d-130">Click the **Import** button.</span></span>  
  
5.  <span data-ttu-id="d2c4d-131">Passare alla cartella contenente il file TryCatch.snippet, fare clic su tale file e quindi sul pulsante **Apri** .</span><span class="sxs-lookup"><span data-stu-id="d2c4d-131">Navigate to the folder containing TryCatch.snippet, click on the TryCatch.snippet file, and click the **Open** button.</span></span> <span data-ttu-id="d2c4d-132">Nella cartella **Frammenti di codice** non dovrebbe essere presente un frammento TryCatch.</span><span class="sxs-lookup"><span data-stu-id="d2c4d-132">You should not have a TryCatch snippet in your **My Code Snippets** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2c4d-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2c4d-133">See Also</span></span>  
 [<span data-ttu-id="d2c4d-134">Inserire frammenti Transact-SQL racchiusi</span><span class="sxs-lookup"><span data-stu-id="d2c4d-134">Insert Surround-with Transact-SQL snippets</span></span>](insert-surround-with-transact-sql-snippets.md)  
  
  
