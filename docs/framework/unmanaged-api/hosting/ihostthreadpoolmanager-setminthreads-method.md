---
title: "IHostThreadPoolManager::SetMinThreads メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.SetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: 10409db9-9fd2-4e4d-b8cd-cf6fec0afaa2
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab0b107c050b1c4b686f761ede75ea2349825270
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="3d243-102">IHostThreadPoolManager::SetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="3d243-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="3d243-103">要求に応じるため、ホストを維持する必要がありますアイドルのスレッドの最小数を設定します。</span><span class="sxs-lookup"><span data-stu-id="3d243-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d243-104">構文</span><span class="sxs-lookup"><span data-stu-id="3d243-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d243-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3d243-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="3d243-106">[in]ホストが保持する必要がありますのスレッドの新しいの最小数。</span><span class="sxs-lookup"><span data-stu-id="3d243-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d243-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="3d243-107">Return Value</span></span>  
  
|<span data-ttu-id="3d243-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3d243-108">HRESULT</span></span>|<span data-ttu-id="3d243-109">説明</span><span class="sxs-lookup"><span data-stu-id="3d243-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3d243-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3d243-110">S_OK</span></span>|<span data-ttu-id="3d243-111">`SetMinThreads`正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="3d243-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="3d243-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3d243-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3d243-113">共通言語ランタイム (CLR) が、プロセスに読み込まれていませんまたは CLR は、状態をマネージ コードを実行またはできないの呼び出しは正常に処理します。</span><span class="sxs-lookup"><span data-stu-id="3d243-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3d243-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3d243-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3d243-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="3d243-115">The call timed out.</span></span>|  
|<span data-ttu-id="3d243-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3d243-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3d243-117">呼び出し元は、ロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="3d243-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3d243-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3d243-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3d243-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="3d243-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3d243-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3d243-120">E_FAIL</span></span>|<span data-ttu-id="3d243-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3d243-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3d243-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="3d243-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3d243-123">メソッドのホストに以降の呼び出しでは、HOST_E_CLRNOTAVAILABLE を返します。</span><span class="sxs-lookup"><span data-stu-id="3d243-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3d243-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="3d243-124">E_NOTIMPL</span></span>|<span data-ttu-id="3d243-125">ホストがの実装を提供していない`SetMinThreads`です。</span><span class="sxs-lookup"><span data-stu-id="3d243-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d243-126">コメント</span><span class="sxs-lookup"><span data-stu-id="3d243-126">Remarks</span></span>  
 <span data-ttu-id="3d243-127">ホストがの実装を提供する必要はありません`SetMinThreads`です。</span><span class="sxs-lookup"><span data-stu-id="3d243-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="3d243-128">この場合、HRESULT 値 E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="3d243-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d243-129">要件</span><span class="sxs-lookup"><span data-stu-id="3d243-129">Requirements</span></span>  
 <span data-ttu-id="3d243-130">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="3d243-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d243-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3d243-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d243-132">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="3d243-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d243-133">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d243-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d243-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d243-134">See Also</span></span>  
 <xref:System.Threading.ThreadPool.SetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="3d243-135">GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="3d243-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [<span data-ttu-id="3d243-136">SetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="3d243-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="3d243-137">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3d243-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)