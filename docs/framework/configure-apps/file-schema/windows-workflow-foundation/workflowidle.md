---
title: '&lt;workflowIdle&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 65bcc1ccd357fb7f331665aefbd975b11a2378cd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756905"
---
# <a name="ltworkflowidlegt"></a>&lt;workflowIdle&gt;
アイドル状態のワークフロー インスタンスのアンロードおよび永続化のタイミングを制御するサービス動作。  
  
\<system.ServiceModel >  
\<ビヘイビアー >  
\<serviceBehaviors>  
\<behavior>  
\<workflowIdle >  
  
## <a name="syntax"></a>構文  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan" 
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|timeToPersist|ワークフローがアイドル状態になりが永続化されるまでの間の期間を指定する Timespan 値です。 既定値は、TimeSpan.MaxValue です。<br /><br /> 継続時間は、ワークフロー インスタンスがアイドル状態になった時点から開始します。 この属性はできるだけ長く用のメモリ内インスタンスも保持しながら、ワークフロー インスタンスをより積極的に永続化する場合に便利です。 この属性は有効なは、その値がある場合のみより小さい**timeToUnload**属性。 それより大きい場合は無視されます。 この属性が値を指定する前に経過すると、 **timeToUnload**属性に、ワークフローが読み込まれる前に、永続化を完了する必要があります。 これは、ワークフローを永続化するまでアンロード操作に遅延が生じる場合があることを意味します。 永続化レイヤーは一時的なエラーの再試行処理は行いますが、回復不可能なエラーに対しては例外をスローするだけです。 したがって、永続化中にスローされる例外は致命的な例外として処理され、ワークフロー インスタンスが中止されます。|  
|timeToUnload|ワークフローがアイドル状態からアンロードされるまでの継続時間を指定する Timespan 値。 既定値は 1 分です。<br /><br /> ワークフローをアンロードすることは、同時に、永続化することも意味します。 この属性は、ワークフロー インスタンスが永続化し、アンロードした直後にゼロに設定されている場合、ワークフローはアイドル状態になります。 この属性を TimeSpan.MaxValue を効果的に設定すると、アンロード操作が無効にします。 アイドル状態になったワークフロー インスタンスはアンロードされません。|  
  
### <a name="child-elements"></a>子要素  
 なし。  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<動作 > の\<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|動作の要素を指定します。|  
  
## <a name="see-also"></a>関連項目  
 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
