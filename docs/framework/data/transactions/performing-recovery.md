---
title: "回復の実行"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6dd17bf6-ba42-460a-a44b-8046f52b10d0
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a73e1b5c6cbb18e89b30550f02c0678e76d12ab4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="performing-recovery"></a>回復の実行
リソース マネージャーは、リソース障害の後にトランザクション参加要素を再参加させることにより、トランザクションの永続参加リストの解決を容易にします。  
  
## <a name="the-recovery-process"></a>回復プロセス  
 後で回復できるリソースを永続的に参加させるには (<xref:System.Transactions.IEnlistmentNotification> インターフェイスの実装により記述)、<xref:System.Transactions.Transaction.EnlistDurable%2A> メソッドを呼び出す必要があります。 さらに、リソース障害発生時にトランザクションの参加要素に一貫したラベル付けを行うためのリソース マネージャー識別子 (<xref:System.Transactions.Transaction.EnlistDurable%2A>) を <xref:System.Guid> メソッドに提供する必要があります。 このため、<xref:System.Guid>初期の参加には、呼び出しと同じにする必要があります提供される、 *resourceManagerIdentifier*内のパラメーター、<xref:System.Transactions.TransactionManager.Reenlist%2A>復旧中に呼び出します。 そうでない場合、<xref:System.Transactions.TransactionException> がスローされます。 永続参加リストの詳細については、次を参照してください。[リソースをトランザクションの参加者として参加](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md)です。  
  
 2PC プロトコルの準備フェーズ (フェーズ 1) で、永続的リソース マネージャーの実装が <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> 通知を受け取った場合、このフェーズ中にその準備レコードをログに記録する必要があります。 このレコードには、コミット時にトランザクションを完了するために必要なすべての情報を含める必要があります。 準備レコード後でできるように回復中に取得することによって、<xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A>のプロパティ、 *preparingEnlistment*コールバック。 <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> メソッド内でレコードのログ記録を実行する必要はありません。RM がワーカー スレッド上でこの処理を実行できるためです。  
  
 回復プロセスは、次の 2 つの手順から構成されます。  
  
### <a name="step-1---reenlist"></a>手順 1 - 再参加  
 リソース マネージャーは、不明な各参加の準備情報レコードについて調べます。 そのためには、フェーズ 1 の <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> 通知でリソース マネージャーに渡された <xref:System.Transactions.PreparingEnlistment> コールバックの <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> プロパティを調べます。  
  
 対象の各参加について、トランザクション マネージャーで <xref:System.Transactions.TransactionManager.Reenlist%2A> を呼び出します。 このメソッドは、リソース マネージャーを識別する一意の <xref:System.Guid> と、バイト配列の参加情報を渡します。 新しい <xref:System.Transactions.Enlistment> オブジェクトが返されます。 再参加が失敗して例外がスローされた場合、リソース マネージャーは後で再試行する必要があります。  
  
 失敗後にリソース マネージャーを再起動するときは、<xref:System.Transactions.TransactionManager.Reenlist%2A> メソッドのみを呼び出す必要があります。 また、2 フェーズ コミットの最初の準備フェーズ中に、リソース マネージャーによってログ記録された未解決トランザクションのみを再参加させる必要があります。 無効な時間にこのメソッドを呼び出した場合、間違った結果が生成される可能性があります。  
  
 参加要素がこのメソッドを使用して再参加すると、トランザクションの結果に対応した <xref:System.Transactions.IEnlistmentNotification> のフェーズ 2 のメソッド (つまり、<xref:System.Transactions.IEnlistmentNotification.Commit%2A>、<xref:System.Transactions.IEnlistmentNotification.Rollback%2A>、または <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A>) が必要に応じて呼び出されます。  
  
### <a name="step-2---completing-the-recovery"></a>手順 2 - 回復の完了  
 すべての再参加が完了すると、リソース マネージャーは <xref:System.Transactions.TransactionManager.RecoveryComplete%2A> メソッドを呼び出します。 このメソッドは回復を完了し、リソース マネージャーに不明なトランザクションがもう存在しないことをトランザクション マネージャーに通知します。 これによりリソース マネージャーは、再び <xref:System.Transactions.TransactionManager.Reenlist%2A> メソッドを呼び出さないことを保証します。  
  
 リソース マネージャーは、新しいトランザクションに参加する前に、不明なトランザクションをすべて解決する必要はありません。 最初のステップは、リソース マネージャーが、トランザクション マネージャーとのリレーションシップを確立した後でいつでも実行できる<xref:System.Transactions.TransactionManager.RecoveryComplete%2A>されました (手順 2.) を呼び出されます。 1 の手順をもう一度実行できません。 手順 2 は、トランザクションの結果に影響を与えることなく、複数回繰り返すことができます。
