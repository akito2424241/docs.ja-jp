---
title: "ICorProfilerCallback7::ModuleInMemorySymbolsUpdated メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfiler7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type: COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 088749195165039639f58f4eb6444fb640ab4cec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="0ca20-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated メソッド</span><span class="sxs-lookup"><span data-stu-id="0ca20-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="0ca20-103">[.NET Framework 4.6.1 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="0ca20-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="0ca20-104">メモリ内のモジュールに関連付けられているシンボルのストリームが更新されるたびに、プロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="0ca20-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ca20-105">構文</span><span class="sxs-lookup"><span data-stu-id="0ca20-105">Syntax</span></span>  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ca20-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0ca20-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="0ca20-107">メモリ内のモジュールのシンボルのストリームの更新の識別子。</span><span class="sxs-lookup"><span data-stu-id="0ca20-107">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ca20-108">コメント</span><span class="sxs-lookup"><span data-stu-id="0ca20-108">Remarks</span></span>  
 <span data-ttu-id="0ca20-109">このコールバックは、設定によって制御されます、 [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)イベント マスク フラグを呼び出すときに、 [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)メソッドです。</span><span class="sxs-lookup"><span data-stu-id="0ca20-109">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ca20-110">このイベントは、現在のシンボルに暗黙的に作成または使用して変更は発生しません<xref:System.Reflection.Emit>Api です。</span><span class="sxs-lookup"><span data-stu-id="0ca20-110">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="0ca20-111">でもシンボルが指定されたときに前もってマネージのオーバー ロードのいずれかへの呼び出しで<xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType>メソッドを含む、 `rawSymbolStore` runtime、アセンブリのシンボルを指定する引数可能性があります実際には関連付けられませんシンボリック データ モジュールまで後、 [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)コールバックが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0ca20-111">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="0ca20-112">このイベントは、このようなモジュールのシンボルを収集する以降の機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="0ca20-112">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ca20-113">要件</span><span class="sxs-lookup"><span data-stu-id="0ca20-113">Requirements</span></span>  
 <span data-ttu-id="0ca20-114">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="0ca20-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ca20-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0ca20-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0ca20-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ca20-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ca20-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ca20-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ca20-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ca20-118">See Also</span></span>  
 [<span data-ttu-id="0ca20-119">ModuleLoadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="0ca20-119">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [<span data-ttu-id="0ca20-120">SetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="0ca20-120">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)  
 [<span data-ttu-id="0ca20-121">ICorProfilerCallback7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ca20-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)