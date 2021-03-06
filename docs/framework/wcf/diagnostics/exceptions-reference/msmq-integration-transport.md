---
title: "MSMQ 統合のトランスポート"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2bf9893a-fbd1-41fc-b6de-a41a44279936
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 18dd1262c572a7e8844d9fe2beb5de7f52c28e1e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="msmq-integration-transport"></a>MSMQ 統合のトランスポート
ここでは、MSMQ 統合トランスポートによって生成されるすべての例外を示します。  
  
## <a name="exception-list"></a>例外の一覧  
  
|リソース コード|リソースの文字列|  
|-------------------|---------------------|  
|MessageSizeMustBeInIntegerRange|このファクトリはメッセージをバッファーするため、メッセージ サイズは整数値の範囲内である必要があります。|  
|MsmqByteArrayBodyExpected|指定されたシリアル化形式と MSMQ メッセージの間で不整合が検出されました。 メッセージを送受信できません。 シリアル化形式 ByteArray では、MSMQ メッセージの本文が byte[] の種類でなければなりません。|  
|MsmqCannotDeserializeActiveXMessage|ActiveX のシリアル化中に、エラーが発生しました。 メッセージを送受信できません。 本文に指定されたバリアント型は、実際の MSMQ メッセージ本文と一致しません。|  
|MsmqCannotUseBodyTypeWithActiveXSerialization|メッセージのプロパティが整合していません。 メッセージを送受信できません。 シリアル化の形式として ActiveX が使用されている場合は、BodyType メッセージ プロパティを指定できません。|  
|MsmqInvalidServiceOperationForMsmqIntegrationBinding|MsmqIntegrationBinding の検証が失敗しました。 サービス エンドポイントを開始できません。 指定したバインディングは、指定したコントラクトの指定したサービス操作に対してメソッド署名をサポートしていません。 MsmqIntegrationBinding を使用するよう、サービス操作を修正してください。|  
|MsmqInvalidTypeDeserialization|シリアル化の形式を認識できないため、ActiveX のシリアル化が失敗しました。 メッセージを送受信できません。|  
|MsmqInvalidTypeSerialization|バリアント型を認識できません。 ActiveX のシリアル化が失敗しました。 メッセージを送受信できません。 指定されたバリアント型はサポートされていません。|  
|MsmqStreamBodyExpected|シリアル化形式と本文のコンテンツの間で不整合があります。 メッセージを送受信できません。 ストリーム シリアル化モードを使用して送受信できるのは、ストリーム型の本文に限られます。|
