---
title: "ICorProfilerCallback::RuntimeSuspendStarted メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeSuspendStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 358536aa51dfef2d079813b34eddbd1b01294bcc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="559c4-102">ICorProfilerCallback::RuntimeSuspendStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="559c4-102">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>
<span data-ttu-id="559c4-103">ランタイムをランタイムのすべてのスレッドを中断することをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="559c4-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="559c4-104">構文</span><span class="sxs-lookup"><span data-stu-id="559c4-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="559c4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="559c4-105">Parameters</span></span>  
 `suspendReason`  
 <span data-ttu-id="559c4-106">[in]値、 [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md)を中断の理由を示す列挙体です。</span><span class="sxs-lookup"><span data-stu-id="559c4-106">[in] A value of the [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="559c4-107">コメント</span><span class="sxs-lookup"><span data-stu-id="559c4-107">Remarks</span></span>  
 <span data-ttu-id="559c4-108">アンマネージ コード内にあるすべてのランタイムのスレッドは、ランタイムを再入力するまで実行を続行が許可されます。</span><span class="sxs-lookup"><span data-stu-id="559c4-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="559c4-109">その時点で、中断されます、ランタイムが再開されるまでです。</span><span class="sxs-lookup"><span data-stu-id="559c4-109">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="559c4-110">これは、新しいスレッドがランタイムに入ることにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="559c4-110">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="559c4-111">ランタイムのすべてのスレッドは、いずれかの即座に中断され、割り込み可能なコードではすでにまたは割り込み可能なコードに到達したときに中断するように求められます。</span><span class="sxs-lookup"><span data-stu-id="559c4-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="559c4-112">要件</span><span class="sxs-lookup"><span data-stu-id="559c4-112">Requirements</span></span>  
 <span data-ttu-id="559c4-113">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="559c4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="559c4-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="559c4-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="559c4-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="559c4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="559c4-116">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="559c4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="559c4-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="559c4-117">See Also</span></span>  
 [<span data-ttu-id="559c4-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="559c4-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="559c4-119">RuntimeSuspendAborted メソッド</span><span class="sxs-lookup"><span data-stu-id="559c4-119">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)  
 [<span data-ttu-id="559c4-120">RuntimeSuspendFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="559c4-120">RuntimeSuspendFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)