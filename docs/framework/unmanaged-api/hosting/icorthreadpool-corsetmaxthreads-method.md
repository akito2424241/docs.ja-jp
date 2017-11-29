---
title: "ICorThreadpool::CorSetMaxThreads メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorThreadpool.CorSetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSetMaxThreads
helpviewer_keywords:
- ICorThreadpool::CorSetMaxThreads method [.NET Framework hosting]
- CorSetMaxThreads method [.NET Framework hosting]
ms.assetid: 4a846238-df4e-4060-ba3b-5173f6a51e85
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 384b214ac38eb99ce45bf3050f33f35702813c69
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="01017-102">ICorThreadpool::CorSetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="01017-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="01017-103">このメソッドは、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="01017-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01017-104">構文</span><span class="sxs-lookup"><span data-stu-id="01017-104">Syntax</span></span>  
  
```  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="01017-105">要件</span><span class="sxs-lookup"><span data-stu-id="01017-105">Requirements</span></span>  
 <span data-ttu-id="01017-106">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="01017-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01017-107">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="01017-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01017-108">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="01017-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01017-109">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01017-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01017-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="01017-110">See Also</span></span>  
 [<span data-ttu-id="01017-111">ICorThreadpool インターフェイス</span><span class="sxs-lookup"><span data-stu-id="01017-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)