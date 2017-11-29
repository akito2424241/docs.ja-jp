---
title: "ICLRStrongName::StrongNameTokenFromAssembly メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameTokenFromAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameTokenFromAssembly
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly method [.NET Framework hosting]
- StrongNameTokenFromAssembly method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: fc725afb-b66b-4015-aa44-1c0d1304197f
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b236fe3b041277401c2983cf229981253c01328
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="eb177-102">ICLRStrongName::StrongNameTokenFromAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="eb177-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="eb177-103">指定したアセンブリ ファイルから、厳密な名前のトークンを作成します。</span><span class="sxs-lookup"><span data-stu-id="eb177-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb177-104">構文</span><span class="sxs-lookup"><span data-stu-id="eb177-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb177-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eb177-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="eb177-106">[in]アセンブリのポータブル実行可能 (PE) ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="eb177-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="eb177-107">[out]厳密な名前が返されたトークンです。</span><span class="sxs-lookup"><span data-stu-id="eb177-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="eb177-108">[out]厳密な名前のトークンのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="eb177-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb177-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="eb177-109">Return Value</span></span>  
 <span data-ttu-id="eb177-110">`S_OK`メソッドが正常に完了した場合それ以外の場合、失敗を示す HRESULT 値 (を参照してください[の共通 HRESULT 値](http://go.microsoft.com/fwlink/?LinkId=213878)一覧)。</span><span class="sxs-lookup"><span data-stu-id="eb177-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb177-111">コメント</span><span class="sxs-lookup"><span data-stu-id="eb177-111">Remarks</span></span>  
 <span data-ttu-id="eb177-112">厳密な名前のトークンは、公開キーの短縮形です。</span><span class="sxs-lookup"><span data-stu-id="eb177-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="eb177-113">トークンは、アセンブリの署名に使用する公開キーから作成される 64 ビット ハッシュです。</span><span class="sxs-lookup"><span data-stu-id="eb177-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="eb177-114">トークンは、アセンブリの厳密な名前の一部であるし、アセンブリのメタデータから読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="eb177-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="eb177-115">トークンの作成後を呼び出す必要があります、 [iclrstrongname::strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)を割り当てられたメモリを解放するメソッド。</span><span class="sxs-lookup"><span data-stu-id="eb177-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb177-116">要件</span><span class="sxs-lookup"><span data-stu-id="eb177-116">Requirements</span></span>  
 <span data-ttu-id="eb177-117">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="eb177-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb177-118">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="eb177-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="eb177-119">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="eb177-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb177-120">**.NET framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb177-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb177-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb177-121">See Also</span></span>  
 [<span data-ttu-id="eb177-122">StrongNameTokenFromAssemblyEx メソッド</span><span class="sxs-lookup"><span data-stu-id="eb177-122">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="eb177-123">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb177-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)