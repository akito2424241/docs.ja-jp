---
title: "追跡レコード"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51adbda3-bd8b-4892-a8ea-d343186472d2
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c871f019179c091fc022be0bf03ad84fbe66dc1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="tracking-records"></a>追跡レコード
ワークフロー ランタイムは、ワークフロー インスタンスの実行状況を追跡する追跡レコードを出力するためにインストルメント化されています。  
  
## <a name="tracking-records"></a>追跡レコード  
 次の表で、ワークフロー ランタイムが出力する追跡レコードの詳細を説明します。  
  
|追跡レコード|説明|  
|---------------------|-----------------|  
|ワークフロー ライフ サイクル レコード|ワークフロー インスタンスのライフ サイクルの多様なステージ中に出力されます。 たとえば、ワークフローの開始時または完了時にレコードは出力されます。|  
|アクティビティ ライフ サイクル レコード|アクティビティの実行状況を詳しく記録します。 これらのレコードは、アクティビティをスケジュールしたとき、アクティビティが完了したとき、エラーが発生したときなど、ワークフロー アクティビティの状態を示します。|  
|ブックマーク再開レコード|ワークフロー インスタンス内のブックマークが再開されたときに出力されます。|  
|カスタム追跡レコード|ワークフロー作成者はカスタム追跡レコードを作成し、カスタム アクティビティ内で出力できます。|  
  
 WF ランタイムから出力されるすべての追跡関連レコードは、基本クラス <xref:System.Activities.Tracking.TrackingRecord> から派生します。この基本クラスには一般的なデータのセットが含まれます。 追跡レコードは、単純なワークフローのライフ サイクルを示します。 各追跡レコードには、<xref:System.Activities.Tracking.TrackingRecord.InstanceId%2A>、<xref:System.Activities.Tracking.TrackingRecord.RecordNumber%2A> などの関連する追跡イベント、および追跡レコードの型に固有の追加情報の詳細が含まれます。  
  
 次の <xref:System.Activities.Tracking.TrackingRecord> オブジェクトの型は、ワークフロー ランタイムによって出力されます。  
  
-   **WorkflowInstanceRecord** - この<xref:System.Activities.Tracking.TrackingRecord>ワークフロー インスタンスのライフ サイクルについて説明します。 たとえば、ワークフローの開始時または完了時にレコードが出力されます。また、レコードにはワークフロー インスタンスの状態が含まれます。 このレコードの詳細については、「<xref:System.Activities.Tracking.WorkflowInstanceRecord>」を参照してください。  
  
-   **WorkflowInstanceAbortedRecord** - この<xref:System.Activities.Tracking.TrackingRecord>はワークフロー インスタンスが中止されると生成されます。 レコードにはワークフロー インスタンスが中止された理由が含まれます。 このレコードの詳細については、「<xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>」を参照してください。  
  
-   **WorkflowInstanceUnhandledExceptionRecord** - この<xref:System.Activities.Tracking.TrackingRecord>は、例外がワークフロー インスタンスで発生し、任意のアクティビティによって処理されない場合に生成されます。 レコードには例外の詳細が含まれます。 このレコードの詳細については、「<xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>」を参照してください。  
  
-   **WorkflowInstanceSuspendedRecord** - この<xref:System.Activities.Tracking.TrackingRecord>はワークフロー インスタンスが中断されるたびに生成されます。 レコードにはワークフロー インスタンスが一時停止された理由が含まれます。 このレコードの詳細については、「<xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>」を参照してください。  
  
-   **WorkflowInstanceTerminatedRecord** - この<xref:System.Activities.Tracking.TrackingRecord>はワークフロー インスタンスが終了するたびに生成されます。 レコードにはワークフロー インスタンスが終了した理由が含まれます。 このレコードの詳細については、「<xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>」を参照してください。  
  
-   **ActivityStateRecord** - この<xref:System.Activities.Tracking.TrackingRecord>は、ワークフロー内のアクティビティを実行するときに生成されます。 これらのレコードは、ワークフロー インスタンス内のアクティビティの状態を示します。 このレコードの詳細については、「<xref:System.Activities.Tracking.ActivityStateRecord>」を参照してください。  
  
-   **ActivityScheduledRecord** - この<xref:System.Activities.Tracking.TrackingRecord>はアクティビティが子アクティビティをスケジュールするときに生成されます。 このレコードには、親のアクティビティ (スケジューリング アクティビティ) およびスケジュール設定された子アクティビティの両方の詳細が含まれます。 このレコードの詳細については、「<xref:System.Activities.Tracking.ActivityScheduledRecord>」を参照してください。  
  
-   **FaultPropagationRecord** - この<xref:System.Activities.Tracking.TrackingRecord>処理されるまでレコードを調べて各ハンドラーが生成されます。 これは、エラーがワークフロー インスタンス内でたどるパスを示すために使用されます。 このレコードの詳細については、「<xref:System.Activities.Tracking.FaultPropagationRecord>」を参照してください。  
  
-   **CancelRequestedRecord** - この<xref:System.Activities.Tracking.TrackingRecord>はアクティビティが子アクティビティをキャンセルしようとするときに生成されます。 このレコードには、親アクティビティおよび取り消される子アクティビティの両方の詳細が含まれます。 このレコードの詳細については、「<xref:System.Activities.Tracking.CancelRequestedRecord>」を参照してください。  
  
-   **BookmarkResumptionRecord** - この<xref:System.Activities.Tracking.TrackingRecord>が正常に再開されるブックマークを追跡します。 このレコードの詳細については、「<xref:System.Activities.Tracking.BookmarkResumptionRecord>」を参照してください。  
  
-   **CustomTrackingRecord** - この<xref:System.Activities.Tracking.TrackingRecord>が作成され、カスタム ワークフロー アクティビティ内のワークフロー作成者によって生成されます。 カスタム追跡レコードには、レコードと一緒に出力されるデータを読み込むことができます。 このレコードの詳細については、「<xref:System.Activities.Tracking.CustomTrackingRecord>」を参照してください。  
  
 単純な <xref:System.Activities.Statements.Sequence> アクティビティの例としては、追跡レコードを次の順序で出力する <xref:System.Activities.Statements.WriteLine> 操作を含めることが考えられます。  
  
1.  <xref:System.Activities.Tracking.WorkflowInstanceRecord> は、ワークフローが起動していることを示します。  
  
2.  <xref:System.Activities.Tracking.ActivityScheduledRecord> は、アクティビティがスケジュールされたことを示します。 この場合は <xref:System.Activities.Statements.Sequence> アクティビティです。  
  
3.  <xref:System.Activities.Tracking.ActivityScheduledRecord> は、<xref:System.Activities.Statements.WriteLine> アクティビティを表します。  
  
4.  2 つのアクティビティが完了していることを示す 2 つの <xref:System.Activities.Tracking.ActivityStateRecord> レコードがあります。  
  
5.  <xref:System.Activities.Tracking.WorkflowInstanceRecord> は、ワークフローが完了していることを示します。  
  
## <a name="see-also"></a>参照  
 [Windows Server App Fabric の監視](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [アプリケーション App Fabric の監視](http://go.microsoft.com/fwlink/?LinkId=201275)
