---
title: Estensione della funzionalità OLAP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 49a17ff3-94e9-4969-84fc-37d49e63933b
author: minewiskan
ms.author: owend
ms.openlocfilehash: d64d1ac46e2571aa6f8065a8ea42e4cc43aa589e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638113"
---
# <a name="extending-olap-functionality"></a><span data-ttu-id="d390b-102">Estensione delle funzionalità OLAP</span><span class="sxs-lookup"><span data-stu-id="d390b-102">Extending OLAP functionality</span></span>
  <span data-ttu-id="d390b-103">I programmatori possono estendere Analysis Services mediante la scrittura di assembly, estensioni personalizzate e stored procedure che forniscono le funzionalità che si desidera utilizzare e ridefinire in più applicazioni di database.</span><span class="sxs-lookup"><span data-stu-id="d390b-103">As a programmer, you can extend Analysis Services by writing assemblies, personalized extensions, and stored procedures that provide functionality you want to use and repurpose in multiple database applications.</span></span> <span data-ttu-id="d390b-104">Gli assembly vengono utilizzati per estendere le funzionalità dei modelli multidimensionali mediante l'aggiunta di nuove procedure e funzioni al linguaggio MDX o per mezzo del componente aggiuntivo di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="d390b-104">Assemblies are used to extend multidimensional models functionality by adding new procedures and functions to the MDX language or by means of the personalization addin.</span></span>  
  
 <span data-ttu-id="d390b-105">Consentendo di sviluppare il codice comune una sola volta e di archiviarlo in una singola posizione, le stored procedure possono essere utilizzare per chiamare routine esterne, semplificando le operazioni di sviluppo e di implementazione del database di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d390b-105">Stored procedures can be used to call external routines, simplifying Analysis Services database development and implementation by allowing common code to be developed once and stored in a single location.</span></span> <span data-ttu-id="d390b-106">Possono essere utilizzate per aggiungere alle applicazioni funzionalità business non presenti in quelle native di MDX.</span><span class="sxs-lookup"><span data-stu-id="d390b-106">Stored procedures can be used to add business functionality to your applications that is not provided by the native functionality of MDX.</span></span>  
  
 <span data-ttu-id="d390b-107">Le personalizzazioni sono oggetti personalizzati che si aggiungono a un cubo per fornire un comportamento che varia in base all'utente.</span><span class="sxs-lookup"><span data-stu-id="d390b-107">Personalizations are custom objects that you add to a cube to provide a behavior that varies by user.</span></span> <span data-ttu-id="d390b-108">Le personalizzazioni non sono oggetti permanenti nel cubo, ma oggetti utilizzati in modo dinamico dall'applicazione client durante la sessione utente.</span><span class="sxs-lookup"><span data-stu-id="d390b-108">Personalizations are not permanent objects in the cube, but are objects that the client application applies dynamically during the user's session.</span></span> <span data-ttu-id="d390b-109">Gli esempi includono la modifica della valuta di un valore valutario a seconda della persona che accede ai dati, la fornitura di indicatori KPI individualizzati o un elenco di suggerimenti di destinazione per clienti regolari che acquistano online.</span><span class="sxs-lookup"><span data-stu-id="d390b-109">Examples include changing the currency of a monetary value depending on the person accessing the data, providing individualized KPIs, or a targeted suggestion list for regular customers who purchase online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d390b-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d390b-110">In This Section</span></span>  
 [<span data-ttu-id="d390b-111">Estensione di OLAP tramite personalizzazioni</span><span class="sxs-lookup"><span data-stu-id="d390b-111">Extending OLAP through personalizations</span></span>](extending-olap-through-personalizations.md)  
  
 [<span data-ttu-id="d390b-112">Analysis Services Personalization Extensions</span><span class="sxs-lookup"><span data-stu-id="d390b-112">Analysis Services Personalization Extensions</span></span>](analysis-services-personalization-extensions.md)  
  
 [<span data-ttu-id="d390b-113">Definizione di stored procedure</span><span class="sxs-lookup"><span data-stu-id="d390b-113">Defining Stored Procedures</span></span>](../../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
