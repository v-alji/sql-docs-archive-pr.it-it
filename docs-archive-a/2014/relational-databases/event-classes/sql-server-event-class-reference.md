---
title: Informazioni di riferimento sulle classi di evento di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 07/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- events [SQL Server], event classes
- event classes [SQL Server], listed
- event classes [SQL Server]
- SQL Server event classes, listed
- SQL Server event classes
ms.assetid: 0f0fe567-e115-4ace-b63c-73dc3428c0f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 177a2d13ec4479f1046a7f20adb3947f0607e781
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726980"
---
# <a name="sql-server-event-class-reference"></a>Guida di riferimento alla classe di evento SQL Server
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] consente di registrare gli eventi nel momento in cui vengono generati in un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] di [!INCLUDE[msCoName](../../includes/msconame-md.md)]. Gli eventi registrati corrispondono a istanze delle classi di evento nella definizione della traccia. In [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]le classi di evento e le rispettive categorie di eventi sono disponibili nella scheda **Selezione eventi** della finestra di dialogo **Proprietà file di traccia** .  
  
 Nella tabella seguente vengono descritte le categorie di eventi e le classi di evento associate.  
  
|Categoria di eventi|Classi di evento|  
|--------------------|-------------------|  
|Nella [categoria di eventi Broker](broker-event-category.md) sono incluse classi di evento generate dal [!INCLUDE[ssSB](../../includes/sssb-md.md)].|[Classe di evento Broker:Activation](broker-activation-event-class.md)<br /><br /> [Classe di evento Broker:Connection](broker-connection-event-class.md)<br /><br /> [Classe di evento Broker:Conversation](broker-conversation-event-class.md)<br /><br /> [Classe di evento Broker:Conversation Group](broker-conversation-group-event-class.md)<br /><br /> [Classe di evento Broker:Corrupted Message](broker-corrupted-message-event-class.md)<br /><br /> [Classe di evento Broker:Forwarded Message Dropped](broker-forwarded-message-dropped-event-class.md)<br /><br /> [Classe di evento Broker:Forwarded Message Sent](broker-forwarded-message-sent-event-class.md)<br /><br /> [Classe di evento Broker:Message Classify](broker-message-classify-event-class.md)<br /><br /> [Classe di evento Broker:Message Drop](broker-message-drop-event-class.md)<br /><br /> [Classe di evento Broker:Remote Message Ack](broker-remote-message-ack-event-class.md)|  
|Nella [categoria di eventi Cursori](cursors-event-category.md) sono incluse classi di evento generate dalle operazioni del cursore.|[Classe di evento CursorClose](cursorclose-event-class.md)<br /><br /> [Classe di evento CursorExecute](cursorexecute-event-class.md)<br /><br /> [Classe di evento CursorImplicitConversion](cursorimplicitconversion-event-class.md)<br /><br /> [Classe di evento CursorOpen](cursoropen-event-class.md)<br /><br /> [Classe di evento CursorPrepare](cursorprepare-event-class.md)<br /><br /> [Classe di evento CursorRecompile](cursorrecompile-event-class.md)<br /><br /> [Classe di evento CursorUnprepare](cursorunprepare-event-class.md)|  
|Nella [categoria di eventi CLR](clr-event-category.md) sono incluse classi di evento generate dall'esecuzione di oggetti CLR (Common Language Runtime) di .NET.|[Classe di evento Assembly Load](../../database-engine/assembly-load-event-class.md)|  
|Nella [categoria di eventi Database](database-event-category.md) sono incluse classi di evento generate dall'aumento o dalla riduzione automatica delle dimensioni dei file di dati o di log.|[Classe di evento Data File Auto Grow](data-file-auto-grow-event-class.md)<br /><br /> [Classe di evento Data File Auto Shrink](data-file-auto-shrink-event-class.md)<br /><br /> [Classe di evento Database Mirroring State Change](database-mirroring-state-change-event-class.md)<br /><br /> [Classe di evento Log File Auto Grow](log-file-auto-grow-event-class.md)<br /><br /> [Classe di evento Log File Auto Shrink](log-file-auto-shrink-event-class.md)|  
|Nella [categoria di eventi Deprecation](deprecation-event-category.md) sono inclusi eventi relativi a elementi deprecati.|[Classe di evento Deprecation Announcement](deprecation-announcement-event-class.md)<br /><br /> [Classe di evento Deprecation Final Support](deprecation-final-support-event-class.md)|  
|La [categoria di eventi Errors and warnings &#40;motore di database&#41;](errors-and-warnings-event-category-database-engine.md) include le classi di evento generate quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .|[Classe di evento Attention](attention-event-class.md)<br /><br /> [Classe di evento Background Job Error](background-job-error-event-class.md)<br /><br /> [Classe di evento Blocked Process Report](blocked-process-report-event-class.md)<br /><br /> [Classe di evento CPU Threshold Exceeded](cpu-threshold-exceeded-event-class.md)<br /><br /> [Classe di evento ErrorLog](errorlog-event-class.md)<br /><br /> [Classe di evento EventLog](eventlog-event-class.md)<br /><br /> [Classe di evento Exception](exception-event-class.md)<br /><br /> [Classe di evento Exchange Spill](exchange-spill-event-class.md)<br /><br /> [Classe di evento Execution Warnings](execution-warnings-event-class.md)<br /><br /> [Classe di evento Hash Warning](hash-warning-event-class.md)<br /><br /> [Classe di evento Missing Column Statistics](missing-column-statistics-event-class.md)<br /><br /> [Classe di evento Missing Join Predicate](missing-join-predicate-event-class.md)<br /><br /> [Classe di evento Sort Warnings](sort-warnings-event-class.md)<br /><br /> [Classe di evento User Error Message](user-error-message-event-class.md)|  
|Nella [categoria di eventi Full Text](full-text-event-category.md) sono incluse classi di evento generate dall'avvio, dalla sospensione o dall'arresto di ricerche full-text.|[Classe di evento FT:Crawl Aborted](ft-crawl-aborted-event-class.md)<br /><br /> [Classe di evento FT:Crawl Started](ft-crawl-started-event-class.md)<br /><br /> [Classe di evento FT:Crawl Stopped](ft-crawl-stopped-event-class.md)|  
|Nella [categoria di eventi Blocchi](locks-event-category.md) sono incluse classi di evento generate per l'acquisizione, l'annullamento o il rilascio di un blocco oppure quando vengono eseguite altre operazioni su un blocco.|[Classe di evento Deadlock Graph](deadlock-graph-event-class.md)<br /><br /> [Classe Lock:Acquired Event](lock-acquired-event-class.md)<br /><br /> [Classe di evento Lock:Cancel](lock-cancel-event-class.md)<br /><br /> [Classe di evento Lock:Deadlock Chain](lock-deadlock-chain-event-class.md)<br /><br /> [Classe di evento Lock:Deadlock](lock-deadlock-event-class.md)<br /><br /> [Classe di evento Lock:Escalation](lock-escalation-event-class.md)<br /><br /> [Classe di evento Lock:Released](lock-released-event-class.md)<br /><br /> [Lock:Timeout &#40;timeout &#62; 0&#41; Event Class](lock-timeout-timeout-0-event-class.md)<br /><br /> [Classe di evento Lock:Timeout](lock-timeout-event-class.md)|  
|Nella [categoria di eventi Objects](objects-event-category.md) sono incluse classi di evento generate dalla creazione, dall'apertura, dalla chiusura, dalla rimozione o dall'eliminazione di oggetti di database.|[Classe di evento Auto Stats](auto-stats-event-class.md)<br /><br /> [Classe di evento Object:Altered](object-altered-event-class.md)<br /><br /> [Classe di evento Object:Created](object-created-event-class.md)<br /><br /> [Classe di evento Object:Deleted](object-deleted-event-class.md)|  
|Nella [categoria di eventi OLEDB](oledb-event-category.md) sono incluse classi di evento generate da chiamate OLE DB.|[Classe di evento OLEDB Call](oledb-call-event-class.md)<br /><br /> [Classe di evento OLEDB DataRead](oledb-dataread-event-class.md)<br /><br /> [Classe di evento OLEDB Errors](oledb-errors-event-class.md)<br /><br /> [Classe di evento OLEDB Provider Information](oledb-provider-information-event-class.md)<br /><br /> [Classe di evento OLEDB QueryInterface](oledb-queryinterface-event-class.md)|  
|Nella [categoria di eventi Prestazioni](performance-event-category.md) sono incluse classi di evento generate con l'esecuzione di operatori DML (Data Manipulation Language) SQL.|[Classe di evento Degree of Parallelism &#40;7.0 Insert&#41;](degree-of-parallelism-7-0-insert-event-class.md)<br /><br /> [Classe di evento Performance Statistics](performance-statistics-event-class.md)<br /><br /> [Classe di evento Showplan All](showplan-all-event-class.md)<br /><br /> [Classe di evento Showplan All for Query Compile](showplan-all-for-query-compile-event-class.md)<br /><br /> [Classe di evento Showplan Statistics Profile](showplan-statistics-profile-event-class.md)<br /><br /> [Classe di evento Showplan Text](showplan-text-event-class.md)<br /><br /> [Classe di evento Showplan Text &#40;Unencoded&#41;](showplan-text-unencoded-event-class.md)<br /><br /> [Classe di evento Showplan XML](showplan-xml-event-class.md)<br /><br /> [Classe di evento Showplan XML For Query Compile](showplan-xml-for-query-compile-event-class.md)<br /><br /> [Classe di evento Showplan XML Statistics Profile](showplan-xml-statistics-profile-event-class.md)<br /><br /> [Classe di evento SQL:FullTextQuery](sql-fulltextquery-event-class.md)|  
|La [categoria di eventi Report di stato](progress-report-event-category.md) include la classe di evento **Progress Report: Online Index Operation**.|[Classe di evento Progress Report: Online Index Operation](progress-report-online-index-operation-event-class.md)|  
|Nella [categoria di eventi Analisi](scans-event-category.md) sono incluse classi di evento generate per l'analisi di tabelle e indici.|[Classe di evento Scan:Started](scan-started-event-class.md)<br /><br /> [Classe di evento Scan:Stopped](scan-stopped-event-class.md)|  
|Nella [categoria di eventi Security Audit](security-audit-event-category-sql-server-profiler.md) sono incluse classi di evento usate per il controllo dell'attività del server.|[Classe di evento Audit Add DB User](audit-add-db-user-event-class.md)<br /><br /> [Classe di evento Audit Add Login to Server Role](audit-add-login-to-server-role-event-class.md)<br /><br /> [Classe di evento Audit Add Member to DB Role](audit-add-member-to-db-role-event-class.md)<br /><br /> [Classe di evento Audit Add Role](audit-add-role-event-class.md)<br /><br /> [Classe di evento Audit Addlogin](audit-addlogin-event-class.md)<br /><br /> [Classe di evento Audit App Role Change Password](audit-app-role-change-password-event-class.md)<br /><br /> [Classe di evento Audit Backup/Restore](audit-backup-and-restore-event-class.md)<br /><br /> [Classe di evento Audit Broker Conversation](audit-broker-conversation-event-class.md)<br /><br /> [Classe di evento Audit Broker Login](audit-broker-login-event-class.md)<br /><br /> [Classe di evento Audit Change Audit](audit-change-audit-event-class.md)<br /><br /> [Classe di evento Audit Change Database Owner](audit-change-database-owner-event-class.md)<br /><br /> [Classe di evento Audit Database Management](audit-database-management-event-class.md)<br /><br /> [Classe di evento Audit Database Object Access](audit-database-object-access-event-class.md)<br /><br /> [Classe di evento Audit Database Object GDR](audit-database-object-gdr-event-class.md)<br /><br /> [Classe di evento Audit Database Object Management](audit-database-object-management-event-class.md)<br /><br /> [Classe di evento Audit Database Object Take Ownership](audit-database-object-take-ownership-event-class.md)<br /><br /> [Classe di evento Audit Database Operation](audit-database-operation-event-class.md)<br /><br /> [Classe di evento Audit Database Principal Impersonation](audit-database-principal-impersonation-event-class.md)<br /><br /> [Classe di evento Audit Database Principal Management](audit-database-principal-management-event-class.md)<br /><br /> [Classe di evento Audit Database Scope GDR](audit-database-scope-gdr-event-class.md)<br /><br /> [Classe di evento Audit DBCC](audit-dbcc-event-class.md)<br /><br /> [Classe di evento Audit Login Change Password](audit-login-change-password-event-class.md)<br /><br /> [Classe di evento Audit Login Change Property](audit-login-change-property-event-class.md)<br /><br /> [Classe di evento Audit Login](audit-login-event-class.md)<br /><br /> [Classe di evento Audit Login Failed](audit-login-failed-event-class.md)<br /><br /> [Classe di evento Audit Login GDR](audit-login-gdr-event-class.md)<br /><br /> [Classe di evento Audit Logout](audit-logout-event-class.md)<br /><br /> [Classe di evento Audit Object Derived Permission](audit-object-derived-permission-event-class.md)<br /><br /> [Classe di evento Audit Schema Object Access](audit-schema-object-access-event-class.md)<br /><br /> [Classe di evento Audit Schema Object GDR](audit-schema-object-gdr-event-class.md)<br /><br /> [Classe di evento Audit Schema Object Management](audit-schema-object-management-event-class.md)<br /><br /> [Classe di evento Audit Schema Object Take Ownership](audit-schema-object-take-ownership-event-class.md)<br /><br /> [Classe di evento Audit Server Alter Trace](audit-server-alter-trace-event-class.md)<br /><br /> [Classe di evento Audit Server Object GDR](audit-server-object-gdr-event-class.md)<br /><br /> [Classe di evento Audit Server Object Management](audit-server-object-management-event-class.md)<br /><br /> [Classe di evento Audit Server Object Take Ownership](audit-server-object-take-ownership-event-class.md)<br /><br /> [Classe di evento Audit Server Operation](audit-server-operation-event-class.md)<br /><br /> [Classe di evento Audit Server Principal Impersonation](audit-server-principal-impersonation-event-class.md)<br /><br /> [Classe di evento Audit Server Principal Management](audit-server-principal-management-event-class.md)<br /><br /> [Classe di evento Audit Server Scope GDR](audit-server-scope-gdr-event-class.md)<br /><br /> [Classe di evento Audit Server Starts and Stops](audit-server-starts-and-stops-event-class.md)<br /><br /> [Classe di evento Audit Statement Permission](audit-statement-permission-event-class.md)|  
|La [categoria di eventi Server](server-event-category.md) contiene eventi generali relativi al server.|[Classe di evento Mount Tape](mount-tape-event-class.md)<br /><br /> [Classe di evento Server Memory Change](server-memory-change-event-class.md)<br /><br /> [Classe di evento Trace File Close](trace-file-close-event-class.md)|  
|Nella [categoria di eventi Sessioni](sessions-event-category.md) sono incluse classi di evento generate in seguito alla connessione e disconnessione dei client da un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|[Classe di evento ExistingConnection](existingconnection-event-class.md)|  
|Nella [categoria di eventi Stored procedure](stored-procedures-event-category.md) sono incluse classi di evento generate in seguito all'esecuzione di stored procedure.|[Classe di evento PreConnect:Completed](preconnect-completed-event-class.md)<br /><br /> [Classe di evento PreConnect:Starting](preconnect-starting-event-class.md)<br /><br /> [Classe di evento RPC:Completed](rpc-completed-event-class.md)<br /><br /> [Classe di evento RPC Output Parameter](rpc-output-parameter-event-class.md)<br /><br /> [Classe di evento RPC:Starting](rpc-starting-event-class.md)<br /><br /> [Classe di evento SP:CacheHit](sp-cachehit-event-class.md)<br /><br /> [Classe di evento SP:CacheInsert](sp-cacheinsert-event-class.md)<br /><br /> [Classe di evento SP:CacheMiss](sp-cachemiss-event-class.md)<br /><br /> [Classe di evento SP:CacheRemove](sp-cacheremove-event-class.md)<br /><br /> [Classe di evento SP:Completed](sp-completed-event-class.md)<br /><br /> [Classe di evento SP:Recompile](sp-recompile-event-class.md)<br /><br /> [Classe di evento SP:Starting](sp-starting-event-class.md)<br /><br /> [Classe di evento SP:StmtCompleted](sp-stmtcompleted-event-class.md)<br /><br /> [Classe di evento SP:StmtStarting](sp-stmtstarting-event-class.md)|  
|Nella [categoria di eventi Transactions](transactions-event-category.md) sono incluse classi di evento generate in seguito all'esecuzione di transazioni di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator o in seguito alla scrittura nel log delle transazioni.|[Classe di evento DTCTransaction](dtctransaction-event-class.md)<br /><br /> [Classe di evento SQLTransaction](sqltransaction-event-class.md)<br /><br /> [Classe di evento TM: Begin Tran Completed](tm-begin-tran-completed-event-class.md)<br /><br /> [Classe di evento TM: Begin Tran Starting](tm-begin-tran-starting-event-class.md)<br /><br /> [Classe di evento TM: Commit Tran Completed](tm-commit-tran-completed-event-class.md)<br /><br /> [Classe di evento TM: Commit Tran Starting](tm-commit-tran-starting-event-class.md)<br /><br /> [Classe di evento TM: Promote Tran Completed](tm-promote-tran-completed-event-class.md)<br /><br /> [Classe di evento TM: Promote Tran Starting](tm-promote-tran-starting-event-class.md)<br /><br /> [Classe di evento TM: Rollback Tran Completed](tm-rollback-tran-completed-event-class.md)<br /><br /> [Classe di evento TM: Rollback Tran Starting](tm-rollback-tran-starting-event-class.md)<br /><br /> [Classe di evento TM: Save Tran Completed](tm-save-tran-completed-event-class.md)<br /><br /> [Classe di evento TM: Save Tran Starting](tm-save-tran-starting-event-class.md)<br /><br /> [Classe di evento TransactionLog](transactionlog-event-class.md)|  
|Nella [categoria di eventi TSQL](tsql-event-category.md) sono incluse classi di evento generate dall'esecuzione di istruzioni Transact-SQL passate a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dal client.|[Classe di evento Exec Prepared SQL](exec-prepared-sql-event-class.md)<br /><br /> [Classe di evento Prepare SQL](prepare-sql-event-class.md)<br /><br /> [Classe di evento SQL:BatchCompleted](sql-batchcompleted-event-class.md)<br /><br /> [Classe di evento SQL:BatchStarting](sql-batchstarting-event-class.md)<br /><br /> [Classe di evento SQL:StmtCompleted](sql-stmtcompleted-event-class.md)<br /><br /> [Classe di evento SQL:StmtRecompile](sql-stmtrecompile-event-class.md)<br /><br /> [Classe di evento SQL:StmtStarting](sql-stmtstarting-event-class.md)<br /><br /> [Classe di evento Unprepare SQL](unprepare-sql-event-class.md)<br /><br /> [Classe di evento XQuery Static Type](xquery-static-type-event-class.md)|  
|Nella [categoria di eventi Configurabile dall'utente](user-configurable-event-category.md) sono incluse le classi di evento definite dall'utente.|[Classe di evento User-Configurable](user-configurable-event-class.md)|  
  
## <a name="see-also"></a>Vedere anche  
 [SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  