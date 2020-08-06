---
title: Proprietà e comportamenti dei set di righe | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowsets [OLE DB], properties
- SQL Server Native Client OLE DB provider, rowsets
- properties [OLE DB]
- OLE DB rowsets, properties
ms.assetid: 9baabcb6-0114-42f2-89f8-d8d66b3c8c14
author: rothja
ms.author: jroth
ms.openlocfilehash: 1158650b8029aed9447ce4d11e4273314ad0aa94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626086"
---
# <a name="rowset-properties-and-behaviors"></a>Proprietà e comportamenti dei set di righe
  Si tratta delle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proprietà del set di righe del provider OLE DB Native Client.  
  
|ID proprietà|Descrizione|  
|-----------------|-----------------|  
|DBPROP_ABORTPRESERVE|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: il comportamento di un set di righe in seguito a un'operazione di interruzione è determinato da questa proprietà.<br /><br /> VARIANT_FALSE: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client invalida i set di righe dopo un'operazione di interruzione. Le funzionalità dell'oggetto set di righe andranno perdute quasi del tutto. Supporta solo operazioni **IUnknown** e il rilascio di handle di riga e di funzione di accesso in attesa.<br /><br /> VARIANT_TRUE: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client gestisce un set di righe valido.|  
|DBPROP_ACCESSORDER|R/W (L/S): Lettura/Scrittura<br /><br /> Impostazione predefinita: DBPROPVAL_AO_RANDOM<br /><br /> Descrizione: ordine di accesso. Ordine in cui è necessario accedere alle colonne nel set di righe.<br /><br /> DBPROPVAL_AO_RANDOM: è possibile accedere alla colonna in qualsiasi ordine.<br /><br /> DBPROPVAL_AO_SEQUENTIALSTORAGEOBJECTS: è possibile accedere a colonne associate come oggetti di archiviazione solo in ordine sequenziale, determinato dall'ordinale di colonna.<br /><br /> DBPROPVAL_AO_SEQUENTIAL: è necessario accedere a tutte le colonne in ordine sequenziale, determinato dall'ordinale di colonna.|  
|DBPROP_APPENDONLY|Questa proprietà del set di righe non è implementata dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client. Il tentativo di lettura o scrittura del valore della proprietà genera un errore.|  
|DBPROP_BLOCKINGSTORAGEOBJECTS|L/S: Sola lettura<br /><br /> Impostazione predefinita: VARIANT_TRUE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] blocco degli oggetti di archiviazione del provider OLE DB di Native client usa altri metodi del set di righe.|  
|DBPROP_BOOKMARKS DBPROP_LITERALBOOKMARKS|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta segnalibri per l'identificazione delle righe del set di righe quando DBPROP_BOOKMARKS o DBPROP_LITERALBOOKMARKS è VARIANT_TRUE.<br /><br /> L'impostazione di una delle proprietà su VARIANT_TRUE non consente il posizionamento del set di righe in base al segnalibro. Impostare DBPROP_IRowsetLocate o DBPROP_IRowsetScroll su VARIANT_TRUE per creare un set di righe che supporta il posizionamento dei set di righe in base al segnalibro.<br /><br /> Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client utilizza un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursore per supportare un set di righe contenente segnalibri. Per altre informazioni, vedere [Set di righe e cursori SQL Server](rowsets-and-sql-server-cursors.md). **Nota:**  L'impostazione di queste proprietà in conflitto con altre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proprietà di definizione del cursore del provider OLE DB Native client causa un errore. Impostando, ad esempio, DBPROP_BOOKMARKS su VARIANT_TRUE quando anche DBPROP_OTHERINSERT è VARIANT_TRUE, viene generato un errore durante il tentativo di apertura di un set di righe da parte di un consumer.|  
|DBPROP_BOOKMARKSKIPPED|L/S: Sola lettura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client restituisce DB_E_BADBOOKMARK se il consumer indica un segnalibro non valido durante il posizionamento o la ricerca di un set di righe con segnalibro.|  
|DBPROP_BOOKMARKTYPE|L/S: Sola lettura<br /><br /> Impostazione predefinita: DBPROPVAL_BMK_NUMERIC<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client implementa solo i segnalibri numerici. Un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] segnalibro del provider OLE DB di Native Client è Unsigned Integer a 32 bit, digitare DBTYPE_UI4.|  
|DBPROP_CACHEDEFERRED|Questa proprietà del set di righe non è implementata dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client. Il tentativo di lettura o scrittura del valore della proprietà genera un errore.|  
|DBPROP_CANFETCHBACKWARDS DBPROP_CANSCROLLBACKWARDS|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta il recupero e lo scorrimento indietro nei set di righe non sequenziali. Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client crea un set di righe supportato dal cursore quando DBPROP_CANFETCHBACKWARDS o DBPROP_CANSCROLLBACKWARDS è VARIANT_TRUE. Per altre informazioni, vedere [Set di righe e cursori SQL Server](rowsets-and-sql-server-cursors.md).|  
|DBPROP_CANHOLDROWS|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: per impostazione predefinita, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client restituisce DB_E_ROWSNOTRELEASED se il consumer tenta di ottenere più righe per un set di righe mentre sono presenti modifiche in sospeso su quelle attualmente presenti nel set di righe. È possibile modificare questo comportamento.<br /><br /> L'impostazione di DBPROP_CANHOLDROWS e DBPROP_IRowsetChange su VARIANT_TRUE produce un set di righe con segnalibro. Se entrambe le proprietà sono VARIANT_TRUE, l'interfaccia **IRowsetLocate** è disponibile nel set di righe e DBPROP_BOOKMARKS e DBPROP_LITERALBOOKMARKS sono entrambe VARIANT_TRUE.<br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]I set di righe del provider OLE DB di Native client contenenti segnalibri sono supportati dai [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursori.|  
|DBPROP_CHANGEINSERTEDROWS|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: questa proprietà può essere impostata solo su VARIANT_TRUE se il set di righe utilizza un cursore gestito da keyset.|  
|DBPROP_COLUMNRESTRICT|L/S: Sola lettura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client imposta la proprietà su VARIANT_TRUE quando una colonna in un set di righe non può essere modificata dal consumer. È possibile che le altre colonne nel set di righe siano aggiornabili e le righe stesse possano essere eliminate.<br /><br /> Quando la proprietà è VARIANT_TRUE, il consumer esamina il membro *dwFlags* della struttura DBCOLUMNINFO per determinare se è possibile o meno scrivere il valore di una singola colonna. Per le colonne modificabili, *dwFlags* indica DBCOLUMNFLAGS_WRITE.|  
|DBPROP_COMMANDTIMEOUT|R/W (L/S): Lettura/Scrittura<br /><br /> Impostazione predefinita: 0<br /><br /> Descrizione: per impostazione predefinita, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non si timeout nel metodo **ICommand:: Execute** .|  
|DBPROP_COMMITPRESERVE|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: il comportamento di un set di righe in seguito a un'operazione di commit è determinato da questa proprietà.<br /><br /> VARIANT_TRUE: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client gestisce un set di righe valido.<br /><br /> VARIANT_FALSE: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client invalida i set di righe dopo un'operazione di commit. Le funzionalità dell'oggetto set di righe andranno perdute quasi del tutto. Supporta solo operazioni **IUnknown** e il rilascio di handle di riga e di funzione di accesso in attesa.|  
|DBPROP_DEFERRED|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: se impostata su VARIANT_TRUE il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native client tenta di utilizzare un cursore server per il set di righe. Le colonne di tipo **text**, **ntext** e **image** non vengono restituite dal server fino a quando l'applicazione non vi accede.|  
|DBPROP_DELAYSTORAGEOBJECTS|L/S: Sola lettura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta la modalità di aggiornamento immediato sugli oggetti di archiviazione.<br /><br /> Le modifiche apportate ai dati in un oggetto flusso sequenziale vengono immediatamente inviate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Viene eseguito il commit delle modifiche in base alla modalità di transazione del set di righe.|  
|DBPROP_HIDDENCOLUMNS|L/S: Sola lettura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> **Descrizione:** numero di colonne nascoste<br /><br /> Se DBPROP_UNIQUEROWS è VARIANT_TRUE, la proprietà DBPROP_HIDDENCOLUMNS restituisce il numero di colonne nascoste (hidden) aggiuntive inserite dal provider per identificare in modo univoco le righe all'interno del set di righe. Queste colonne vengono restituite da **IColumnsInfo::GetColumnInfo** e **IColumnsRowset::GetColumnsRowset**. Non sono tuttavia incluse nel conteggio delle righe restituite dall'argomento *pcColumns* restituito da **IColumnsInfo::GetColumnInfo**.<br /><br /> Per determinare il numero totale di colonne rappresentate nella struttura *prgInfo* restituita da **IColumnsInfo::GetColumnInfo**, incluse le colonne nascoste, il consumer aggiunge il valore di DBPROP_HIDDENCOLUMNS al conteggio delle colonne restituite da **IColumnsInfo::GetColumnInfo** in *pcColumns*. Se DBPROP_UNIQUEROWS è VARIANT_FALSE, il valore di DBPROP_HIDDENCOLUMNS è zero.|  
|DBPROP_IAccessor DBPROP_IColumnsInfo DBPROP_IConvertType DBPROP_IRowset DBPROP_IRowsetInfo|L/S: Sola lettura<br /><br /> Impostazione predefinita: VARIANT_TRUE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta queste interfacce su tutti i set di righe.|  
|DBPROP_IColumnsRowset|R/W (L/S): Lettura/Scrittura<br /><br /> Impostazione predefinita: VARIANT_TRUE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta l'interfaccia **IColumnsRowset** .|  
|DBPROP_IConnectionPointContainer|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: IConnectionPointContainer. Se impostata su VARIANT_TRUE, il set di righe supporta l'interfaccia specificata. Se impostata su VARIANT_FALSE, il set di righe non supporta l'interfaccia specificata. I provider che supportano un'interfaccia devono supportare la proprietà associata all'interfaccia con un valore VARIANT_TRUE. Tali proprietà vengono utilizzate principalmente per richiedere interfacce tramite ICommandProperties::SetProperties.|  
|DBPROP_IMultipleResults|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta l'interfaccia **IMultipleResults** .|  
|DBPROP_IRowsetChange DBPROP_IRowsetUpdate|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta le interfacce **IRowsetChange** e **IRowsetUpdate** .<br /><br /> Un set di righe creato tramite DBPROP_IRowsetChange uguale a VARIANT_TRUE indica comportamenti basati sulla modalità di aggiornamento immediato.<br /><br /> Quando DBPROP_IRowsetUpdate è VARIANT_TRUE, anche DBPROP_IRowsetChange è VARIANT_TRUE. Il set di righe indica un comportamento basato sulla modalità di aggiornamento posticipato.<br /><br /> Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client utilizza un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursore per supportare i set di righe che espongono **IRowsetChange** o **IRowsetUpdate**. Per altre informazioni, vedere [Set di righe e cursori SQL Server](rowsets-and-sql-server-cursors.md).|  
|DBPROP_IRowsetIdentity|R/W (L/S): Lettura/Scrittura<br /><br /> Impostazione predefinita: VARIANT_TRUE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta l'interfaccia **IRowsetIdentity** . Se un set di righe supporta questa interfaccia, qualsiasi coppia di handle di riga che rappresenta la stessa riga sottostante rifletterà sempre gli stessi dati e lo stesso stato. I consumer possono chiamare il metodo **IRowsetIdentity:: IsSameRow** per confrontare due handle di riga e determinare se fanno riferimento alla stessa istanza di riga.|  
|DBPROP_IRowsetLocate DBPROP_IRowsetScroll|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client può esporre le interfacce **IRowsetLocate** e **IRowsetScroll** .<br /><br /> Quando DBPROP_IRowsetLocate è VARIANT_TRUE, anche DBPROP_CANFETCHBACKWARDS e DBPROP_CANSCROLLBACKWARDS sono VARIANT_TRUE.<br /><br /> Se DBPROP_IRowsetScroll è VARIANT_TRUE, anche DBPROP_IRowsetLocate è VARIANT_TRUE ed entrambe le interfacce sono disponibili nel set di righe.<br /><br /> I segnalibri sono necessari per entrambe le interfacce. Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client imposta DBPROP_BOOKMARKS e DBPROP_LITERALBOOKMARKS su VARIANT_TRUE quando il consumer richiede una delle due interfacce.<br /><br /> Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client utilizza [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursori per supportare **IRowsetLocate** e **IRowsetScroll**. Per altre informazioni, vedere [Set di righe e cursori SQL Server](rowsets-and-sql-server-cursors.md).<br /><br /> L'impostazione di queste proprietà in conflitto con altre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proprietà di definizione del cursore del provider OLE DB Native client causa un errore. Impostando, ad esempio, DBPROP_IRowsetScroll su VARIANT_TRUE quando anche DBPROP_OTHERINSERT è VARIANT_TRUE, viene generato un errore durante il tentativo di apertura di un set di righe da parte del consumer.|  
|DBPROP_IRowsetResynch|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client espone l'interfaccia **IRowsetResynch** su richiesta. Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client può esporre l'interfaccia su qualsiasi set di righe.|  
|DBPROP_ISupportErrorInfo|R/W (L/S): Lettura/Scrittura<br /><br /> Impostazione predefinita: VARIANT_TRUE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client espone l'interfaccia **ISupportErrorInfo** nei set di righe.|  
|DBPROP_ILockBytes|Questa interfaccia non viene implementata dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client. Il tentativo di lettura o scrittura della proprietà genera un errore.|  
|DBPROP_ISequentialStream|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client espone l'interfaccia **ISequentialStream** per supportare i dati Long a lunghezza variabile archiviati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .|  
|DBPROP_IStorage|Questa interfaccia non viene implementata dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client. Il tentativo di lettura o scrittura della proprietà genera un errore.|  
|DBPROP_IStream|Questa interfaccia non viene implementata dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client. Il tentativo di lettura o scrittura della proprietà genera un errore.|  
|DBPROP_IMMOBILEROWS|R/W (L/S): Lettura/Scrittura<br /><br /> Impostazione predefinita: VARIANT_TRUE<br /><br /> Descrizione: la proprietà è VARIANT_TRUE solo per i cursori keyset [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mentre è VARIANT_FALSE per tutti gli altri cursori.<br /><br /> VARIANT_TRUE: il set di righe non riordinerà le righe inserite o aggiornate. Per **IRowsetChange::InsertRow**, le righe vengono visualizzate alla fine del set di righe. Per **IRowsetChange::SetData**, se il set di righe non viene ordinato, la posizione delle righe aggiornate non viene modificata. Se il set di righe viene ordinato e **IRowsetChange::SetData** modifica una colonna usata per ordinare il set di righe, la riga non viene spostata. Se il set di righe è basato su un set di colonne chiave, in genere un set di righe per cui DBPROP_OTHERUPDATEDELETE è VARIANT_TRUE ma DBPROP_OTHERINSERT è VARIANT_FALSE, la modifica del valore di una colonna chiave equivale in genere all'eliminazione della riga corrente e all'inserimento di una nuova. Può pertanto sembrare che la riga venga spostata o non più visualizzata nel set di righe, se DBPROP_OWNINSERT è VARIANT_FALSE, anche se la proprietà DBPROP_IMMOBILEROWS è VARIANT_TRUE.<br /><br /> VARIANT_FALSE: se il set di righe viene ordinato, le righe inserite vengono visualizzate nell'ordine corretto del set di righe. Se il set di righe non viene ordinato, la riga inserita viene visualizzata alla fine. Se **IRowsetChange::SetData** modifica una colonna usata per ordinare il set di righe, la riga viene spostata. Se il set di righe non viene ordinato, la posizione della riga non viene modificata.|  
|DBPROP_LITERALIDENTITY|L/S: Sola lettura<br /><br /> Impostazione predefinita: VARIANT_TRUE<br /><br /> Descrizione: questa proprietà è sempre VARIANT_TRUE.|  
|DBPROP_LOCKMODE|R/W (L/S): Lettura/Scrittura<br /><br /> Impostazione predefinita: DBPROPVAL_LM_NONE<br /><br /> Descrizione: livello di blocco eseguito dal set di righe (DBPROPVAL_LM_NONE, DBPROPVAL_LM_SINGLEROW). **Nota:**  Quando si utilizza l'isolamento dello snapshot in una transazione, se un set di righe viene aperto utilizzando un cursore keyset o Dynamic Server e la modalità di blocco è impostata su DBPROPVAL_LM_SINGLEROW, si verificherà un errore durante il recupero di una riga se un altro utente ha aggiornato la riga dall'avvio della transazione. Per altri tipi di cursore e modalità di blocco, se un altro utente ha aggiornato la riga dall'avvio della transazione, non si verifica alcun errore fino a quando l'utente non tenta di aggiornare la riga. In entrambi i casi, questi errori vengono generati dal server.|  
|DBPROP_MAXOPENROWS|L/S: Sola lettura<br /><br /> Impostazione predefinita: 0<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non limita il numero di righe che possono essere attive nei set di righe.|  
|DBPROP_MAXPENDINGROWS|L/S: Sola lettura<br /><br /> Impostazione predefinita: 0<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non limita il numero di righe del set di righe con modifiche in sospeso.|  
|DBPROP_MAXROWS|R/W (L/S): Lettura/Scrittura<br /><br /> Impostazione predefinita: 0<br /><br /> Descrizione: per impostazione predefinita, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non limita il numero di righe in un set di righe. Quando il consumer imposta DBPROP_MAXROWS, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native client utilizza l'istruzione SET ROWCOUNT per limitare il numero di righe nel set di righe.<br /><br /> SET ROWCOUNT può provocare conseguenze impreviste nell'esecuzione di istruzioni [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Per altre informazioni, vedere [SET ROWCOUNT](/sql/t-sql/statements/set-rowcount-transact-sql).|  
|DBPROP_MAYWRITECOLUMN|Questa proprietà del set di righe non è implementata dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client. Il tentativo di lettura o scrittura del valore della proprietà genera un errore.|  
|DBPROP_MEMORYUSAGE|Questa proprietà del set di righe non è implementata dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client. Il tentativo di lettura o scrittura del valore della proprietà genera un errore.|  
|DBPROP_NOTIFICATIONGRANULARITY|Questa proprietà del set di righe non è implementata dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client. Il tentativo di lettura o scrittura del valore della proprietà genera un errore.|  
|DBPROP_NOTIFICATIONPHASES|L/S: Sola lettura<br /><br /> Impostazione predefinita: DBPROPVAL_NP_OKTODO &#124; DBPROPVAL_NP_ABOUTTODO &#124;  DBPROPVAL_NP_SYNCHAFTER &#124; DBPROPVAL_NP_FAILEDTODO &#124;  DBPROPVAL_NP_DIDEVENT<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta tutte le fasi di notifica.|  
|DBPROP_NOTIFYCOLUMNSET DBPROP_NOTIFYROWDELETE DBPROP_NOTIFYROWFIRSTCHANGE DBPROP_NOTIFYROWINSERT DBPROP_NOTIFYROWRESYNCH DBPROP_NOTIFYROWSETRELEASE DBPROP_NOTIFYROWSETFETCH-POSITIONCHANGE DBPROP_NOTIFYROWUNDOCHANGE DBPROP_NOTIFYROWUNDODELETE DBPROP_NOTIFYROWUNDOINSERT DBPROP_NOTIFYROWUPDATE|L/S: Sola lettura<br /><br /> Impostazione predefinita: DBPROPVAL_NP_OKTODO &#124;  DBPROPVAL_NP_ABOUTTODO<br /><br /> Descrizione: le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fasi di notifica del provider OLE DB di Native Client sono annullabili prima di un tentativo di eseguire la modifica del set di righe indicata. Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non supporta l'annullamento della fase dopo il completamento del tentativo.|  
|DBPROP_ORDEREDBOOKMARKS|Questa proprietà del set di righe non è implementata dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client. Il tentativo di lettura o scrittura del valore della proprietà genera un errore.|  
|DBPROP_OTHERINSERT DBPROP_OTHERUPDATEDELETE DBPROP_OWNINSERT DBPROP_OWNUPDATEDELETE|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: l'impostazione delle proprietà di visibilità delle modifiche fa [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in modo che il provider OLE DB di Native Client utilizzi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] i cursori per supportare il set di righe. Per altre informazioni, vedere [Set di righe e cursori SQL Server](rowsets-and-sql-server-cursors.md).|  
|DBPROP_QUICKRESTART|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: se impostata su VARIANT_TRUE, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client tenta di utilizzare un cursore server per il set di righe.|  
|DBPROP_REENTRANTEVENTS|L/S: Sola lettura<br /><br /> Impostazione predefinita: VARIANT_TRUE<br /><br /> Descrizione: i [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] set di righe del provider di OLE DB di Native Client sono rientranti e possono restituire DB_E_NOTREENTRANT se un consumer tenta di accedere a un metodo del set di righe non-concorrente da un callback di notifica.|  
|DBPROP_REMOVEDELETED|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client modifica il valore della proprietà in base alla visibilità delle modifiche apportate ai [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dati esposti dal set di righe.<br /><br /> VARIANT_TRUE: le righe eliminate dal consumer o da altri utenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono rimosse dal set di righe quando questo viene aggiornato. DBPROP_OTHERINSERT è VARIANT_TRUE.<br /><br /> VARIANT_FALSE: le righe eliminate dal consumer o da altri utenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non vengono rimosse dal set di righe quando questo viene aggiornato. Il valore dello stato di riga per righe di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eliminate nel set di righe è DBROWSTATUS_E_DELETED. DBPROP_OTHERINSERT è VARIANT_TRUE.<br /><br /> Questa proprietà ha valore solo per i set di righe supportati da cursori [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Per altre informazioni, vedere [Set di righe e cursori SQL Server](rowsets-and-sql-server-cursors.md).<br /><br /> Quando la proprietà DBPROP_REMOVEDELETED viene implementata in un set di righe del cursore keyset, le righe eliminate vengono rimosse in fase di recupero ed è possibile che i metodi di recupero righe, ad esempio **GetNextRows** e **GetRowsAt**, restituiscano sia S_OK sia un numero minore di righe rispetto al necessario. Si noti che questo comportamento non implica la condizione DB_S_ENDOFROWSET. Inoltre, il numero di righe restituito non sarà mai pari a zero se vi sono righe rimanenti.|  
|DBPROP_REPORTMULTIPLECHANGES|Questa proprietà del set di righe non è implementata dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client. Il tentativo di lettura o scrittura del valore della proprietà genera un errore.|  
|DBPROP_RETURNPENDINGINSERTS|L/S: Sola lettura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: quando viene chiamato un metodo che recupera le righe, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non restituisce righe di inserimento in sospeso.|  
|DBPROP_ROWRESTRICT|L/S: Sola lettura<br /><br /> Impostazione predefinita: VARIANT_TRUE<br /><br /> Descrizione: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] i set di righe del provider OLE DB di Native client non supportano i diritti di accesso in base alla riga. Se l'interfaccia **IRowsetChange** è esposta in un set di righe, il metodo **SetData** può essere chiamato dal consumer.|  
|DBPROP_ROWSET_ASYNCH|R/W (L/S): Lettura/Scrittura<br /><br /> Impostazione predefinita: 0<br /><br /> Descrizione: fornisce l'elaborazione asincrona dei set di righe. Questa proprietà è inclusa nel gruppo di proprietà Rowset e nel set di proprietà DBPROPSET_ROWSET. Il tipo è VT_14.<br /><br /> L'unico valore nella maschera di bit supportato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client è `DBPROPVAL_ASYNCH_INITIALIZE`.|  
|DBPROP_ROWTHREADMODEL|L/S: Sola lettura<br /><br /> Impostazione predefinita: DBPROPVAL_RT_FREETHREAD<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta l'accesso ai relativi oggetti da più thread di esecuzione di un singolo consumer.|  
|DBPROP_SERVERCURSOR|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: se impostata, viene utilizzato un cursore [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per supportare il set di righe. Per altre informazioni, vedere [Set di righe e cursori SQL Server](rowsets-and-sql-server-cursors.md).|  
|DBPROP_SERVERDATAONINSERT|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: dati server in fase di inserimento.<br /><br /> VARIANT_TRUE: quando viene trasmesso un inserimento al server, il provider recupera dati dal server per aggiornare la cache locale delle righe.<br /><br /> VARIANT_FALSE: il provider non recupera valori server per le nuove righe inserite.|  
|DBPROP_STRONGIDENTITY|L/S: Sola lettura<br /><br /> Impostazione predefinita: VARIANT_TRUE<br /><br /> Descrizione: identità di riga sicura. Se in un set di righe gli inserimenti sono consentiti, ovvero se **IRowsetChange** o **IRowsetUpdate** è true, e la proprietà DBPROP_UPDATABILITY è impostata per il supporto di InsertRows, il valore di DBPROP_STRONGIDENTITY dipende dalla proprietà DBPROP_CHANGEINSERTEDROWS (è VARIANT_FALSE se il valore della proprietà DBPROP_CHANGEINSERTEDROWS è VARIANT_FALSE).|  
|DBPROP_TRANSACTEDOBJECT|L/S: Sola lettura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta solo oggetti transazionali. Per altre informazioni, vedere [Transazioni](../native-client-ole-db-transactions/transactions.md).|  
|DBPROP_UNIQUEROWS|R/W (L/S): Lettura/Scrittura<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: righe univoche.<br /><br /> VARIANT_TRUE: ogni riga viene identificata in modo univoco dai relativi valori di colonna. Per il set di colonne che identificano in modo univoco la riga, il set DBCOLUMNFLAGS_KEYCOLUMN nella struttura DBCOLUMNINFO viene restituito dal metodo **GetColumnInfo**.<br /><br /> VARIANT_FALSE: le righe possono o meno essere identificate in modo univoco dai relativi valori di colonna. Le colonne chiave possono o non possono essere contrassegnate con DBCOLUMNFLAGS_KEYCOLUMN.|  
|DBPROP_UPDATABILITY|R/W (L/S): Lettura/Scrittura<br /><br /> Impostazione predefinita: 0<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta tutti i valori DBPROP_UPDATABILITY. L'impostazione di DBPROP_UPDATABILITY non consente di creare un set di righe modificabile. Per rendere modificabile un set di righe, impostare DBPROP_IRowsetChange o DBPROP_IRowsetUpdate.|  
  
 Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client definisce il set di proprietà specifico del provider DBPROPSET_SQLSERVERROWSET, come illustrato in questa tabella.  
  
|ID proprietà|Descrizione|  
|-----------------|-----------------|  
|SSPROP_COLUMN_ID|Colonna: ColumnID<br /><br /> L/S: Sola lettura<br /><br /> Tipo: VT_U12 &#124; VT_ARRAY<br /><br /> Impostazione predefinita: VT_EMPTY<br /><br /> Descrizione: matrice di valori integer che rappresenta la posizione ordinale (base 1) di una colonna di risultati della clausola COMPUTE all'interno dell'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT. Si tratta dell' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] equivalente del provider di OLE DB di Native client dell'attributo ODBC SQL_CA_SS_COLUMN_ID.|  
|SSPROP_DEFERPREPARE|Colonna: No<br /><br /> R/W (L/S): Lettura/Scrittura<br /><br /> Digitare: VT_BOOL<br /><br /> Impostazione predefinita: VARIANT_TRUE<br /><br /> Descrizione: VARIANT_TRUE: in esecuzione preparata, la preparazione del comando è posticipata fino a quando non viene chiamato **ICommand::Execute** o non viene eseguita un'operazione di metaproprietà. Se la proprietà è impostata su<br /><br /> VARIANT_FALSE: l'istruzione viene preparata quando si esegue **ICommandPrepare::Prepare**.|  
|SSPROP_IRowsetFastLoad|Colonna: No<br /><br /> R/W (L/S): Lettura/Scrittura<br /><br /> Digitare: VT_BOOL<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: impostare questa proprietà su VARIANT_TRUE per aprire un set di righe di caricamento rapido con **IOpenRowset::OpenRowset**. Non è possibile impostare questa proprietà in **ICommandProperties::SetProperties**.|  
|SSPROP_ISSAsynchStatus|Colonna: nessuna<br /><br /> R/W (L/S): Lettura/Scrittura<br /><br /> Digitare: VT_BOOL<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: impostare questa proprietà su VARIANT_TRUE per consentire operazioni asincrone con l'interfaccia [ISSAsynchStatus](../../relational-databases/native-client-ole-db-interfaces/issasynchstatus-ole-db.md).|  
|SSPROP_MAXBLOBLENGTH|Colonna: No<br /><br /> R/W (L/S): Lettura/Scrittura<br /><br /> Tipo: VT_I4<br /><br /> Impostazione predefinita: Il provider non limita le dimensioni del testo restituito dal server e il valore della proprietà è impostato sul valore massimo, ad esempio 2147483647.<br /><br /> Descrizione: il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client esegue un'istruzione SET TEXTSIZE per limitare la lunghezza dei dati BLOB (Binary Large Object) restituiti in un'istruzione SELECT.|  
|SSPROP_NOCOUNT_STATUS|Colonna: NoCount<br /><br /> L/S: Sola lettura<br /><br /> Digitare: VT_BOOL<br /><br /> Predefinito: VARIANT_FALSE<br /><br /> Descrizione: valore booleano che rappresenta lo stato di SET NOCOUNT ON/OFF in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:<br /><br /> VARIANT_TRUE: con SET NOCOUNT ON<br /><br /> VARIANT_TRUE: con SET NOCOUNT OFF|  
|SSPROP_QP_NOTIFICATION_MSGTEXT|Colonna: No<br /><br /> R/W (L/S): Lettura/Scrittura<br /><br /> Tipo: VT_BSTR (1-2000 caratteri consentiti)<br /><br /> Impostazione predefinita: stringa vuota<br /><br /> Descrizione: testo del messaggio della notifica delle query. Il testo è definito dall'utente e non ha un formato definito.|  
|SSPROP_QP_NOTIFICATION_OPTIONS|Colonna: No<br /><br /> R/W (L/S): Lettura/Scrittura<br /><br /> Digitare: VT_BSTR<br /><br /> Impostazione predefinita: stringa vuota<br /><br /> Descrizione: opzioni di notifica delle query. Tali opzioni vengono specificate in una stringa con `name=value`. L'utente è responsabile della creazione del servizio e della lettura delle notifiche all'esterno della coda. La sintassi delle opzioni delle notifiche delle query è la seguente:<br /><br /> `service=<service-name>[;(local database=<database>&#124;broker instance=<broker instance>)]`<br /><br /> Ad esempio:<br /><br /> `service=mySSBService;local database=mydb`|  
|SSPROP_QP_NOTIFICATION_TIMEOUT|Colonna: No<br /><br /> R/W (L/S): Lettura/Scrittura<br /><br /> Tipo: VT_UI4<br /><br /> Impostazione predefinita: 432000 secondi (5 giorni)<br /><br /> Valore minimo: 1 secondo<br /><br /> Valore massimo: 2^31-1 secondi<br /><br /> Descrizione: numero di secondi durante i quali la notifica delle query deve rimanere attiva.|  
  
## <a name="see-also"></a>Vedere anche  
 [Set di righe](rowsets.md)  
  
  