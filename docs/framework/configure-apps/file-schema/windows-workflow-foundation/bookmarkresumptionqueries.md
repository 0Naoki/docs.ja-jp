---
title: '&lt;bookmarkResumptionQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: ae6a81123379ecd0e7fdc72f4e115a462f81eb90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555038"
---
# <a name="ltbookmarkresumptionqueriesgt"></a>&lt;bookmarkResumptionQueries&gt;
ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。 追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。  
  
 追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel>  
\<追跡 >  
\<trackingProfile>  
\<ワークフロー >  
\<bookmarkResumptionQueries>  
\<bookmarkResumptionQuery>  
  
## <a name="syntax"></a>構文  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
 なし。  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|ワークフロー インスタンス内のブックマークの再開を追跡するために使用されるクエリ。 追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<workflow>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|識別される特定のワークフローのすべてのクエリを格納する構成要素、 **activityDefinitionId**プロパティ。|  
  
## <a name="see-also"></a>関連項目
- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [ワークフローの追跡とトレース](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
