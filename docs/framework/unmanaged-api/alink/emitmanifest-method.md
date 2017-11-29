---
title: "EmitManifest メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EmitManifest
- IALink.EmitManifest
api_location: alink.dll
api_type: COM
f1_keywords: EmitManifest
helpviewer_keywords: EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 03ef815f03a65cbf7e2dc936b21848e206132add
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="emitmanifest-method"></a><span data-ttu-id="e2d9a-102">EmitManifest メソッド</span><span class="sxs-lookup"><span data-stu-id="e2d9a-102">EmitManifest Method</span></span>
<span data-ttu-id="e2d9a-103">最終的なマニフェストを出力します。</span><span class="sxs-lookup"><span data-stu-id="e2d9a-103">Emits the final manifest.</span></span> <span data-ttu-id="e2d9a-104">その他のすべてのファイルをインポートして、すべてのオプションを設定した後、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e2d9a-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="e2d9a-105">非バインド モジュールのこのメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="e2d9a-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2d9a-106">構文</span><span class="sxs-lookup"><span data-stu-id="e2d9a-106">Syntax</span></span>  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2d9a-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e2d9a-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e2d9a-108">アセンブリの ID です。</span><span class="sxs-lookup"><span data-stu-id="e2d9a-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="e2d9a-109">取得したアセンブリ ファイルで予約サイズを受け取る[StrongNameSignatureSize 関数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2d9a-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="e2d9a-110">必要に応じて、アセンブリのマニフェスト トークンを受信します。</span><span class="sxs-lookup"><span data-stu-id="e2d9a-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2d9a-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="e2d9a-111">Return Value</span></span>  
 <span data-ttu-id="e2d9a-112">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="e2d9a-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2d9a-113">要件</span><span class="sxs-lookup"><span data-stu-id="e2d9a-113">Requirements</span></span>  
 <span data-ttu-id="e2d9a-114">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="e2d9a-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2d9a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2d9a-115">See Also</span></span>  
 [<span data-ttu-id="e2d9a-116">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2d9a-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e2d9a-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2d9a-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="e2d9a-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="e2d9a-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)