---
title: 302 - UserDefinedWarningOccurred
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae455c9eec2335fcf6eb5473932bd8d9e5d2db95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="302---userdefinedwarningoccurred"></a>302 - UserDefinedWarningOccurred
## <a name="properties"></a>プロパティ  
  
|||  
|-|-|  
|ID|302|  
|キーワード|Troubleshooting、HealthMonitoring、UserEvents、ServiceModel、EndToEndMonitoring|  
|レベル|警告|  
|チャネル|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>説明  
 このイベントは、ユーザー コードから生成されます。 開発者は、カスタム定義の警告イベントがサービスで発生したときに、このイベントを生成できます。 これは、<xref:System.Diagnostics.Eventing> API を使用して実行できます。 また、その API をラップし、このイベントを適切に生成する方法を示す、WCF サンプルもあります。  
  
## <a name="message"></a>メッセージ  
 名前:'%1'、参照:'%2'、ペイロード:%3  
  
## <a name="details"></a>説明  
  
|データ項目名|データ項目の型|説明|  
|--------------------|--------------------|-----------------|  
|name|`xs:string`|イベントのユーザー定義名。|  
|HostReference|`xs:string`|Web ホスト サービスの場合は、このフィールドにより、サービスが Web 階層内で一意に識別されます。 その形式とは見なさ ' Web サイト名アプリケーション仮想パス &#124;です。サービス仮想パス &#124;です。ServiceName' です。 例: ' 既定の Web サイト/CalculatorApplication &#124;/CalculatorService.svc &#124;です。CalculatorService'。|  
|Payload|`xs:string`|イベントのユーザー定義ペイロード。|
