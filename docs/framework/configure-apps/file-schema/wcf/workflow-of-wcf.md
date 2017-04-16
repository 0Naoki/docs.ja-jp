---
title: "WCF の &lt;workflow&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c0443eba-d3b4-4fae-886e-9878daf77691
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# WCF の &lt;workflow&gt;
ランタイムから直接出力される追跡レコードをリッスンし、追跡レコードの構成方法に従って処理を行う追跡参加要素を構成します。  これには、特定の出力 \(ファイル、コンソール、ETW など\) への書き込み、レコードの処理や集計、またはその他の必要な組み合わせが含まれます。  
  
 ワークフロー追跡と追跡参加要素の詳細については、「[ワークフロー追跡とトレース](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)」および「[追跡参加要素](../../../../../docs/framework/windows-workflow-foundation//tracking-participants.md)」を参照してください。  
  
## 構文  
  
```vb  
  
<tracking>   
   <participants>   
      <add name="String"   
           profileName="String"  
           type="String" />   
   </participants>   
</tracking>  
  
```  
  
## 属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### 属性  
  
|要素|説明|  
|--------|--------|  
|name|追跡参加要素の名前を指定する文字列。|  
|profileName|追跡参加要素が定期受信した追跡レコードを定義する、追跡プロファイルの名前を指定する文字列。|  
|型|追跡参加要素の型を指定する文字列。|  
  
### 子要素  
 なし。  
  
### 親要素  
  
|要素|説明|  
|--------|--------|  
|[\<participants\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|追跡参加要素の一覧|  
  
## 解説  
 追跡参加要素は、ワークフローから生成される追跡データを取得し、それを別のメディアに保存するために使用します。  同様に、追跡レコードの後処理はすべて、追跡参加要素内でも実行できます。  
  
 複数の追跡参加要素が追跡イベントを同時に使用することができます。  各追跡参加要素は、それぞれ別の追跡プロファイルと関連付けることができます。  
  
 追跡レコードを ETW セッションに書き込む、標準の追跡参加要素が用意されています。  参加要素は、追跡固有の動作を構成ファイルに追加することによって、ワークフロー サービスで構成されます。  ETW 追跡参加要素を有効にすると、追跡レコードをイベント ビューアーで表示できます。  これで要件が満たされない場合は、カスタムの追跡参加要素を作成することもできます。  
  
## 使用例  
 次の構成例は、Web.config ファイルで構成されている標準の ETW 追跡参加要素を示します。  
  
 ETW 追跡参加要素が追跡レコードを ETW に書き込むために使用するプロバイダー ID は、`<diagnostics>` セクションで定義されます。  追跡参加要素には、その要素が定期受信した追跡レコードを指定するためのプロファイルが関連付けられています。  これは、`<add>` 要素の `profileName` 属性で定義されます。  これらが定義されると、追跡参加要素は `<etwTracking>` サービス動作に追加されます。  これにより、選択した追跡参加要素がワークフロー インスタンスの拡張機能に追加され、追跡レコードの受信が開始されます。  
  
```  
  
<configuration>   
  <system.web>   
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>   
  </system.web>   
  <system.serviceModel>   
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />                
    <tracking>   
      <participants>   
        <add name="EtwTrackingParticipant"   
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"   
             profileName="HealthMonitoring_Tracking_Profile"/>   
      </participants>   
    </tracking>   
    <behaviors>   
      <serviceBehaviors>   
        <behavior>   
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>   
      </serviceBehaviors>   
    </behaviors>   
  </system.serviceModel>   
</configuration>  
```  
  
## 参照  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>   
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>   
 <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehavior>   
 [ワークフロー追跡とトレース](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [追跡参加要素](../../../../../docs/framework/windows-workflow-foundation//tracking-participants.md)