---
title: Linee guida e limitazioni di SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, about SQLXML
ms.assetid: fe433d30-90a1-421e-85c6-af13294dc18d
author: rothja
ms.author: jroth
ms.openlocfilehash: e020cbf0ac32e4c878b0b74b67e7c9c679d5d178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623119"
---
# <a name="guidelines-and-limitations-of-sqlxml-40"></a><span data-ttu-id="14cbb-102">Linee guida e limitazioni di SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="14cbb-102">Guidelines and Limitations of SQLXML 4.0</span></span>
  <span data-ttu-id="14cbb-103">Quando si utilizza SQLXML 4.0, tenere presenti le considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="14cbb-103">Remember the following when working with SQLXML 4.0:</span></span>  
  
-   <span data-ttu-id="14cbb-104">Il codice XML restituito come risultato della query non viene convalidato rispetto allo schema di mapping che lo ha generato.</span><span class="sxs-lookup"><span data-stu-id="14cbb-104">XML returned as a query result is not validated against the mapping schema that generated the XML.</span></span>  
  
-   <span data-ttu-id="14cbb-105">In SQLXML 4.0 sono inclusi i PROGID dipendenti e quelli indipendenti dalla versione.</span><span class="sxs-lookup"><span data-stu-id="14cbb-105">SQLXML 4.0 includes version-independent and version-dependent PROGIDs.</span></span> <span data-ttu-id="14cbb-106">Per tutte le applicazioni di produzione è consigliabile utilizzare i PROGID dipendenti dalla versione.</span><span class="sxs-lookup"><span data-stu-id="14cbb-106">It is recommended that all production applications use version-dependent PROGIDs.</span></span> <span data-ttu-id="14cbb-107">Questo aspetto è particolarmente importante perché SQLXML 4.0 non è completamente compatibile con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="14cbb-107">This is especially important because SQLXML 4.0 is not fully backward compatible.</span></span> <span data-ttu-id="14cbb-108">L'utilizzo di PROGID dipendenti dalla versione protegge da possibili errori di produzione quando si installano le versioni più recenti.</span><span class="sxs-lookup"><span data-stu-id="14cbb-108">Using version dependent PROGIDs protects from possible production failures when you install newer releases.</span></span> <span data-ttu-id="14cbb-109">Nelle diverse versioni il comportamento del programma può cambiare per molti motivi, ad esempio per correzioni di bug, per possibili modifiche di progettazione e così via.</span><span class="sxs-lookup"><span data-stu-id="14cbb-109">From release to release, program behavior may change for a variety of reasons, such as bug fixes, possible design changes, and so on.</span></span> <span data-ttu-id="14cbb-110">L'utilizzo di PROGID dipendenti dalla versione protegge da errori imprevisti quando si installano le versioni più recenti.</span><span class="sxs-lookup"><span data-stu-id="14cbb-110">Using version-dependent PROGIDs protects from unexpected failure when you install newer releases.</span></span> <span data-ttu-id="14cbb-111">Grazie ai PROGID dipendenti dalla versione, quando si installa una versione più recente, l'applicazione continuerà a funzionare senza errori.</span><span class="sxs-lookup"><span data-stu-id="14cbb-111">With version-dependent PROGIDs, when you install a newer release, your application will continue to work without failure.</span></span> <span data-ttu-id="14cbb-112">Se si decide di modificare i PROGID dipendenti dalla versione precedenti e di utilizzare quelli recenti di una versione più nuova, è necessario testare l'applicazione prima di inserirli in produzione.</span><span class="sxs-lookup"><span data-stu-id="14cbb-112">If you decide to change the previous version-dependent PROGIDs and use the recent version-dependent PROGIDs in a newer release, you must test your application before putting it into production.</span></span> <span data-ttu-id="14cbb-113">Ad esempio, le applicazioni che utilizzando i PROGID indipendenti dalla versione possono generare errori nello scenario seguente:</span><span class="sxs-lookup"><span data-stu-id="14cbb-113">For example, applications using version-independent PROGIDs may fail in the following scenario:</span></span>  
  
     <span data-ttu-id="14cbb-114">Si esegue un'applicazione che utilizza SQLXML 4.0 e i PROGID indipendenti dalla versione e si decide di installare un altro programma software.</span><span class="sxs-lookup"><span data-stu-id="14cbb-114">You are running an application that uses SQLXML 4.0 and version-independent PROGIDs, and you decide to install some other software program.</span></span> <span data-ttu-id="14cbb-115">Questo programma potrebbe installare una versione precedente di SQLXML.</span><span class="sxs-lookup"><span data-stu-id="14cbb-115">This program might install an earlier version of SQLXML.</span></span> <span data-ttu-id="14cbb-116">L'applicazione può avere esito negativo poiché i PROGID indipendenti dalla versione dell'applicazione puntano ora alla versione precedente di SQLXML che può disporre o meno della caratteristica SQLXML utilizzata dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="14cbb-116">Your application may fail because the version-independent PROGIDS in your application now point to the earlier version of SQLXML, which may or may not have the SQLXML feature that your application is using.</span></span>  
  
-   <span data-ttu-id="14cbb-117">Se per qualsiasi motivo non si desidera utilizzare il provider SQLXMLOLEDB e si desidera utilizzare invece il provider SQLOLEDB per le funzionalità SQLXML, impostare la proprietà della **versione SQLXML** su "SQLXML. 4.0".</span><span class="sxs-lookup"><span data-stu-id="14cbb-117">If for any reason you don't want to use the SQLXMLOLEDB provider, and instead want to use the SQLOLEDB provider for SQLXML features, set the **SQLXML Version** property to "SQLXML.4.0".</span></span>  
  
  
