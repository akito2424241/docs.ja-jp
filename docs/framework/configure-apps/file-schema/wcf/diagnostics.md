---
title: "&lt;診断&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c7997b3ffc1a1c3a16372398f43e8f0d06aadee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="ltdiagnosticsgt"></a>&lt;診断&gt;
`diagnostics` 要素は、ランタイムの検査と管理を行う管理者が使用できる設定を定義します。  
  
 \<システムです。ServiceModel >  
\<診断 >  
  
## <a name="syntax"></a>構文  
  
```xml  
<system.serviceModel>  
   <diagnostics etwProviderId="String"       performanceCounters="Off/ServiceOnly/All/Default"              wmiProviderEnabled="Boolean" >       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
       <messageLogging logEntireMessage="Boolean"  
          logMalformedMessages="Boolean"  
          logMessagesAtServiceLevel="Boolean"  
          logMessagesAtTransportLevel="Boolean"  
          maxMessagesToLog="Integer"  
          maxSizeOfMessageToLog="Integer" >  
          <filters>  
             <clear />  
          </filters>  
       </messageLogging>  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|etwProviderId|イベントを ETW セッションに書き込むイベント追跡プロバイダーの識別子を指定する文字列。|  
|performanceCounters|アセンブリのパフォーマンス カウンターが有効であるかどうかを指定します。 有効な値は、次のとおりです。<br /><br /> -Off: パフォーマンス カウンターが無効になります。<br />-ServiceOnly: このサービスに関連するパフォーマンス カウンターのみが有効にします。<br />-すべて: のパフォーマンス カウンターは、実行時に表示できます。<br />-既定値: 1 つのパフォーマンス カウンター インスタンス _WCF_Admin が作成されます。 このインスタンスは、インフラストラクチャで使用される SQM データのコレクションを有効にするために使用されます。 このインスタンスのカウンター値は更新されず、0 のままになります。 WCF の構成が存在しない場合は、これが既定値になります。|  
|wmiProviderEnabled|アセンブリの WMI プロバイダーが有効であるかどうかを指定するブール値。 ユーザーが Windows Communication Foundation (WCF) の検査および制御機能に対する実行時アクセス権を取得するには、WMI プロバイダーが必要です。 既定値は、`false` です。|  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<endToEndTracing >](../../../../../docs/framework/configure-apps/file-schema/wcf/endtoendtracing.md)|サービス アプリケーションの実行中にエンドツーエンドのトレースのさまざまな側面を有効または無効にするための構成要素。|  
|[\<メッセージ ログ >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)|WCF メッセージ ログの設定について説明します。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|serviceModel|すべての WCF 構成要素のルート要素です。|  
  
## <a name="remarks"></a>コメント  
 `diagnostics` セクションは、アセンブリに配置されるすべてのサービスの診断設定を定義します。 アセンブリ内のサービスが 1 つでない限り、サービス レベル別に診断設定を定義することはできません。 属性は、セクションの要件に応じて設定されます。  
  
## <a name="example"></a>例  
  
```xml  
<diagnostics wmiProviderEnabled="false"  
       performanceCounters="all">  
       <messageLogging logEntireMessage="true"  
          logMalformedMessages="true"  
          logMessagesAtServiceLevel="true"  
          logMessagesAtTransportLevel="true"  
          maxMessagesToLog="42"  
          maxSizeOfMessageToLog="42">  
         <filters>  
         <clear />  
    </filters>  
       </messageLogging>  
</diagnostics>  
```  
  
## <a name="see-also"></a>参照  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>
