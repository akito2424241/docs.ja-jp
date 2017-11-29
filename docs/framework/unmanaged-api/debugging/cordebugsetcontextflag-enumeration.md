---
title: "CorDebugSetContextFlag 列挙体"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugSetContextFlag
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugSetContextFlag
helpviewer_keywords: CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 958ed303fab3dcb01fad2040dd06381e76fe5a00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="e98fb-102">CorDebugSetContextFlag 列挙体</span><span class="sxs-lookup"><span data-stu-id="e98fb-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="e98fb-103">スタック上のアクティブ (またはリーフ) フレーム上からのコンテキストなのか、別のフレームからのアンワインドにより計算されたコンテキストなのかを示します。</span><span class="sxs-lookup"><span data-stu-id="e98fb-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e98fb-104">構文</span><span class="sxs-lookup"><span data-stu-id="e98fb-104">Syntax</span></span>  
  
```  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="e98fb-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="e98fb-105">Members</span></span>  
  
|<span data-ttu-id="e98fb-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="e98fb-106">Member</span></span>|<span data-ttu-id="e98fb-107">説明</span><span class="sxs-lookup"><span data-stu-id="e98fb-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e98fb-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="e98fb-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="e98fb-109">コンテキストは、スレッドのアクティブなコンテキストです。</span><span class="sxs-lookup"><span data-stu-id="e98fb-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="e98fb-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="e98fb-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="e98fb-111">別のフレームからのアンワインドにより計算されたコンテキストであります。</span><span class="sxs-lookup"><span data-stu-id="e98fb-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e98fb-112">コメント</span><span class="sxs-lookup"><span data-stu-id="e98fb-112">Remarks</span></span>  
 <span data-ttu-id="e98fb-113">`CorDebugSetContextFlag`によって使用されている値を提供、 [icordebugstackwalk::setcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)メソッドです。</span><span class="sxs-lookup"><span data-stu-id="e98fb-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e98fb-114">要件</span><span class="sxs-lookup"><span data-stu-id="e98fb-114">Requirements</span></span>  
 <span data-ttu-id="e98fb-115">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="e98fb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e98fb-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e98fb-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e98fb-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e98fb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e98fb-118">**.NET framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e98fb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e98fb-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e98fb-119">See Also</span></span>  
 [<span data-ttu-id="e98fb-120">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="e98fb-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="e98fb-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="e98fb-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)