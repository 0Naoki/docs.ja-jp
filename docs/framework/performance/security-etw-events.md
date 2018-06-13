---
title: セキュリティ ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e02274b63ddf7df42d26621791de0286df9655b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395513"
---
# <a name="security-etw-events"></a>セキュリティ ETW イベント
<a name="top"></a> セキュリティ イベントは、厳密な名前の検証時と Authenticode の検証時に発生します。  
  
 このカテゴリは、次のイベントで構成されます。  
  
-   [StrongNameVerificationStart_V1 イベントと StrongNameVerificationStop_V1 イベント](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [AuthenticodeVerificationStart_V1 イベントと AuthenticodeVerificationStop_V1 イベント](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a>StrongNameVerificationStart_V1 イベントと StrongNameVerificationStop_V1 イベント  
 次の表に、キーワードとレベルを示します。 (詳細については、「 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)」を参照してください)。  
  
|イベントを発生させるキーワード|レベル|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0x400)|情報通知 (4)|  
  
 次の表に、イベント情報を示します。  
  
|イベント|イベント ID|いつ発生するか|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|181|厳密な名前の検証の開始。|  
|`StrongNameVerificationStop_V1`|182|厳密な名前の検証の終了。|  
  
 次の表に、イベント データを示します。  
  
|フィールド名|データ型|説明|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|検証フラグ。|  
|ErrorCode|win:UInt32|HResult エラー コード。|  
|FullyQualifiedAssemblyName|win:UnicodeString|完全修飾アセンブリ名。|  
|ClrInstanceID|win:UInt16|CLR または CoreCLR のインスタンスの一意の ID。|  
  
 [ページのトップへ](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a>AuthenticodeVerificationStart_V1 イベントと AuthenticodeVerificationStop_V1 イベント  
 次の表に、キーワードとレベルを示します。  
  
|イベントを発生させるキーワード|レベル|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0x400)|情報通知 (4)|  
  
 次の表に、イベント情報を示します。  
  
|イベント|イベント ID|いつ発生するか|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|183|Authenticode 検証の開始。|  
|`AuthenticodeVerificationStop_V1`|184|Authenticode 検証の終了。|  
  
 次の表に、イベント データを示します。  
  
|フィールド名|データ型|説明|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|検証フラグ。|  
|ErrorCode|win:UInt32|HResult エラー コード。|  
|ModulePath|win:UnicodeString|モジュール パス|  
|ClrInstanceID|win:UInt16|CLR または CoreCLR のインスタンスの一意の ID。|  
  
## <a name="see-also"></a>関連項目  
 [CLR ETW イベント](../../../docs/framework/performance/clr-etw-events.md)
