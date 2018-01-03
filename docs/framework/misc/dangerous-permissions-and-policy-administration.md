---
title: "危険なアクセス許可とポリシー管理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 471570aec43398b05b8678bdcf74a3ef2494e289
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="dangerous-permissions-and-policy-administration"></a>危険なアクセス許可とポリシー管理
.NET Framework がアクセス許可を提供する保護された操作のいくつかで、セキュリティ システムが回避されてしまう可能性があります。 これらの危険なアクセス許可は信頼できるコードにのみ付与し、その付与は必要な場合に限る必要があります。 これらのアクセス許可が付与されると、通常、悪意のあるコードに対する防御策はありません。  
  
> [!NOTE]
>  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]では、.NET Framework のセキュリティ モデルと用語に重要な変更が加えられています。 これらの変更の詳細については、次を参照してください。[セキュリティの変更点](../../../docs/framework/security/security-changes.md)です。  
  
 危険なアクセス許可については、次の表で説明します。  
  
|アクセス許可|潜在的なリスク|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|マネージ コードからアンマネージ コードを呼び出せるようにしますが、これは大抵リスクを伴います。|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|検証なしで、コードは何でも実行できます。|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|無効な証拠でセキュリティ ポリシーをかいくぐることができます。|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|セキュリティ ポリシーを変更する機能によって、セキュリティを無効にできます。|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|シリアル化を使用して、ユーザー補助機能のメカニズムを回避できます。 詳細については、「 [セキュリティとシリアル化](../../../docs/framework/misc/security-and-serialization.md)」を参照してください。|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|現行プリンシパルを設定する機能によって、ロール ベースのセキュリティを欺くことができます。|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|スレッドにはセキュリティ状態が関連付けられているため、スレッドの操作は危険です。|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|プライベート メンバーを使用して、ユーザー補助機能のメカニズムを無効にすることができます。|  
  
## <a name="see-also"></a>参照  
 [安全なコーディングのガイドライン](../../../docs/standard/security/secure-coding-guidelines.md)
