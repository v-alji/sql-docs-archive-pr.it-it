---
title: Query FOR XML e query FOR XML annidate a confronto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML query
- queries [XML in SQL Server], comparing query types
ms.assetid: 19225b4a-ee3f-47cf-8bcc-52699eeda32c
author: rothja
ms.author: jroth
ms.openlocfilehash: ca10060702d0c7e50f2be79310c55e177dca358d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726780"
---
# <a name="for-xml-query-compared-to-nested-for-xml-query"></a><span data-ttu-id="0b964-102">Query FOR XML e query nidificata FOR XML a confronto</span><span class="sxs-lookup"><span data-stu-id="0b964-102">FOR XML Query Compared to Nested FOR XML Query</span></span>
  <span data-ttu-id="0b964-103">In questo argomento viene messa a confronto una query FOR XML con un solo livello con una query FOR XML nidificata.</span><span class="sxs-lookup"><span data-stu-id="0b964-103">This topic compares a single-level FOR XML query to a nested FOR XML query.</span></span> <span data-ttu-id="0b964-104">Uno dei vantaggi dell'utilizzo di query FOR XML consiste nella possibilità di specificare una combinazione di XML incentrati sia sugli attributi che sugli elementi per i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="0b964-104">One of the benefits of using nested FOR XML queries is that you can specify a combination of attribute-centric and element-centric XML for query results.</span></span> <span data-ttu-id="0b964-105">Tutto ciò è dimostrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0b964-105">The example demonstrates this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b964-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b964-106">Example</span></span>  
 <span data-ttu-id="0b964-107">La query seguente `SELECT` recupera informazioni sulla categoria e sulla sottocategoria di un prodotto dal database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0b964-107">The following `SELECT` query retrieves product category and subcategory information in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="0b964-108">La query non include istruzioni FOR XML nidificate.</span><span class="sxs-lookup"><span data-stu-id="0b964-108">There is no nested FOR XML in the query.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT   ProductCategory.ProductCategoryID,   
         ProductCategory.Name as CategoryName,  
         ProductSubCategory.ProductSubCategoryID,   
         ProductSubCategory.Name  
FROM     Production.ProductCategory, Production.ProductSubCategory  
WHERE    ProductCategory.ProductCategoryID = ProductSubCategory.ProductCategoryID  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
GO  
```  
  
 <span data-ttu-id="0b964-109">Risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="0b964-109">This is the partial result:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory ProductSubCategoryID="1" Name="Mountain Bike"/>  
  <ProductSubCategory ProductSubCategoryID="2" Name="Road Bike"/>  
  <ProductSubCategory ProductSubCategoryID="3" Name="Touring Bike"/>  
</ProductCategory>  
...  
```  
  
 <span data-ttu-id="0b964-110">Se nella query si specifica la direttiva `ELEMENTS` , verrà restituito un risultato incentrato sugli elementi, come illustrato nel frammento di risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="0b964-110">If you specify the `ELEMENTS` directive in the query, you receive an element-centric result, as shown in the following result fragment:</span></span>  
  
```  
<ProductCategory>  
  <ProductCategoryID>1</ProductCategoryID>  
  <CategoryName>Bike</CategoryName>  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <Name>Mountain Bike</Name>  
  </ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  </ProductSubCategory>  
</ProductCategory>  
```  
  
 <span data-ttu-id="0b964-111">Si supponga quindi di voler generare una gerarchia XML costituita da una combinazione di valori XML incentrati sugli elementi e incentrati sugli attributi, come illustrato nel frammento seguente:</span><span class="sxs-lookup"><span data-stu-id="0b964-111">Next, assume that you want to generate an XML hierarchy that is a combination of attribute-centric and element-centric XML, as shown in the following fragment:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bike</SubCategoryName></ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  <ProductSubCategory>  
     ...  
</ProductCategory>  
```  
  
 <span data-ttu-id="0b964-112">Nel frammento precedente le informazioni sulla categoria del prodotto, ad esempio il nome e l'ID della categoria, sono attributi.</span><span class="sxs-lookup"><span data-stu-id="0b964-112">In the previous fragment, product category information such as category ID and category name are attributes.</span></span> <span data-ttu-id="0b964-113">Tuttavia, le informazioni sulla sottocategoria sono incentrate sugli elementi.</span><span class="sxs-lookup"><span data-stu-id="0b964-113">However, the subcategory information is element-centric.</span></span> <span data-ttu-id="0b964-114">Per costruire l'elemento <`ProductCategory`> è possibile creare una query `FOR XML`, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0b964-114">To construct the <`ProductCategory`> element, you can write a `FOR XML` query as shown in the following:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName  
FROM Production.ProductCategory ProdCat  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="0b964-115">Risultato:</span><span class="sxs-lookup"><span data-stu-id="0b964-115">This is the result:</span></span>  
  
```  
< ProdCat ProductCategoryID="1" CategoryName="Bikes" />  
< ProdCat ProductCategoryID="2" CategoryName="Components" />  
< ProdCat ProductCategoryID="3" CategoryName="Clothing" />  
< ProdCat ProductCategoryID="4" CategoryName="Accessories" />  
```  
  
 <span data-ttu-id="0b964-116">Per costruire gli elementi <`ProductSubCategory`> nidificati nel valore XML, è quindi necessario aggiungere una query `FOR XML` nidificata, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0b964-116">To construct the nested <`ProductSubCategory`> elements in the XML you want, you then add a nested `FOR XML` query, as shown in the following:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName,  
       (SELECT ProductSubCategoryID, Name SubCategoryName  
        FROM   Production.ProductSubCategory  
        WHERE ProductSubCategory.ProductCategoryID =   
              ProductCategory.ProductCategoryID  
        FOR XML AUTO, TYPE, ELEMENTS  
       )  
FROM Production.ProductCategory  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="0b964-117">Dalla query precedente si noti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0b964-117">Note the following in the previous query:</span></span>  
  
-   <span data-ttu-id="0b964-118">La query `FOR XML` interna recupera informazioni sulla sottocategoria del prodotto.</span><span class="sxs-lookup"><span data-stu-id="0b964-118">The inner `FOR XML` query retrieves product subcategory information.</span></span> <span data-ttu-id="0b964-119">Nella query `ELEMENTS` interna viene aggiunta la direttiva `FOR XML` per generare un valore XML incentrato sugli elementi, che verrà aggiunto al valore XML generato dalla query esterna.</span><span class="sxs-lookup"><span data-stu-id="0b964-119">The `ELEMENTS` directive is added in the inner `FOR XML` to generate element-centric XML that is added to the XML generated by the outer query.</span></span> <span data-ttu-id="0b964-120">Per impostazione predefinita la query esterna genera un valore XML incentrato sugli attributi.</span><span class="sxs-lookup"><span data-stu-id="0b964-120">By default, the outer query generates attribute-centric XML.</span></span>  
  
-   <span data-ttu-id="0b964-121">Nella query interna è specificata la direttiva `TYPE` in modo che venga restituito un risultato di tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="0b964-121">In the inner query, the `TYPE` directive is specified so the result is of **xml** type.</span></span> <span data-ttu-id="0b964-122">Se la direttiva `TYPE` non viene specificata, verrà restituito un risultato di tipo `nvarchar(max)` e i dati XML verranno restituiti come entità.</span><span class="sxs-lookup"><span data-stu-id="0b964-122">If `TYPE` is not specified, the result is returned as `nvarchar(max)` type and the XML data is returned as entities.</span></span>  
  
-   <span data-ttu-id="0b964-123">Poiché la direttiva `TYPE` è specificata anche nella query esterna,</span><span class="sxs-lookup"><span data-stu-id="0b964-123">The outer query also specifies the `TYPE` directive.</span></span> <span data-ttu-id="0b964-124">il risultato della query verrà restituito al client come tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="0b964-124">Therefore, the result of this query is returned to the client as **xml** type.</span></span>  
  
 <span data-ttu-id="0b964-125">Risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="0b964-125">This is the partial result:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bike</SubCategoryName></ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  <ProductSubCategory>  
     ...  
</ProductCategory>  
```  
  
 <span data-ttu-id="0b964-126">La query seguente è semplicemente un'estensione della precedente.</span><span class="sxs-lookup"><span data-stu-id="0b964-126">The following query is just an extension of the previous query.</span></span> <span data-ttu-id="0b964-127">Visualizza la gerarchia dei prodotti completa nel database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] ,</span><span class="sxs-lookup"><span data-stu-id="0b964-127">It shows the full product hierarchy in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="0b964-128">Sono inclusi gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b964-128">This includes the following:</span></span>  
  
-   <span data-ttu-id="0b964-129">Categorie di prodotti</span><span class="sxs-lookup"><span data-stu-id="0b964-129">Product categories</span></span>  
  
-   <span data-ttu-id="0b964-130">Sottocategorie di prodotti in ogni categoria</span><span class="sxs-lookup"><span data-stu-id="0b964-130">Product subcategories in each category</span></span>  
  
-   <span data-ttu-id="0b964-131">Modelli di prodotti in ogni sottocategoria</span><span class="sxs-lookup"><span data-stu-id="0b964-131">Product models in each subcategory</span></span>  
  
-   <span data-ttu-id="0b964-132">Prodotti per ogni modello</span><span class="sxs-lookup"><span data-stu-id="0b964-132">Products in each model</span></span>  
  
 <span data-ttu-id="0b964-133">Per comprendere l'organizzazione del database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , è possibile utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="0b964-133">You might find the following query useful in understanding the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName,  
       (SELECT ProductSubCategoryID, Name SubCategoryName,  
               (SELECT ProductModel.ProductModelID,   
                       ProductModel.Name as ModelName,  
                       (SELECT ProductID, Name as ProductName, Color  
                        FROM   Production.Product  
                        WHERE  Product.ProductModelID =   
                               ProductModel.ProductModelID  
                        FOR XML AUTO, TYPE)  
                FROM   (SELECT distinct ProductModel.ProductModelID,   
                               ProductModel.Name  
                        FROM   Production.ProductModel,   
                               Production.Product  
                        WHERE  ProductModel.ProductModelID =   
                               Product.ProductModelID  
                        AND    Product.ProductSubCategoryID =   
                               ProductSubCategory.ProductSubCategoryID)   
                                  ProductModel  
                FOR XML AUTO, type  
               )  
        FROM Production.ProductSubCategory  
        WHERE ProductSubCategory.ProductCategoryID =   
              ProductCategory.ProductCategoryID  
        FOR XML AUTO, TYPE, ELEMENTS  
       )  
FROM Production.ProductCategory  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="0b964-134">Risultato parziale:</span><span class="sxs-lookup"><span data-stu-id="0b964-134">This is the partial result:</span></span>  
  
```  
<Production.ProductCategory ProductCategoryID="1" CategoryName="Bikes">  
  <Production.ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bikes</SubCategoryName>  
    <ProductModel ProductModelID="19" ModelName="Mountain-100">  
      <Production.Product ProductID="771"   
                ProductName="Mountain-100 Silver, 38" Color="Silver" />  
      <Production.Product ProductID="772"   
                ProductName="Mountain-100 Silver, 42" Color="Silver" />  
      <Production.Product ProductID="773"   
                ProductName="Mountain-100 Silver, 44" Color="Silver" />  
        ...  
    </ProductModel>  
     ...  
```  
  
 <span data-ttu-id="0b964-135">Se si rimuove la direttiva `ELEMENTS` dalla query `FOR XML` nidificata che genera le sottocategorie di prodotti, il risultato sarà interamente incentrato sugli attributi.</span><span class="sxs-lookup"><span data-stu-id="0b964-135">If you remove the `ELEMENTS` directive from the nested `FOR XML` query that generates product subcategories, the whole result is attribute-centric.</span></span> <span data-ttu-id="0b964-136">È pertanto possibile scrivere questa query senza nidificazione.</span><span class="sxs-lookup"><span data-stu-id="0b964-136">You can then write this query without nesting.</span></span> <span data-ttu-id="0b964-137">L'aggiunta della direttiva `ELEMENTS` consente di ottenere un valore XML incentrato in parte sugli attributi ed in parte sugli elementi.</span><span class="sxs-lookup"><span data-stu-id="0b964-137">The addition of `ELEMENTS` results in an XML that is partly attribute-centric and partly element-centric.</span></span> <span data-ttu-id="0b964-138">Questo tipo di risultato non può essere generato da una query FOR XML con un solo livello.</span><span class="sxs-lookup"><span data-stu-id="0b964-138">This result cannot be generated by a single-level, FOR XML query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b964-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b964-139">See Also</span></span>  
 [<span data-ttu-id="0b964-140">Utilizzo di query FOR XML nidificate</span><span class="sxs-lookup"><span data-stu-id="0b964-140">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
