---
title: "IHostTaskManager::ReverseEnterRuntime メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.ReverseEnterRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1c8d84cbd02527a026206d6fa172a9d3f40683fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="a07b1-102">IHostTaskManager::ReverseEnterRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="a07b1-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="a07b1-103">呼び出しがアンマネージ コードから共通言語ランタイム (CLR) に作成されていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="a07b1-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a07b1-104">構文</span><span class="sxs-lookup"><span data-stu-id="a07b1-104">Syntax</span></span>  
  
```  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a07b1-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="a07b1-105">Return Value</span></span>  
  
|<span data-ttu-id="a07b1-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a07b1-106">HRESULT</span></span>|<span data-ttu-id="a07b1-107">説明</span><span class="sxs-lookup"><span data-stu-id="a07b1-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a07b1-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="a07b1-108">S_OK</span></span>|<span data-ttu-id="a07b1-109">`ReverseEnterRuntime`正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="a07b1-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="a07b1-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a07b1-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a07b1-111">CLR が、プロセスに読み込まれていませんまたは CLR は、状態をマネージ コードを実行またはできないの呼び出しは正常に処理します。</span><span class="sxs-lookup"><span data-stu-id="a07b1-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a07b1-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a07b1-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a07b1-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="a07b1-113">The call timed out.</span></span>|  
|<span data-ttu-id="a07b1-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a07b1-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a07b1-115">呼び出し元は、ロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="a07b1-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a07b1-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a07b1-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a07b1-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="a07b1-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a07b1-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a07b1-118">E_FAIL</span></span>|<span data-ttu-id="a07b1-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a07b1-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a07b1-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a07b1-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a07b1-121">メソッドのホストに以降の呼び出しでは、HOST_E_CLRNOTAVAILABLE を返します。</span><span class="sxs-lookup"><span data-stu-id="a07b1-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a07b1-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a07b1-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a07b1-123">十分なメモリが要求されたリソースの割り当てを完了します。</span><span class="sxs-lookup"><span data-stu-id="a07b1-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a07b1-124">コメント</span><span class="sxs-lookup"><span data-stu-id="a07b1-124">Remarks</span></span>  
 <span data-ttu-id="a07b1-125">各呼び出しを開始したシーケンスからマネージ コードで CLR への呼び出しが行われた場合`ReverseEnterRuntime`への呼び出しに対応して[ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)です。</span><span class="sxs-lookup"><span data-stu-id="a07b1-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a07b1-126">呼び出しは、入れ子にせず、アンマネージ コードから取得できます。</span><span class="sxs-lookup"><span data-stu-id="a07b1-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="a07b1-127">この場合への呼び出しはありません[EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)、 [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)、または`ReverseLeaveRuntime`への呼び出しの数と`ReverseEnterRuntime`への呼び出しの数と等しくない`ReverseLeaveRuntime`です。</span><span class="sxs-lookup"><span data-stu-id="a07b1-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a07b1-128">要件</span><span class="sxs-lookup"><span data-stu-id="a07b1-128">Requirements</span></span>  
 <span data-ttu-id="a07b1-129">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="a07b1-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a07b1-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a07b1-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a07b1-131">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="a07b1-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a07b1-132">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a07b1-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a07b1-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="a07b1-133">See Also</span></span>  
 [<span data-ttu-id="a07b1-134">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a07b1-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="a07b1-135">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a07b1-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="a07b1-136">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a07b1-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="a07b1-137">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a07b1-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)