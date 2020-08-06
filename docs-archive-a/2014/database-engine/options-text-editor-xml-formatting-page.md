---
title: Opzioni (editor di testo-XML-pagina formattazione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 97373178-d288-4127-af37-d9f5fe1b8607
author: rothja
ms.author: jroth
ms.openlocfilehash: dce36142fe9974c0167fca700c509642e05d89b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716580"
---
# <a name="options-text-editor---xml---formatting-page"></a><span data-ttu-id="1bd9b-102">Opzioni (Editor di testo - XML - pagina Formattazione)</span><span class="sxs-lookup"><span data-stu-id="1bd9b-102">Options (Text Editor - XML - Formatting Page)</span></span>

<span data-ttu-id="1bd9b-103">Questa finestra di dialogo consente di specificare le impostazioni di formattazione per l'editor XML.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-103">This dialog box allows you to specify the formatting settings for the XML Editor.</span></span> <span data-ttu-id="1bd9b-104">È possibile accedere alla finestra di dialogo **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-104">You can access the **Options** dialog box from the **Tools** menu.</span></span>  
  
> [!NOTE]  
> <span data-ttu-id="1bd9b-105">Queste impostazioni sono disponibili quando si selezionano la cartella **Editor di testo**, la cartella **XML** e quindi l'opzione **Formattazione** nella finestra di dialogo **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-105">These settings are available when you select the **Text Editor** folder, the **XML** folder, and then the **Formatting** option from the **Options** dialog box.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="1bd9b-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="1bd9b-106">Attributes</span></span>  
 <span data-ttu-id="1bd9b-107">**Mantieni la formattazione manuale degli attributi**</span><span class="sxs-lookup"><span data-stu-id="1bd9b-107">**Preserve manual attribute formatting**</span></span>  
 <span data-ttu-id="1bd9b-108">Consente di non riformattare gli attributi.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-108">Do not reformat attributes.</span></span> <span data-ttu-id="1bd9b-109">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-109">This is the default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1bd9b-110">Se gli attributi sono disposti su più righe, a ogni riga di attributi verrà applicato un rientro corrispondente al rientro dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-110">If the attributes are on multiple lines, the editor indents each line of attributes to match the indentation of the parent element.</span></span>  
  
 <span data-ttu-id="1bd9b-111">**Allinea ogni attributo su una riga separata**</span><span class="sxs-lookup"><span data-stu-id="1bd9b-111">**Align attributes each on a separate line**</span></span>  
 <span data-ttu-id="1bd9b-112">Il secondo attributo e i successivi vengono allineati verticalmente in modo da corrispondere al rientro del primo attributo.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-112">Align the second and subsequent attributes vertically to match the indentation of the first attribute.</span></span> <span data-ttu-id="1bd9b-113">Il testo XML seguente rappresenta un esempio del modo in cui gli attributi vengono allineati.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-113">The following XML text is an example of how the attributes would be aligned.</span></span>  
  
```  
<item id = "123-A"  
      name = "hammer"  
      price = "9.95"  
</item>  
```  
  
## <a name="auto-reformat"></a><span data-ttu-id="1bd9b-114">Riformatta automaticamente</span><span class="sxs-lookup"><span data-stu-id="1bd9b-114">Auto Reformat</span></span>  
 <span data-ttu-id="1bd9b-115">**Quando si incolla dagli Appunti**</span><span class="sxs-lookup"><span data-stu-id="1bd9b-115">**On paste from clipboard.**</span></span>  
 <span data-ttu-id="1bd9b-116">Consente di riformattare il testo XML incollato dagli Appunti.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-116">Reformat XML text pasted from the clipboard.</span></span>  
  
 <span data-ttu-id="1bd9b-117">**Al completamento del tag di fine**</span><span class="sxs-lookup"><span data-stu-id="1bd9b-117">**On completion of end tag**</span></span>  
 <span data-ttu-id="1bd9b-118">Consente di riformattare l'elemento al completamento del tag di fine.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-118">Reformat the element when the end tag is completed.</span></span>  
  
## <a name="mixed-content"></a><span data-ttu-id="1bd9b-119">Contenuto misto</span><span class="sxs-lookup"><span data-stu-id="1bd9b-119">Mixed Content</span></span>  
 <span data-ttu-id="1bd9b-120">**Formatta contenuto misto per impostazione predefinita**</span><span class="sxs-lookup"><span data-stu-id="1bd9b-120">**Format mixed content by default.**</span></span>  
 <span data-ttu-id="1bd9b-121">Viene riformattato il contenuto misto, tranne quando il contenuto si trova in un ambito `xml:space="preserve"`.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-121">Attempt to reformat mixed content, except when the content is found in an `xml:space="preserve"` scope.</span></span> <span data-ttu-id="1bd9b-122">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-122">This is the default.</span></span>  
  
 <span data-ttu-id="1bd9b-123">Se un elemento contiene testo e markup, il contenuto viene considerato misto.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-123">If an element contains a mix of text and markup, the contents are considered to be mixed content.</span></span> <span data-ttu-id="1bd9b-124">Di seguito viene riportato un esempio di elemento con contenuto misto.</span><span class="sxs-lookup"><span data-stu-id="1bd9b-124">Following is an example of an element with mixed content.</span></span>  
  
```  
<dir>c:\data\AlphaProject\  
  <file readOnly="false">test1.txt</file>  
  <file readOnly="false">test2.txt</file>  
```  
  
 \</dir>  
  
## <a name="see-also"></a><span data-ttu-id="1bd9b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bd9b-125">See Also</span></span>  
 [<span data-ttu-id="1bd9b-126">Editor XML &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1bd9b-126">XML Editor &#40;SQL Server Management Studio&#41;</span></span>](../ssms/sql-server-management-studio-ssms.md)  
