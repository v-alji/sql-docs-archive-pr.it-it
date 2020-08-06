---
title: 'Attività 6: impostazione di sinonimi | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: b7d35ee9-d1c9-41d9-bbc5-0ca7db93e54d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bde0c0ec7f230ba2325aa01328b191fd8fd67fa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623653"
---
# <a name="task-6-setting-synonyms"></a><span data-ttu-id="94de7-102">Attività 6: Impostazione di sinonimi</span><span class="sxs-lookup"><span data-stu-id="94de7-102">Task 6: Setting Synonyms</span></span>
  <span data-ttu-id="94de7-103">In questa attività vengono impostati due valori di dominio, **Stati Uniti** e **Stati Uniti**, del dominio **Country** come sinonimi con **Stati Uniti** come valore principale.</span><span class="sxs-lookup"><span data-stu-id="94de7-103">In this task, you set two domain values, **USA** and **United States**, of the **Country** domain as synonyms with **United States** as the leading value.</span></span> <span data-ttu-id="94de7-104">Poiché l'opzione **Usa valori iniziali** è stata selezionata durante la creazione del dominio **Country** , tutti i valori **USA** per il dominio **Country** verranno restituiti come **Stati Uniti** (Stati Uniti è il valore principale).</span><span class="sxs-lookup"><span data-stu-id="94de7-104">Since the **Use Leading Values** option was selected when creating the **Country** domain, any **USA** values for the **Country** domain will be output as **United States** (as United States is the leading value).</span></span> <span data-ttu-id="94de7-105">Per altri dettagli, vedere [modificare i valori di dominio](https://msdn.microsoft.com/library/hh510408.aspx) .</span><span class="sxs-lookup"><span data-stu-id="94de7-105">See [Change Domain Values](https://msdn.microsoft.com/library/hh510408.aspx) for more details.</span></span>

1.  <span data-ttu-id="94de7-106">Selezionare **Country** nell'elenco dei domini.</span><span class="sxs-lookup"><span data-stu-id="94de7-106">Select **Country** from the list of domains.</span></span>

2.  <span data-ttu-id="94de7-107">Passare alla scheda **valori di dominio** .</span><span class="sxs-lookup"><span data-stu-id="94de7-107">Switch to the **Domain Values** tab.</span></span>

3.  <span data-ttu-id="94de7-108">Fare clic sul pulsante **Aggiungi nuovo valore di dominio** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="94de7-108">Click **Add new domain value** button on the toolbar.</span></span>

4.  <span data-ttu-id="94de7-109">Digitare **USA** per il valore e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="94de7-109">Type **USA** for the value and press **ENTER**.</span></span>

5.  <span data-ttu-id="94de7-110">Selezionare **Stati Uniti** e **USA** con il tasto CTRL o MAIUSC, fare clic con il pulsante destro del mouse sugli elementi selezionati e quindi scegliere **Imposta come sinonimi**.</span><span class="sxs-lookup"><span data-stu-id="94de7-110">Multiselect **United States** and **USA** using CTRL or SHIFT keys, right-click the selected items, and then click **Set as Synonyms**.</span></span> <span data-ttu-id="94de7-111">Tramite DQS questi valori vengono raggruppati e uno di essi viene definito come valore iniziale con cui vengono sostituiti gli altri valori.</span><span class="sxs-lookup"><span data-stu-id="94de7-111">DQS groups these values and designate one of the values as the leading value that the other values are replaced with.</span></span>

     <span data-ttu-id="94de7-112">![Menu Imposta come sinonimi](../../2014/tutorials/media/et-settingsynonyms-01.jpg "Menu Imposta come sinonimi")</span><span class="sxs-lookup"><span data-stu-id="94de7-112">![Set as Synonyms Menu](../../2014/tutorials/media/et-settingsynonyms-01.jpg "Set as Synonyms Menu")</span></span>

6.  <span data-ttu-id="94de7-113">Si noti che **Stati Uniti** è impostato come valore principale.</span><span class="sxs-lookup"><span data-stu-id="94de7-113">Notice that **United States** is set as the leading value.</span></span> <span data-ttu-id="94de7-114">Se si vuole che gli Stati Uniti siano i valori iniziali, è possibile fare clic con il pulsante destro del mouse su USA e selezionare **Imposta come opzione leader** .</span><span class="sxs-lookup"><span data-stu-id="94de7-114">If you want USA to be the leading value, you can right-click on USA and select **Set as Leading** option.</span></span> <span data-ttu-id="94de7-115">Per questa esercitazione si userà **Stati Uniti** come valore principale.</span><span class="sxs-lookup"><span data-stu-id="94de7-115">For this tutorial, we use **United States** as the leading value.</span></span>

     <span data-ttu-id="94de7-116">![Stati Uniti e USA come sinonimi](../../2014/tutorials/media/et-settingsynonyms-02.jpg "Stati Uniti e USA come sinonimi")</span><span class="sxs-lookup"><span data-stu-id="94de7-116">![United States and USA as Synonyms](../../2014/tutorials/media/et-settingsynonyms-02.jpg "United States and USA as Synonyms")</span></span>

## <a name="next-step"></a><span data-ttu-id="94de7-117">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="94de7-117">Next Step</span></span>
 [<span data-ttu-id="94de7-118">Attività 7: Creazione di un dominio composito</span><span class="sxs-lookup"><span data-stu-id="94de7-118">Task 7: Creating a Composite Domain</span></span>](../../2014/tutorials/task-7-creating-a-composite-domain.md)


