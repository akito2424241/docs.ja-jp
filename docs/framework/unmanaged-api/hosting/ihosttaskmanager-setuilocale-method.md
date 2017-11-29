---
title: "IHostTaskManager::SetUILocale メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.SetUILocale
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c29687d430187577ac25d8d2a007785632989ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="2db5a-102">IHostTaskManager::SetUILocale メソッド</span><span class="sxs-lookup"><span data-stu-id="2db5a-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="2db5a-103">ユーザー インターフェイス (UI) のロケール、または現在実行中のタスクで、カルチャ、共通言語ランタイム (CLR) が変更されたことをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="2db5a-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2db5a-104">構文</span><span class="sxs-lookup"><span data-stu-id="2db5a-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2db5a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2db5a-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="2db5a-106">[in]新しく割り当てられた地理的なカルチャや言語にマップされるロケール識別子の値。</span><span class="sxs-lookup"><span data-stu-id="2db5a-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2db5a-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="2db5a-107">Return Value</span></span>  
  
|<span data-ttu-id="2db5a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2db5a-108">HRESULT</span></span>|<span data-ttu-id="2db5a-109">説明</span><span class="sxs-lookup"><span data-stu-id="2db5a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2db5a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2db5a-110">S_OK</span></span>|<span data-ttu-id="2db5a-111">`SetUILocale`正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="2db5a-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="2db5a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2db5a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2db5a-113">CLR が、プロセスに読み込まれていませんまたは CLR は、状態をマネージ コードを実行またはできないの呼び出しは正常に処理します。</span><span class="sxs-lookup"><span data-stu-id="2db5a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2db5a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2db5a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2db5a-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="2db5a-115">The call timed out.</span></span>|  
|<span data-ttu-id="2db5a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2db5a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2db5a-117">呼び出し元は、ロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="2db5a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2db5a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2db5a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2db5a-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="2db5a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2db5a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2db5a-120">E_FAIL</span></span>|<span data-ttu-id="2db5a-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2db5a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2db5a-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2db5a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2db5a-123">メソッドのホストに以降の呼び出しでは、HOST_E_CLRNOTAVAILABLE を返します。</span><span class="sxs-lookup"><span data-stu-id="2db5a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2db5a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="2db5a-124">E_NOTIMPL</span></span>|<span data-ttu-id="2db5a-125">ホストには、マネージ ユーザー コードの UI カルチャを変更するのにはできません。</span><span class="sxs-lookup"><span data-stu-id="2db5a-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2db5a-126">コメント</span><span class="sxs-lookup"><span data-stu-id="2db5a-126">Remarks</span></span>  
 <span data-ttu-id="2db5a-127">ランタイム呼び出し`SetUILocale`ときの値、<xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType>マネージ コードでプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="2db5a-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="2db5a-128">このメソッドは、ロケールの同期のための任意の機構いる可能性がありますを実行するホストの機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="2db5a-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="2db5a-129">ホストは、マネージ コードに変更する UI 言語を許可しないまたはロケールを同期するためのメカニズムを実装していません、このメソッドから E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="2db5a-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2db5a-130">要件</span><span class="sxs-lookup"><span data-stu-id="2db5a-130">Requirements</span></span>  
 <span data-ttu-id="2db5a-131">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="2db5a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2db5a-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2db5a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2db5a-133">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="2db5a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2db5a-134">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2db5a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2db5a-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="2db5a-135">See Also</span></span>  
 [<span data-ttu-id="2db5a-136">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2db5a-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="2db5a-137">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2db5a-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="2db5a-138">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2db5a-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="2db5a-139">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2db5a-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="2db5a-140">SetLocale メソッド</span><span class="sxs-lookup"><span data-stu-id="2db5a-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)